# MECHMATE
#### *[CAD](CAD.md) ==> [CAM](CAM.md) ==>* MACHINE CONTROL

The notes below assumes:
* __CAD__: you have created you design in Fusion 360 or other package
* __CAM__: You have used the CAM feature in Fusion 360 or other package to create a suitable gcode file to be used on the Hackland MechmMate CNC machine.

This includes:
  * 2D version of your model (perhaps using the mapboards Fusion 360 plugin)
  * “Dogboned” corners as needed
  * Added tabs to keep the work secure as needed
  * Used milling tools from the Hackland tool library
  * Specified the size of your workpiece and the thickness of the ply you are using
  * Created gcode file (a .tap file) and given it a name that identifies your project
  * Put the gcode file on a USB file - ready to be imported into the MACH3 CNC software
  * Separated the Job into sensible process steps (the order of steps matter). For example:
    * Hold Down - Drill holes for hold down (secure workpiece to CNC after this step)
    * Drill Holes - drilling
    * Countersync - countersyncing
    * Engraving - any shallow engraving
    * Pockets - mill any pockets that do not penetrate the work
    * Profile Internal - cut all components with internal holes
    * Profile External - finish cutting out components, leaving tabs to secure work+

### CNC Startup Steps
1. __Clear up on and around the CNC router__
  * make sure the surface is clear so job can lie flat - vacuum away dust etc using the dust extractor if needed
  * Make sure all rails and the table are clear of obstructions so the mechmate can move unimpeded
  * Check the CNC machine looks OK, including the dust extraction ducting around the mill/drill
  * Ensure the milling cover is on for dust extraction
2. __Safety__
  * Make sure there are no tripping hazards in the work area
  * Never put your hands on the rails
  * Let people know the CNC machine will be turn on
  * Use ear muffs (noisy), eye protection (things can fly off CNC), dust protection (especially for long jobs) …
3. __Check spindle coolant levels__
  * check the red tank under the table next to control box
  * __If low ...__
4. __Turn on CNC__
  * Turn red switch to ON position (CNC control box)
  * Push top Green button (CNC control box)
  * Turn on Coolant Pump - red tank under the table next to control box, plug it in to power (or turn on power on power board)
  * Turn on the Dust Extractor
5. __Power up PC__
  * Turn on PC
  * Open Mach3 software

### Job Setup Steps
1. __Load the gcode__ (.tap file)
  * In Mach3 -Load GCode - load from your USB drive inserted into CNC computer
  * Check GCODE - make sure it is your file and the gcode looks OK
2. __Zero the CNC machine X & Y coordinates?__
  * To zero the machine - press the __REF ALL HOME__ button.  The machine will head to the X & Y e-stops and then back off a little, giving it the info it needs to zero the machine. Green lights beside Zero X and Zero Y show it was successful.
  * Note: In Mach3 red around the Machine Coordinates button means it is showing the Machine coordinates, rather than the Job Coordinates.
  * The X axis is the longer side (approx 2400mm), The Y axis is the shorter side (approx 1200mm)
  * 0, 0 is the corner nearest the aluminium Z stop
3. __Place material on work table__
  * Check job restrained effectively - restrain it now or do this later once you have drilled some safe holes
4. __Zero the Job X & Y coordinates__
  * Jog machine to the bottom left hand corner of your job.
  * Use __arrow buttons__ to move in X & Y directions; or __shift-arrow__ moves more quickly
  * Use __PageUp__ and __PageDown__ to move in Z directions (Don’t move Z too far up or down)
  *Remember that you are zeroing the machine coordinates when there is NOT a red box around the  Machine Coordinates button.*
  * Set the job coordinates to X=0 , Y=0 by pressing the Zero X and Zero Y buttons
  * __Regen Toolpath__ - look at the display (Toggle Display Mode if needed) showing the location of your job relative to the table. The cross hairs should be over the left hand corner of your job.
  *Note, don’t worry about Z-axis, this zeros automatically when the tool zeros.*
  *Note also that Z is homed to top, so touching the work with the mill is a -ve number*
5. __Trace the job to make sure if all fits on the stock__
  * Check toolpath looks OK
  * Check Z clearance?
6. __Override feed rate to 10% when job is starting__
   * return to 100% when job is running as expected.
7. __Start running the gcode__
  * __Cycle Start__

### CNC Shutdown Steps
1. __Clean up the machine area__
  * Take the work off the machine - jog the machine out of the way if need be
  * Clean up mess on and around the machine
  * Making sure that tools are put away in the right place
  * Vacuum away dust etc using the dust extractor - jog the machine out of the way if need be
2. __Turn off CNC__ (after cleanup above)
  * Turn red switch to OFF position (CNC control box)
  * Turn OFF Coolant Pump - red tank under the table next to control box
  * Turn OFF Dust Extractor
3. __Put away safety gear__
  * Ear, eye & dust protection
4. __Power OFF PC__
  * Shut down Mach3 software
  * Shutdown the PC
  * Make sure you have you USB stick

### Troubleshooting / Issues
cstewart000@gmail.com

### Recommended Links
* [Mechmate-74-hackland-user-guide](https://hackingismakingisengineering.wordpress.com/mechmate-74-hackland-user-guide/) *- Cams User Guide*
* [Mach3 User Interface]()                  - Mach3 User Interface
* [Mach3 Coords Video]()                     - Mach3 CNC Controller, Homing / Limits / Offsets


### Other Links
* [Cams Blog](https://hackingismakingisengineering.wordpress.com/) *- Cams Blog*
* [Cams VB Scripts](https://github.com/cstewart000/HME_Mach3) *- Cams Github MechMate VB scripts*
* [MechMate Hardware](http://www.mechmate.com/) *- Mechmate machine page*
* [Mach3 CNC controller software](http://www.machsupport.com/software/mach3/) *- Mach3 CNC support page*
