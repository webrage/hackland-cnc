# CAM *- Fusion 360*
#### *[CAD](CAD.md) ==>* CAM *==> [MACHINE CONTROL](Machine.md)*

### CAM PURPOSE
The purpose of the CAM step is to translate what you have designed in your CAD software of choice, into a bunch of instructions *(gcode)* that will work on the *(Hackland)* CNC machine being used to bring your design to life.

__Fusion 360__ can be used for both CAD design and for CAM processing. This document describes the CAM process of getting from a Fusion 360 design to a Hackland CNC compatible gcode.

### Note
These notes are unashamedly opinionated, they describe just one way of many of doing things. They are also a work in progress. They are designed to help complete "first steps", not describe all the features.

### CAM setup *- Fusion 360*
Make sure you have specified the thickness of the ply you are using in the CAD drawing, preferably as a user specified parameter such as __ply_mm__.

Cam's documents some "one time" Fusion 360 setup steps needed for the CAM process here -    [mechmate-74-hackland-user-guide](https://hackingismakingisengineering.wordpress.com/mechmate-74-hackland-user-guide/#resources).
* Mapboards add-in *- to quickly 2D layout your 3D design - purchase for US$2 from the Fusion 360 store*
* Dogbone add-in *- quickly add dogbones to your internal corners, so components fit together nicely*
* Import the Fusion 360 Operations template - use this to quickly set up a draft standard CAM setup *- you can simply delete any process steps not required*
* Import the mechmate 74 library - use these tools which are available in Hackland


### CAM Steps *- Fusion 360*

#### Fusion 360 Preparation
1. select __Model toolbar__ for the following steps (if needed)
2. *right-click* __bodies  | create components__ to create components from the bodies you have selected
3. __Create | Mapboards__ to layout the components
    * __Lumber__ maximum of 1200 x 2400mm  (also select material)
    * __Arrange type__ Matching Lengths Vertical
    * __Saw Kerf__ 10mm
    * __Trim on Board Edge__ 6.35mm
    * __Map Orientation__ Z up
4. __Create | Dogbone__ to dogbone the components
    * select the __components__ you wish to dogbone
    * __tool diameter__ 6mm
    * __select up plane__ Z *- assuming board is on XY plane*
5. __model the screw restraint locations__
    * *use restraint screws every 500mm - less if material is thin or has a bow in it*
    * __Sketch | New Sketch__ put points (__Sketch | Point__) on the sketch where you want the restraint screws to go. Make sure you don't put a hole too near any drilling / milling!
6. __Change to the CAM toolbar__

#### Fusion 360 CAM toolbar
1. __Setup | New Setup__
    * __Setup | Setup__ Milling
    * __WCS | Orientation__ Model Orientation
    * __WCS | Origin__ Stock box point
    * __WCS | Stock Point__ This is __important!__ select the BOTTOM left hand corner of the stock.
    * __Model | Model__ select the stock and work bodies to mill
    * __Stock | Mode__ Relative size box
    * __Stock | Stock Offset Mode__ No additional stock
    * __Post Process | Program Name__ your-model-name
2. *right-click* __Setup1 | Create From Template | 2.5d - Typ - wood ops.drill_profile_pocket__ - to create a draft CAM setup
3. Adjust the setup operations that you have created - follow notes below as appropriate before continuing.
4. *right-click* __Setup1 | Generate__ to generate a toolpath for all operations
5. *right-click* __Setup1 | Simulate__  to simulate the CAM opartion
6. *right-click* __Setup1 | Post Process__ to create the gcode - .tap file
    * Give it a good name that will distinguish it as yours *- not “gcode.tap”!*
    * Put on USB drive ready to transfer to the MechMate CNC computer

#### Standard Process Steps
It is useful to think of the CNC process as a number of standard process steps that are completed in a standard order. Not all of these steps will be needed for every job. At the end of each process step the CNC machine should stop (for a tool change). *If the next step has the same tool - just click OK on the computer to carry on*
1. __Drill Hold Down Holes__  *drill holes for hold down the work-piece during the more vigorous operations that follow.*
     * __Tool | Tool__ e.g. #24 - 4mm drill - from the Hackspace drill library
     * __Geometry | Hole Mode__ Selected Points
     * __Geometry | Hole Points__ Select one of the points to drill
     * secure work-piece to CNC after this step
     * __Geometry | Select Same Diameter__ True
     * __Geometry | Optimize order__ True     


2. __Drill holes__
     * __Tool | Tool__ e.g. #24 - 4mm drill - from the Hackspace drill library
     * __Geometry | Hole Mode__ Selected Faces
     *  __Geometry | Hole Faces__ remember to select a cylinder face from your work *- you may need to turn off any filtering*
     * __Geometry | Select Same Diameter__ True
     * __Geometry | Optimize order__ True



5. __Pockets__ - mill any pockets that do not penetrate the work
     * __Tool | Tool__ e.g #162 5.5 mm flat *- from the Hackspace drill library*
     * __Geometry | Contour Selection__ remember to select bottom contours of components

6. __Profile Internal__ - cut all components with internal holes
     * __Tool | Tool__ e.g #162 5.5 mm flat *- from the Hackspace drill library*
     * __Geometry | Contour Selection__ remember to select bottom contours of components

7. __Profile External__ - finish cutting out components, leaving tabs to secure work+
     * __Tool | Tool__ e.g #162 5.5 mm flat *- from the Hackspace drill library*
     * __Geometry | Contour Selection__ remember to select bottom contours of components
     * __Geometry | Tabs__ True
     * __Geometry | Tab Shape__ Rectangular
     * __Geometry | Tab width__ 5.5 mm
     * __Geometry | Tab height__ 2 mm
     * __Geometry | Tab Positioning__ By Distance
     * __Geometry | Tab Distance__ 150 mm


     3. __Countersync holes__
          * __Tool | Tool__ e.g
          * __Geometry | Contour Selection__


     4. __Engraving__ - any shallow engraving
          * __Tool | Tool__ e.g
          * __Geometry | Contour Selection__ remember to select bottom contours of components



8. __Camfering__
     * __Tool | Tool__ e.g
     * __Geometry | Contour Selection__

### Recommended Links
* [mechmate-74-hackland-user-guide](https://hackingismakingisengineering.wordpress.com/mechmate-74-hackland-user-guide/)
* https://github.com/caseycrogers/Dogbone - Dogbone add-in

### Other Links
* https://github.com/tapnair              - some Fusion 360 add-ins
