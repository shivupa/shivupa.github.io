---
layout: post
title: Making Publication Quality Images With VMD
modified:
categories: blog
excerpt:
tags: []
image:
  feature:
date: 2016-01-10T09:42:38-05:00
---
I am a bit obsessive when it comes to the quality of images I produce. I have two preferences when it comes to an image:  
1. I always try to use vector images(SVG)
2. If I can't use a vector, I use a 4k resolution (PNG)
Rendering an image from VMD falls into the second category, but without setting it up correctly just rendering at 4k doesn't look very great. Proper rendering in VMD requires the use of a ray tracing engine. Ray tracing is essentially a method that simulates the path of light in a scene and the interactions of these paths with the materials in the scene. I'll provide an example here of rendering a water molecule.

Steps:
1. Load a PDB and set the axes off and the background to white
![alt text](making-publication-quality-images-with-vmd/Step1.png "Step1")

2. Choose the orthographic view
![alt text](making-publication-quality-images-with-vmd/Step2.png "Step2")

3. Navigate to the "Display Settings" options
![alt text](making-publication-quality-images-with-vmd/Step3.png "Step3")

4. Turn "Shadows" and "Ambient Occlusion" on
![alt text](making-publication-quality-images-with-vmd/Step4.png "Step4")

5. Navigate to the "Materials" options
![alt text](making-publication-quality-images-with-vmd/Step5.png "Step5")

6. Duplicate a material so you can modify the settings. Here I duplicated and modified the "AOChalky" material
![alt text](making-publication-quality-images-with-vmd/Step6.png "Step6")

7. Navigate to the "Render" options
![alt text](making-publication-quality-images-with-vmd/Step7.png "Step7")

8. Select the tachyon ray tracing option
![alt text](making-publication-quality-images-with-vmd/Step8.png "Step8")

9. Resize the display window using the console because you can make it bigger than the size of your screen this way. This may cause the view window to go blank. Don't panic that's fine. Render using the tachyon setting. This may take some time.
![alt text](making-publication-quality-images-with-vmd/Step9.png "Step9")

10. Save the visualization state for future renders
![alt text](making-publication-quality-images-with-vmd/Step10.png "Step10")

You can see the fruits of the render below. This took about ten minutes start to finish but resulted in a fairly polished product. If I were actually using this render for anything serious I would fix the "washed out" look that it currently has.
![alt text](making-publication-quality-images-with-vmd/waterquickrender.png "Water Quick Render")
Here are a few of my better renders:
![alt text](making-publication-quality-images-with-vmd/WaterCluster.png "Water Cluster")
![alt text](making-publication-quality-images-with-vmd/WaterDimer.png "Water Dimer")
![alt text](making-publication-quality-images-with-vmd/wateroverlay.png "Water Overlay")
![alt text](making-publication-quality-images-with-vmd/H2O_density.png "Water Density")
![alt text](making-publication-quality-images-with-vmd/solvation.png "Solvation")
![alt text](making-publication-quality-images-with-vmd/folding.png "Folding")
