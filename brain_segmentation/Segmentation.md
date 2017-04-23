
#### Reconstructing the Brain

### Instillation of FreeSurfer
After downloading the software package, open the Terminal window on your computer. 
The first step is to define the home enviroment for FreeSurfer, the code below is what needs to be entered in the Terminal for Macs.

```
$> export FREESURFER_HOME=/Applications/freesurfer
$> source $FREESURFER_HOME/SetUpFreeSurfer.sh
```

After the enviroment is set, which is needed to be done each time the terminal is opened, it is time to test that the installation work. 
FreeSurfer has two different sets of code that allow you to test your download.
I personally only used the one that ended with the opening of their example MRI scan in Freeview.

```
$> cd $FREESURFER_HOME/subjects
$> freeview -v \
    bert/mri/T1.mgz \
    bert/mri/wm.mgz \
    bert/mri/brainmask.mgz \
    bert/mri/aseg.mgz:colormap=lut:opacity=0.2 \
    -f \
    bert/surf/lh.white:edgecolor=blue \
    bert/surf/lh.pial:edgecolor=red \
    bert/surf/rh.white:edgecolor=blue \
    bert/surf/rh.pial:edgecolor=red
```

If run correctly, this image below is what should been seen in Freeview.


![alt text](https://github.com/nomcomm/IndependentStudy_NolanJahn/blob/master/Screen%20Shot%202017-04-17%20at%205.36.28%20PM.png)

If it worked, you are ready to move on to the Recon-all function.

### Running Reconstruction Command
First, the location of the MRI scan folder needs to be in an easy to direct to location.
Putting the file on the desktop is typically the easiest. 
When pulling up the the file on Finder there will be a directive path at the bottom, as highlighted on the photo below.


![alt text](https://github.com/nomcomm/IndependentStudy_NolanJahn/blob/master/Edited%20Screen%20Shot.jpg)

Once, you know the path to the file, the path has to be coded in the Terminal.
Below is the code for the Subject Directive command in the Terminal.
The first line will be the code with no path inserted, the next will be the code with the path to my file inserted.

```
SUBJECTS_DIR=/path/goes/here

SUBJECTS_DIR=/Users/nolanjahn/Destop/ralfbrain
```

To check if this worked correctly, test it with the code below.

```
$SUBJECTS_DIR
```

If it worked, the output will say
```
-bash: /Users/nolanjahn/Desktop/ralfbrain: is a directory
```
Everything is ready for the Recon-all command.
It is a very short command, but it is powerful, and there is a lot of room for errors to arise.
Again, if it does not work, go back to the Freesurfer Wiki or try this [Stanford Freesurfer page.](https://web.stanford.edu/group/vista/cgi-bin/wiki/index.php/FreeSurfer)
Below is the command for Recon-all, the first with no path directed, the second is the one I used.

```
recon-all -i /path/to/NIFTI/T1/MRI/Scan -s subject file name -all

recon-all -i /Users/nolanjahn/Desktop/ralfbrain/Ralf_MRT.nii -s ralfbrain3 -all
```

If no error is seen right after running this command, the program will run for anywhere from a couple of hours to a couple of days.
Afterward, in the folder that was your subject file, there will be number of new sub folders with new files. 
In the ralfbrain3 folder, there is a sub folder, surf, that has dozens of new files.
Two files from the surf folder will be used going forward, lh.pial and rh.pial.
