# Project 1: MD Simulations of RNA Acridine:G-quadruplexes

Note: You are strongly encouraged to work together.  However, each person is responsible for producing and submitting their own work.

Overview: We will perform CHARMM MD simulations with NAMD of a RNA G-quadruplex in explicit solvent on the DEAC cluster.  Using the production run of the simulation, we will use VMD and other programs to visualize trajectories and perform analyses on them.  

## Part 1: Visualizing Biomolecular Structures Using VMD

Website References: [ VMD Tutorial ](http://www.ks.uiuc.edu/Training/Tutorials/vmd/tutorial-html/index.html)

VMD is a powerful program that can be used to render biomolecular images and MD simulation trajectories and perform basic analyses on them. To get your feet wet and get you familiar with the many, many features of VMD, you will learn to load a biomolecule, change its representations, and render it using Povray.

1. Download the latest version of VMD from their [ website ](https://www.ks.uiuc.edu/Development/Download/download.cgi?PackageName=VMD). Alternatively, you can log into the DEAC HPC Cluster and type the following:
```
module load apps/vmd/1.9.4a57
```
Note: It is much slower to run VMD on the DEAC HPC Cluster because the graphics needs to be transferred across a network instead of being rendered directly on your laptop.

2. Run VMD by typing “vmd” in your Terminal or Powershell program. There will be two windows that open: 1) VMD Main and 2) OpenGL Display. Open up and load a biomolecule by going to the “VMD Main” window and selecting File --> New Molecule… . A new window titled “Molecule File Browser” will open.

![image](https://github.com/user-attachments/assets/dca126fb-6736-443a-9a6c-1754b004335a)
![image](https://github.com/user-attachments/assets/8f785b34-9e38-4987-a344-ea451fe22347)

3. We will start by selecting a protein structure that VMD will download directly from the PDB onto your browser. For this example, we will use “2kwf”, which is the PDB ID for a KREB binding protein. In the “Filename:” box, type in “2kwf” and press the “Load” button. In the “OpenGL Display” window, the protein structure will appear.

![image](https://github.com/user-attachments/assets/d71b110d-7f95-4803-9241-5b782323f290)

You are now done with the “Molecule File Browser” window and you may close it. 

4. Move your mouse over to the OpenGL Display window, press the left trackpad button, and move your finger on the trackpad. You should be able to rotate the molecule.

5. You can also move the biomolecule across the screen by going back to the “VMD Main” window and selecting Mouse --> Translate Mode then using the trackpad as you did before for rotation. Or you can enlarge or shrink the biomolecule by selecting Mouse --> Scale Mode then using the trackpad to move left (shrink) or right (enlarge).

![image](https://github.com/user-attachments/assets/05ca878c-407f-411a-9b9a-19085c80d0af)

__Pro Tip:__
To reset your biomolecule structure at any time, in the “VMD Main” window select Display --> Reset View.

__Pro Tip:__
If you do not like the axes on the lower left hand corner, in the “VMD Main” window select Display --> Axes --> Off

__Pro Tip:__
If you want to change the background color to white, in the “VMD Main” window select Graphics -> Colors… . A “Color Controls” window will open. In the Categories box select “Display”, in the Names box select “Background”, and in the Colors box select “8 White”. For some figures, white is a better background color, for others black is. 

__Pro Tip:__
By default, VMD has a feature that brightens the parts of the biomolecule closest to the screen and adds shadows to those parts that are further away. If you want to remove this feature, in the “VMD Main” window select Display --> Depth Cueing to remove the checkbox.

6. In the “VMD Main” window, select Graphics --> Representations… . A “Graphical Representation” window will open.

![image](https://github.com/user-attachments/assets/94581ff7-88b8-41fb-b276-d9ce42508e8a)
![image](https://github.com/user-attachments/assets/d14d88c6-0d8f-475e-a0b3-24a8c0a16ce2)

The current biomolecule is listed in the “Selected Molecule” box. Although we will not do this here, VMD can read in multiple biomolecule structure files at the same time. 

In the “Draw Styles” tab, we can change the coloring schemes and representations of the biomolecule using the “Coloring Method” and “Drawing Method” dropbox menus. From the Drawing Methods dropbox menu, here are the results of the VDW, Licorice, Tube, NewCartoon, and Surf representations:

![image](https://github.com/user-attachments/assets/b1c21fb0-5ba0-4acc-be7e-4cca97306189)
![image](https://github.com/user-attachments/assets/8957029e-ab05-4ced-ab64-335beef282a2)
![image](https://github.com/user-attachments/assets/77c86c0b-9652-4efe-82b5-245e5380d104)
![image](https://github.com/user-attachments/assets/f3d6e89d-9e65-4a26-aa14-aa69736265f1)
![image](https://github.com/user-attachments/assets/2b852084-4d96-40ea-ae71-367afdff2668)

Using the NewCartoon representation, from the Coloring Method dropbox, here are the results of the ResName, ResType, Chain, Secondary Structure, ColorID (4), and Index:

![image](https://github.com/user-attachments/assets/944d4374-8c15-4971-815d-c41045e3f4f3)
![image](https://github.com/user-attachments/assets/d2e48807-6a3e-4624-8b8f-9fd2afbbc182)
![image](https://github.com/user-attachments/assets/8e2c9e27-dc7c-4d02-aa84-e42e12703834)
![image](https://github.com/user-attachments/assets/d0c1694a-59d2-4be3-bd88-142dddfc7cd8)
![image](https://github.com/user-attachments/assets/a7681465-cc61-4054-85c1-74c5bb698596)
![image](https://github.com/user-attachments/assets/2cd39f38-647b-48f6-a349-c3b8b046d70b)

7. In the Selections tab are tables of keywords that you can use to select only a portion of the protein to display. There are a lot of options that we cannot cover here. Here are the results of a few selections that you can type in the “Selected Atoms” with results:

chain A

![image](https://github.com/user-attachments/assets/d4de98df-4a46-43f1-971c-73666a31a20b)

(chain A) and (resid 12 to 26)

![image](https://github.com/user-attachments/assets/2262e303-d48d-4717-b58f-da50cf716ea9)

8. The "Create Rep" button can be used to create multiple representations that result in a mixture of selections with different styles and colors all displayed at the same time. Here is the result with the following representations:

Representation 1: Selected Atoms: chain A,  Coloring Method: ResType, and Drawing Method: VDW
Representation 2: Selected Atoms: chain B, Coloring Method: ColorID (4), and Drawing Method: NewCartoon 

![image](https://github.com/user-attachments/assets/13b09605-8477-4844-8de9-a827edc5ce1a)

8. To save your work, in the “VMD Main” window, select File --> Save Visualization State… . After this, you can exit VMD and come back to your work later. To load your saved work, in the “VMD Main” window, select File --> Load Visualization State… .

![image](https://github.com/user-attachments/assets/2c124515-5a9a-4c2a-b6bc-a7bd312dd6da)
![image](https://github.com/user-attachments/assets/8f8278ec-e17d-4043-a7ae-908415af28d5)

9. Edit this README.md file to post your rendered structure of the protein below. Your rendered image should not look exactly like mine, and I instead encourage you to turn in a more creative looking image. Repeat this exercise above with the PDB ID 1kf1 and turn in a rendered image of the RNA below.


VMD Rendered Protein (PDB ID: 2KWF) Image here:


VMD Rendered RNA (PDB ID: 1KF1) Image here:



