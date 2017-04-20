Independent Study Nolan Jahn
=======================================

This repository was created to keep track of  Nolan Jahn's Independent Study in the Lab in SS2017 at Michigan State University.
The main purpose was to learn how to reconstruct a 3D image of a brain from a T1 MRI scan of a head, using FreeSurfer software. 
The surface image, then was imported into a modeling software, in this case MeshLab, to be prepared for 3D printing.
The model was brought to the Michigan State University Library, to be printed at thier Make Centeral 3D printing station.
Then we were joined by Eric Novotny and moved into virtual reality.
MSU Communication Department's Charisma Lab, which features HTC Vive VR system. 

Documentation
-------------

A good tutorial to learn git is: https://try.github.io

### Step 1: Reconstucting the brain

The first step in this project is to take the T1 MRI scan and to digitally reconstruct a 3D image of the brain, including all the segmented parts.
There are three main steps to the reconstruction: installing freesurfer (the MRI scan analyzing software), run the reconstruction command, and finally check the results of the command.
Here is the entire [tutorial.](https://github.com/nomcomm/IndependentStudy_NolanJahn/blob/master/brain_segmentation/Segmentation.md)

#### Installing freesurfer

Here is the link to [FreeSurfer website.](https://surfer.nmr.mgh.harvard.edu/)
There are versions for various operating systems, I personally used a Mac for this project, so the following instructions will all be specific for a Mac, however FreeSurfer has their own Wiki page that can help with any questions that you will have not addressed in this [tutorial.](https://surfer.nmr.mgh.harvard.edu/fswiki/FreeSurferWiki)
It is crucial after downloading to the software, to also download a license agreement, this is free as well. 

#### Running Reconstruction command

Utalizing FreeSurfer is done in what is called the Terminal for Macs. The Terminal is a powerful tool to operate the software, and it helps to have some background on how to code in command line language, although it is not necessary.
After having the checked that the download for FreeSurfer worked correctly, it is time to code FreeSurfer to run the "Recon-all" command, which will reconstruct the MRI scan, which should be saved as a NIFTI file, into a 3D image.
If the command is running properly, it will take several hours or up to a day, for your computer to finish the reconstruction, depending on the processing power of your computer. 

#### Checking the results

The finished product will result in a new folder in the folder that held your original NIFTI T1 MRI scan. 
This folder will have the name surf, and it will should have several different images that have a label of lh or rh, which stand for left hemisphere and right hemisphere respectively.
The two that are of most interest are lh.pial and rh.pial, both of these are 3D images of the outer cortical surface, which is what is wanted to be printed.
Freeview, the viewing app for FreeSurfer, can be used to open both lh.pial and rh.pial.
After this step, you will be ready to move on to preparing the 3D images for printing.
The Recon all function will also the segment the subcortical structures and the cerebellum, if you want to print that as well. 

### Step 2: Preparing the brain surface for 3D printing

#### Converting files
The first step in this process, is turning the pial images into .stl files, which can be opened in any software that prepares images to be 3D printed. The details to this step and the following ones can be found on this [tutorial](https://github.com/nomcomm/IndependentStudy_NolanJahn/blob/master/3d_printing/3D_print.md)

#### Preapare Meshes for 3D printing
Next, a software to prepare the image for printing will have to be downloaded. 
I used Meshlab for my software, this also can be downloaded for various operating [systems.](http://www.meshlab.net/)
After the software is downloaded, both .stl files can be opened at the same time into Meshlab.
After a few minor adjustments to the meshes are made, it can be exported as one complete mesh that is ready for printing.

#### Print the finalized Mesh
After the alterations are made, and there is one ready to print .stl file, it is time to find access to a 3D printer.
As a student at Michigan State Univeristy, I used our library 3D printer.
There are many online sources that allow you to submit a file to be printed.
It is important to remember that .stl files are dimensionless files, so the dimensions of the brain mesh can be altered to fit the costs you are willing to print.

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
