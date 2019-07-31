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

The dropper used a single servo in order to save weight. The use of the arduino allows for a single PPM signal from the Pixhawk to be interpreted for three positions of the servo.

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

## Electrical/Software
A protoboard was built to connect the arduino nano, servo and Futaba RC receiver for control of the servo.
The source code for the arduino is available: 

## How to Use
Once the system is setup, calibrate the servo positions in the arduino code. Be sure this is done with all of the arms open. Because of the elastics the servo can push in the wrong direction and either jam or worse break an arm. The arms are weak so it is advisable to have spares. Once it is calibrated, to reset put all of the arms in the open position, press the reset button on the arduino and wait until the servo resets. Once this happens, close the arms and put the elastics on.
