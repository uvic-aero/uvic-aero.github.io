# Using the laser cutter
The UVic machine shop has a laser cutter which is very helpful for being able to rapidly manufacture light, inexpensive parts for the aircraft.

The laser cutter can cut wood and certain plastics. Primarily, we laser cut either 1/8 in or 1/4in birch plywood. The next most common is Acrylic plastic. Polycarbonate (also known as Lexan) CANNOT be cut.

## Designing for the Laser Cutter
The design process is faily straight forward.
First design the part in Solidworks in 3D using the thickness of the wood. For very precise assemblies it is valuable to measure the thickness of the piece of wood which you are using as they are not very consistent. 
Next the part must be exported to a DXF. A DXF is a 2D text based format that is useful for transferring the data.
It is important to note that the beam has a diameter. For perfectly fitting parts an offset may be required to copmensate for that. 

## Calibrating the Laser Cutter
To turn on the laser cutter turn the black key to the right. If it has been off, the bed will likely go all the way down to its lowest position. Don't touch any of the buttons while this step is occurring. 
Once the cutter has stopped moving, use the arrow keys to move the bed up and the laser head around the work surface.
In order for the beam to be in the best focus, the height must be calibrated. To do this, place the calibration piece, [Insert photo] on the edge of the beam head. Place the piece of material on the work surface and move the laser head so that it is on top of it. Now slowly move the bed up until the metal calibration piece is touching or just bumped off the head. Now the height has been calibrated. 

Finally, open the DXF(s) in Inkscape. To add extra DXFs to a drawing in Inkscape use the shortcut Ctrl+I to import additional drawings.
Because we use an educational version of Solidworks, Solidworks inserts a watermark of Solidworks Educational. Simply select the words and delete them in Inkscape.
Before printing, select all, Ctrl+A, and go the right hand panel and choose fill and stroke. Go to stroke and choose solid. For the colour, unless you are engraving choose red. (R: 255, G:0, B:0) and the thickness 1pt.
Now you are ready to cut. From Inkscape on the laser cutter computer print the file to Trotec Engraver (Ctrl+P).
After a few seconds the JobControl app will flash yellow. Open JobControl. On the right, there is a panel of tasks. Your DXF will be the most recent. Click and drag it onto the work area. The white rectangle represents the works area of the laser cutter.
The crosshair represents the location of the laser.
