
#### Reconstructing the Brain

### Instillation of FreeSurfer
After downloading the software package, open the Terminal window on your computer. 
The first step is to set to define the home enviroment for FreeSurfer, the code below is for the Terminal for Macs.

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
