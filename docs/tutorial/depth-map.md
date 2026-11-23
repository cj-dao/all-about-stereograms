---
layout: default
title: Depth Map
parent: How to Make Your Own
nav_order: 1
---

![]({{ '/assets/images/depth1.png' | relative_url }}){: width="40%" .float-right .ml-4 }

# How to Make Depth Maps
{: .no_toc }

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## 3D Modeling

Depth maps rely on highly precise grayscale values; as such, the best way to create them is with 3D modeling software. Creating gradients in Photoshop or using AI to make depth maps directly will probably result in wonky-looking final results.

Unfortunately, 3D modeling can have a somewhat steep learning curve. You can find many depth maps available online, or on forums like [Reddit](https://www.reddit.com/r/depthMaps/).

### Software

I use [Blender](https://www.blender.org/) to make my depth maps; it's free, open source, and has hundreds of beginner tutorials on YouTube, such as [this one](https://www.youtube.com/watch?v=peSv5IT5Ve4).

You can download this template Blender file that already has the correct settings to render depth maps. Or, you can download the 2nd file, which contains a ready-to-use demo for rendering a depth map as well as a matching texture.

<a href="{{ '/assets/other/depth_tutorial_1.blend' | relative_url }}" class="btn btn-primary" download>Download .blend Template</a> <br>
<a href="{{ '/assets/other/depth_tutorial_2.blend' | relative_url }}" class="btn btn-green" download>Download Frog Demo</a>

### Importing files

If you want to avoid modeling your own depth maps, you can find many free models available on sites like [Sketchfab](https://sketchfab.com). Once downloaded and unzipped, you can import them into the template Blender file with `File > Import`.

### Setup

If you already have some experience in Blender and want to integrate this into your own workflow, here is the setup I use to make depth maps.

![]({{ '/assets/images/diagram2.png' | relative_url }}){: width="85%" }

These nodes take the raw, linear depth output and transform it into an inverse curve mapped to the camera's clip start/end, allowing you to render depth maps with perspective _and_ preserve the depth accuracy. Other setups require an orthographic perspective.

{: .note }
For proper color formatting and best depth fidelity, ensure you have the proper output settings:
![]({{ '/assets/images/diagram4.png' | relative_url }}){: width="20%" }

### Adjustment

![]({{ '/assets/images/diagram3.png' | relative_url }}){: width="30%" .float-right .ml-4 }

Once you've imported or designed your 3D model, move, rotate, or scale it so that it fits within the camera. You can change the aspect ratio on the right sidebar under `Output > Format > Resolution`.

To make sure that your 3D scene fits within the depth range (i.e. the closest objects are completely white, and the background is completely dark), select the `Camera` object and adjust `Clip Start` and `End` under `Data` (see screenshot ->). You can preview the depth render in the viewport by pressing `Z` then `R`.

### Exporting

Export the image using `F12` or by pressing `Render` > `Render Image`.

## General Tips

The clarity of the final stereogram depends a lot on the composition of the depth map. Generally, you want a simple object that can be recognized by its silhouette alone; objects with a lot of thin spikes or fine detail will probably not produce clear results.

Additionally, try to avoid overlapping objects, especially when one object is much closer to the camera; because of the way stereogram algorithms displace patterns to create depth, overlapping depth planes can create pattern "gaps." See [Advanced Techniques]({% link docs/tutorial/advanced.md %}) for more details.

