### Description of 3D Printin Steps
Now that there are two files represent the surface of each hemisphere of the brain, there are a couple of steps before to complete to reach the point of a printed copy of a brain. 

#### Converting Files to .stl Files
The two files of interest are saved as .pial, which indicates that it is the outer-most surface of the brain.
Fortunately, Freesurfer is equipped with the ability to convert these files to .stl files. 
It is a relatively easy code to convert the files, and like previously for the recon-all command, the path to the .pial files will be needed.
Below is the command, the first version will be without any specific path, the second will be the path I used for the lh.pial, and the third will be for rh.pial.
```
mris_convert/path/to/file name.stl

mris_convert/users/nolanjahn/Desktop/ralfbrain/ralfbrain3/surf/lh.pial lh.stl

mris_convert/users/nolanjahn/Desktop/ralfbrain/ralfbrain3/surf/rh.pial rh.stl 
```

After completing this step, there will be two new files in the surf folder, lh.stl and rh.stl.
Now these files can be opened up in a modeling software to be prepared for printing.

#### Preparing Meshes for 3D printing 
As stated in the overview, to prepare the .stl files for printing a modeling software is needed. I used [Meshlab](http://www.meshlab.net/) for this. 
Once the program is downloaded, the two .stl files can be imported and combined to form one single brain mesh.
Just a note for when using Meshlab, there is no undo button, like on most programs, instead any mistake made will result in importing the files again.


To do this, go to **File** and then select **Import Mesh...**
Choose one of the two files and then it will ask to unify duplicate vertices, select **Ok**
Repeat the process for the other file, and Meshlab will connect the two hemispheres to complete the brian.
After this, there are a few steps to refine the image for printing. 


First, go to **Filters** menu, **mesh layer**, select **flatten Visible Layers**, and hit the **Apply** button.
Now it is ready for printing, however there are additional steps to help the pritning.
Second, go to **Filters**, **Smoothing Fairing and Deformation**, and select **Laplacian Smooth**.
This will make the mesh a little nicer in appearence. 


Finally, the last step, one that I did not personally take, however may be necessary if the 3D printer you use cannot handle the number of vertices of the mesh.
It allows you type in the number of vertices you want, and will merge accordingly.
Go to **Filters, Remeshing Simplification Reconstructiong**, and select **Simplification: Quadratic Edge Collapse Decimation**.
After doing this a box will appear with an area to type in the desired amount of vertices. 
As I said, I did not do this for when I printed my brian image, however if the printer you use cannot handle the amount, it is an easy change. Below is a screenshot of what the completed mesh should look like after these steps are taken. 

![alt text](https://github.com/nomcomm/IndependentStudy_NolanJahn/blob/master/Screen%20Shot%202017-04-23%20at%205.05.02%20PM.png)

#### Printing the Finalized Mesh

Now that there is a finalized single mesh, the mesh can be exported as an .stl file.
The .stl file is ready to be printed on a 3D printer. 
An important thing to remember is that an .stl file is dimensionless, so it is easy to adjust the size to fit the price that you want to spend on your print.

![alt text](https://github.com/nomcomm/IndependentStudy_NolanJahn/blob/master/Brain%20Edit.jpg)
![alt text](https://github.com/nomcomm/IndependentStudy_NolanJahn/blob/master/Brain%202%20Edit.jpg)

