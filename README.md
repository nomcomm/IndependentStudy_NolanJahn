Independent Study Nolan Jahn
=======================================

This repository was created to keep track of  Nolan Jahn's Independent Study in the Lab in SS2017 at Michigan State University.
The main purpose was to learn how to extract brains
Then we were joined by Eric Novotny and moved into VR
It went so great we were even able to go to charisma.... and print out.....

Documentation
-------------

A good tutorial to learn git is: https://try.github.io

### Step 1: Segmenting the brain
Text goes here
Here is the short description
Here is the entire [tutorial](https://github.com/nomcomm/IndependentStudy_NolanJahn/blob/master/3d_printing/3D_print.md)

test
[Notebook #01](https://github.com/nomcomm/IndependentStudy_YiYan/blob/master/scripts/Plot_Networkx_Brain_Communities.ipynb)

#### Installing freesurfer
#### Running segmentation command
#### Checking the results

### Step 2: Preparing the brain surface for 3d printing
#### a
#### b
http://github.com - automatic![GitHub](http://github.com)


### Step 3: Preparing for Virtual Reality 1: Converting .3ds file to a .osgb (Open Scene Graphics file)

	a) Download brain image as a .3ds file, save to Desktop as something (e.g., brain.3ds).
	b) Download 2 free programs: Autodesk 3DS Max (2016 or 2017; free for students) and OSG Exporter of same year.
	c) Open 3DS Max, go to File -> Import -> open the brain.3ds file from your computer.
	d) Once brain.3ds is imported and visible on 3DS Max, go to File -> Export -> File type -> OSGB -> and save as brain.osgb.
	e) A dropdown menu will open up. Click check boxes as you see fit (defaults are presented at http://docs.worldviz.com/vizard/exporting.htm), and at the bottom of this menu click OK.
	f) The Autodesk 3DS Inspector Editor will open and show the brain. Change color and lighting as you wish.

### Step 4: Preparing for Virtual Reality 2: Programming the .osgb file into an empty VR world

	a) Download and open Vizard (the VR programming environment software).
	b) Type the following code into the window, highlight all and press the green arrow on top

      #starts vizard script and opens empty world
      import viz
      viz.go()

      #Setting the start position of the viewer; change as necessary (in parentheses are x,y,z coordinates respectively)
      viz.MainView.setPosition(-8,-4,4)
      #for some reason negative means right, up and forward

      #creating object variable called brain, and viz.AddChild gets this object from the path in parentheses
      brain = viz.addChild ('C:/Users/Eric/Desktop/brain.osgb')

      #doubles size
      brain.setScale(2.0,2.0,2.0)   
	
 ### Step 5: Preparing for Virtual Reality 3: Getting brain into VR and seeable with HTC Vive 
 
	a) Turn on the HTC Vive (VR hardware) via the CARISMA lab computer
	b) In Vizard, go to Tools and click on Vizconnect, and press OK on prompt
	c) Save script as brain.py or something like that (.py is python file)
	d) Two windows will open now: A piazza.osgb file (Italian courtyard VR world) and the Vizconnect Startup window
	e) In Vizconnect startup, click "Select from some preset..." and click on HTC Vive, and Apply Preset.
	f) This will apply a preset program to your current program, and enable you to see the brain in the headset
 #### More to come on making brain manipulable and centered in VR world; right now, it is only viewable, and somewhat distant.


Examples
--------

Text goes here and ideally a link to some example ipynbs that demonstrate the features.

Dependencies
------------


### Mandatory

- Freesurfer


Development
-----------
https://github.com/nomcomm
Nolan Jahn & Ralf Schmaelzle
