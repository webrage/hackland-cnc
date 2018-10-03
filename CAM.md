# CAM
#### *[CAD](CAD.md) ==>* CAM *==> [MACHINE CONTROL](Machine.md)*



* __CAM__: You have used the CAM feature in Fusion 360 or other package to create a suitable gcode file to be used on the Hackland MechmMate CN* __CAM__: You have used the CAM feature in Fusion 360 or other package to create a suitable gcode file to be used on the Hackland MechmMate CNC machine. This includes:
  * 2D version of your model (perhaps using the mapboards Fusion 360 plugin)
  * “Dogboned” corners as needed
  * Added tabs to keep the work secure as needed
  * Used milling tools from the Hackland tool library
  * Specified the size of your workpiece and the thickness of the ply you are using
  * Created gcode file (a .tap file) and given it a name that identifies your project
  * Put the gcode file on a USB file - ready to be imported into the MACH3 CNC softwareC machine. This includes:
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
