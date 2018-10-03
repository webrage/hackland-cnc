# MECHMATE
#### *[CAD](CAD.md) ==> [CAM](CAM.md) ==>* MACHINE CONTROL

 *The notes below assumes:*
* __CAD__ *: you have created you design in Fusion 360 or other package*
* __CAM__ *: you have used the CAM feature in Fusion 360 or other package to load a suitable __gcode__ file onto a USB drive ready to be used on the Hackland MechMate CNC machine. Refer to [CAM](CAM.md) for info on this step*

### CNC Startup Steps
1. __Clear up on and around the CNC router__
  * make sure the surface is clear so job can lie flat - vacuum away dust etc using the dust extractor if needed
  * make sure all rails and the table are clear of obstructions so the mechmate can move unimpeded
  * check the CNC machine looks OK, including the dust extraction ducting around the mill/drill
  * ensure the milling cover is on for dust extraction

2. __Safety__
  * make sure there are no tripping hazards in the work area
  * never put your hands on the rails of the CNC machine
  * let people know the CNC machine will be turn on
  * use ear muffs (noisy), eye protection (things can fly off CNC), dust-mask (dust protection,especially for long jobs) …

3. __Check spindle coolant levels__
  * check the coolant level of the red tank under the table next to the CNC control box
  * __If low ...__

4. __Turn on CNC__
  * turn on the turn the CNC machine
    * turn the red switch to the ON position (CNC control box)
    * push the top Green button ON (CNC control box)
  * turn on the Coolant Pump *- this is the red tank under the table next to control box, plug it in, and/or or turn on power on the power board*
  * Turn on the Dust Extractor

5. __Power up PC__
  * Turn on PC
  * Open Mach3 software

### Job Setup Steps
1. __Load the gcode__ (.tap file)
  * in Mach3 __Load GCode__ *- to load from your USB drive inserted into CNC computer*
  * check the gcode *- make sure it is your file and the gcode looks OK*

2. __Zero the CNC machine X & Y coordinates?__
  * to zero the machine - press the __REF ALL HOME__ button.
  *The machine will head to the X & Y e-stops and then back off a little, giving it the info it needs to zero the machine. Green lights beside Zero X and Zero Y show it was successful.*
  * *Note:*
    * *in Mach3 red around the Machine Coordinates button means it is showing the Machine coordinates, rather than the Job Coordinates.*
    * *the X axis is the longer side (approx 2400mm), The Y axis is the shorter side (approx 1200mm)*
    * *0, 0 is the corner nearest the aluminium Z stop*

3. __Place material on work table__
  * restrain it now - *unless you are using the CNC machine to drill some safe restraining holes*

4. __Zero the Job X & Y coordinates__
  * Jog machine to the bottom left hand corner of your job.
    * __arrow buttons__ move in the X & Y directions slowly
    * __shift-arrow__ moves in the X & Y directions quickly
    * __PageUp__ & __PageDown__ move in the Z directions *- be careful not to move the router too far up or down*
  * Set the job coordinates to X=0 , Y=0 by pressing the __Zero X__ and __Zero Y__ buttons - *remember that you are zeroing the machine coordinates when there is NOT a red box around the __Machine Coordinates__ button.*
  * __Regen Toolpath__ - look at the display (Toggle __Display Mode__ if needed) showing the location of your job relative to the table. The cross hairs should be over the left hand corner of your job.
  * *Note, don’t worry about Z-axis, this zeros automatically when the tool zeros.*
  * *Note also that Z is homed to the top, so touching the work with the mill is displayed as a -ve number*

5. __Trace the job to make sure if all fits on the stock__
  * Check toolpath looks OK
  * make sure the job is oriented correctly -
  * check all fits on the stock

6. __Override feed rate to 10%__
   * return to 100% when job is running as expected.

7. __Start running the gcode__
  * press the __Cycle Start__ button
  * Restrain the work once the drilling of restraining holes complete *- If drilling restraining holes, this should be the first CNC process in your gcode*
  * return the feed rate to 100% *- when job is running as expected*

### CNC Operating Rules of thumb
* __Tight, but not over-tight__
  *  try not to over tighten when doing a tool change

* __Don't distract the PC__
  * try not load or run other programs on the CNC PC - especially when running the CNC machine. *The CNC machine operates over very short timing cycles, such that the PC needs to "concentrate hard" on running the job and not be "distracted" by non critical stuff. It the PC gets out of step with the CNC machine the job will throw an error :(*

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
* Refer to Cam's list of current issues on his [website](https://hackingismakingisengineering.wordpress.com/mechmate-74-hackland-user-guide/#troubleshooting).
* Send an email to <mechmate74@gmail.com> if:
  * an issue is discovered *- whether or not it is resolved*
  * you do not leave the CNC router in a working state for any reason

### Recommended Links
* [Mechmate-74-hackland-user-guide](https://hackingismakingisengineering.wordpress.com/mechmate-74-hackland-user-guide/) *- Cams User Guide*
* [Mach3 User Interface](https://www.youtube.com/watch?v=08qK4NfnXqA) *- Video overview of the Mach3 User Interface*
* [Mach3 Coords](https://youtu.be/ACx64oWwbMc) *- Video of Mach3 CNC Controller, Homing / Limits / Offsets*

### Other Links
* [Cams Blog](https://hackingismakingisengineering.wordpress.com/) *- Cams Blog*
* [Cams VB Scripts](https://github.com/cstewart000/HME_Mach3) *- Cams Github MechMate VB scripts*
* [MechMate Hardware](http://www.mechmate.com/) *- Mechmate machine page*
* [Mach3 CNC controller software](http://www.machsupport.com/software/mach3/) *- Mach3 CNC support page*
