# Marker Dropper 2019

## Requirements
For the 2018-19 Competition USC required the placement of a 3D printed marker on to a velcro surface

## Considerations
When working on the design a number of constraints and goals were imposed
* Work from an altitude of >5m
* Pose no risk of damage to the flight platform
* Attach to the Scout or Ranger
* Marker must fall so that the velcro is flat

## Design
The dropper was initially prototyped as a shooter. The shooter was found to be ineffective because it caused the markers to spin in the air. Using slow motion video we could see that less rotation occured with the dropper.

The dropper is designs as triangular payloads with three holes in the corners. The holes are sockets for the markers. The markers are held in place with pairs of clamp arms tensioned with rubber bands. Each pair of arms is coupled with gears, and one arm extends further, to allow a triggering actuator to unclamp the arms and drop the marker. This is accomplished with a centrally-located servomotor which turns in a specific sequence to open one set of arms at a time.

The dropper used a single servo in order to save weight. Two PWM signals sent to the control system allow triggering the servo to drop the next marker.

## Manufacturing
BOM:

|Quantity  | Material      | Cost|
|----------|-----------|------|
|3inx4in   | 1/8in plywood | $|
|_N_       | M3 Screws     ||
|_N_       |M3 Nylock Nuts ||
|6       |Rubber Squares | |
|6 |Nylon spacers||
|1|_Hitech_ Servo||
|Many |_Dollar store_ elastic bands|$1.5|
||Wood glue||

The DXFs for laser curring are available:

The laser cut structure is glued together as shown in the 3D model. The orientation of the arms depends on the orientation of the servo. 
[image of arms]
The rubber square should be glued in the curve of the arms to help hold the markers in place.

## Electrical/Embedded Control System
The dropper is actuated by a control system consisting of an Arduino-based prototype board, a Futaba radio receiver, and a 3S battery.

### Hardware
The following components comprise the hardware:
* Arduino Nano
* Dropper prototype board
* Futaba r6303sb receiver
* 3S battery
* Servo motor (7V input)
* Cables (1x 3-wire servo cable, 2x 3-wire radio receiver cables)

The protoboard has one power input, which accepts 3S voltage levels (~10V). The power is then stepped down to 7.2V (nominal) via a low drop-out (LDO) linear regulator. Power is routed to the Arduino Nano _Vin_ pin, and internal stepped down to 5V. Power is also routed to the servomotor and the receiver. Two ports on the board are receiver channel inputs, and one is the servomotor output.

__TODO__: make schematic of prototype board and link to it, make a table with the BOM here

### Embedded Firmware

The firmware is a fairly straightforward Arduino script. 

The script measures radio inputs to determine when to drop a marker. One PWM channel from the receiver represents a safety signal, the other a trigger signal. The script ensures that to drop the marker, the safety signal must be in the "armed" mode before the trigger signal sends the drop command. A trigger signal that occurs when the safety is not in "armed" mode is ignored. The signals are 70 Hz PWM, with a duty-cycle that can take on discrete values of 1 ms or 2 ms pulse length. For the safety signal, 1 ms duty is "safe", 2 ms is "armed". For the trigger signal, 1 ms duty is default; 2ms is the drop signal.

Once a trigger condition is detected, the firmware actuates the servo motor to the next position that corresponds to a drop. Markers are dropped in a specific order that corresponds to the geometry of the payload. These positions are encoded in an array. Additionally, after a drop, the servo retracts slightly to releive tension on the arms. After a drop, both PWM channels must go back to default signal ("safe" and "no action") before another trigger event can be detected (i.e. it is not possible to fire multiple droppers without disarming between each drop). After three drops, any further trigger conditions are ignored.

The firmware is stored in a repository in bitbucket [here](https://github.com/uvic-aero/Dropper2019)

## How to Use

1. If not already done, disconnect any wires from the prototype board
2. Load the firmware according to the steps [below](### Load Firmware)
3. Reattach all cables to the Arduino Nano, WITHOUT connecting the battery.
4. With all the SERVO ARMS OPEN (no elastics), connect the battery. The servo should spin to its starting position. It is important to follow this instruction exactly since with the elastics on or the arms closed, the servo can push in the wrong direction and either jam or worse break an arm.
5. Close the arms around the markers, and put the elastics on.
6. Turn on Futaba transmitter
7. To drop, flick the left trigger into the up position, then hold the right trigger momentarily. The first marker should drop.
8. Release the right trigger, and flick the left back into the off position.
9. Repeast 7 and 8 to continue releasing markers.

The arms are weak so it is advisable to have spares. Once it is calibrated, to reset put all of the arms in the open position, press the reset button on the arduino and wait until the servo resets. Once this happens, close the arms and put the elastics on.

### Load Firmware
1.	Download or clone the firmware from the code repository [here](https://github.com/uvic-aero/Dropper2019).
2.	Open the file entitled “Rev1/Rev1.ino” in the Arduino IDE or other Arduino-compatible IDE.
3.	Connect the Arduino Nano to the computer using a USB Mini-B-terminated cable.
4.	In the tools menu, select Board->Arduino Nano and select the appropriate serial port with Port->[PORT NUMBER] (on Windows, this should be something like COM#, on MAC or Linux, something like tty/USB#).
5.	Compile and upload the firmware (arrow button in the top left of the IDE). If the IDE says that no board can be found at that port, check that you have the correct Port settings (see step 4). If that doesn’t work, make sure your USB data supports data transfer.
6.	Once the compilation and upload is complete, disconnect the Nano from the USB cable.
7.	The firmware should be successfully installed.
