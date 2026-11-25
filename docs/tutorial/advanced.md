---
layout: default
title: Advanced Techniques
parent: How to Make Your Own
nav_order: 4
---

![]({{ '/assets/images/tutorial_layer_1.png' | relative_url }}){: width="55%" .float-right .ml-4 .mt-3 }

# Advanced Techniques
{: .no_toc }

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}

Successfully encoding depth into a pattern is only part of the way there. Almost every professional-grade stereogram you see online has gone through several steps of post-processing and compositing to produce the final result. 

This section discusses some of those techniques, as well as new techniques that I have used to push MTS beyond simple depth encoding.

## Layering

Layering is the fundamental process of making multiple stereograms with different textures and depth maps and stacking them on top of each other using graphic design software. It is the most reliable way of making [outlines]({% link docs/tutorial/texture.md %}#outlines), for instance.

For example, I drew an outline-only frog and used it as a transparent texture to get an outline-only stereogram:

![]({{ '/assets/images/diagram8.png' | relative_url }}){: width="90%"}

Then, I layered that on top of the plain, un-mapped stereogram:

![]({{ '/assets/images/example6.png' | relative_url }}){: width="90%"}

{: .tip}
When tracing the depth map, make sure to draw outlines *inside* the object. Outlining the exterior of an object's edge means the lines won't get picked up by the depth.

You can layer more than just outlines. Here, a stereogram using the Blender-rendered default frog texture has been reduced to 40% opacity and layered on top:

![]({{ '/assets/images/example7.png' | relative_url }}){: width="90%"}

{: .tip}
Each individual stereogram should be rendered using the same depth settings; otherwise, the layers will be mis-matched.

## Translucent Objects

In the above example, the same depth map was used for the base, the outline, and the frog texture. Using the same depth map is not required at all—in fact, you can layer a different stereogram with a different depth map to create translucent objects.

In the next example, there are two depth maps in play: one without the mirror surface, and one with. 

![]({{ '/assets/images/tutorial_mirror_depth_nm.png' | relative_url }}){: width="35%"}
![]({{ '/assets/images/tutorial_mirror_depth_m.png' | relative_url }}){: width="35%"}

Each depth map was paired with a different texture—one for the solid objects, and one for the translucent object.

![]({{ '/assets/images/tutorial_mirror_stereo_nm.png' | relative_url }}){: width="35%"}
![]({{ '/assets/images/tutorial_mirror_stereo_m.png' | relative_url }}){: width="35%"}

The two were then layered on top to create the following:

![]({{ '/assets/images/stereo1.png' | relative_url }}){: width="70%"}

{: .tip}
Alpha-mask gradients can be applied to layers, not just global opacity. Gradients look best when vertical, since horizontal transitions can mess with tile convergence. 

![]({{ '/assets/images/stereo2.png' | relative_url }}){: width="55%" .float-right .ml-4 .mt-3 .m-4 }

## Coloring-Book Style

A different MTS paradigm that results in an elegant, hand-drawn look is the "coloring-book" style, inspired by 3Dimka, who made many stereograms in that style.

This style primarily relies on two things: lines and color, avoiding the occasional noise and distortion you might see in traditional MTS methods.

This is especially apparent in the image below by [eyefind3d](https://www.eyefind3d.com/):

{: style="clear: both;" }

[![]({{ '/assets/images/eyefind3d_1.webp' | relative_url }}){: width="40%" .float-left .mr-4 .mb-4 }](https://www.eyefind3d.com/)

They are relatively simple conceptually but labor-intensive to make.

Just as with the Frog, you start by making an outline-only stereogram, which will contain gaps (see [theory]({% link docs/theory.md %}#the-overlap-problem)):

![]({{ '/assets/images/wizard_stereo_1.png' | relative_url }}){: width="42%"}

One way of removing the gaps is by completing the lines manually in order to form closed-loop shapes, then flood-filling in the shapes with different colors:

![]({{ '/assets/images/wizard_stereo_2.png' | relative_url }}){: width="42%" .mr-8}
![]({{ '/assets/images/wizard_stereo_3.png' | relative_url }}){: width="42%"}



## Overlap Gap-Filling
{: style="clear: both;" }
