---
layout: post
section-type: post
title: Documentation on the Aorta Segmentation project
category: documentation
tags: [ 'medical imaging' ]
---

Between August and December 2016 I worked on my computing engineering undergraduate thesis on medical images analysis in order to develop a tool for
the Segmentation of the aorta artery for applications such as the
quantification of the elasticity of the aorta artery and
quantification of the aorta artery calcifications under the direction
of prof. Marcela Hernandez.
The work has been done in colaboration with prof. Leonardo Florez, from Pontificia
 Universidad Javeriana (Bogota, Colombia), and Eduardo Davila, from CREATIS Laboratory
  (Lyon, France).

Some of the scripts and documentation can be found in this <a href="https://github.com/sercharpak/Proyecto_de_grado"> repository</a>.

This project is based on previous solutions to this problem developped at CREATIS Laboratory (Lyon, France).
Previous implementations were developed by Eduardo Dávila for users in the CREATIS Laboratory environment in the <a href="https://www.creatis.insa-lyon.fr/site/en/CreaTools_home.html"> CreaTools</a>
toolbox. In one project the goal was to obtain a visualization of the deformation of the aorta artery wall. In an other project the objective was to retrieve segmentation of the calcifications around the aorta artery.

<h2> Previous projects</h2>
<!---
<h3>Aorta Wall Deformation project</h3>

<p>The main developer of this project was Eduardo Dávila. The
goal of the project was to visualize and quantify the deformation of the aorta artery wall between the systole and diastole phases.  </p>
<p>A summary of the project is the following <b>diagram</b>. Download the  <a href="https://github.com/sercharpak/Proyecto_de_grado/raw/master/docs/old_project_AortaWall.gv"> .DOT source here</a>.</p>
<img src="https://github.com/sercharpak/Proyecto_de_grado/raw/master/docs/old_project_AortaWall.png"  >
--->
<h3>Calcifications Segmentation project</h3>
<p>The main developer of this project was Eduardo Dávila. The
goal of the project was to visualize and confirm the calcifications around the aorta artery. </p>
<p>A summary of the project is the following <b>diagram</b>. Download the  <a href="https://github.com/sercharpak/Proyecto_de_grado/raw/master/docs/old_project_SegCall.gv"> .DOT source here</a>.</p>
<img src="https://github.com/sercharpak/Proyecto_de_grado/raw/master/docs/old_project_SegCall.png"  >

<h2> Our solution</h2>
<p>The segmentation algorithm was implemented in two steps. The first, the axis extraction, is
implemented in the cpPlugins framework developed by Leonardo Flórez, itself written in C++
and using the external image processing libraries ITK and VTK versions 4.10 and 7.0
respectively. The second step is the extraction of the aorta with the axis as an input. It is
implemented in the CreaTools framework. </p>
<p>A summary of the project is the following <b>diagram</b>. Download the  <a href="https://github.com/sercharpak/Proyecto_de_grado/raw/master/docs/new_project.gv"> .DOT source here</a>.</p>
<img src="https://github.com/sercharpak/Proyecto_de_grado/raw/master/docs/new_project.png"  >
