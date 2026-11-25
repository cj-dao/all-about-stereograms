---
layout: default
title: Texture
parent: How to Make Your Own
nav_order: 2
---

![]({{ '/assets/images/tutorial_frog_texture.png' | relative_url }}){: width="40%" .float-right .ml-4 }

# How to Make a Texture
{: .no_toc }

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}

The texture comprises the actual patterns and colors that serve as the horizontally-repeating vessel encoding the 3D shapes provided by your depth map. It can be anything from abstract floral patterns to realistic artwork that directly matches your object.

How you make a texture depends on whether you want a [classic or mapped-texture stereogram]({% link index.md %}#classic-unmapped-vs-mapped-texture-stereograms-mts). If you want to make a classic stereogram, you can skip straight to choosing a [background tile](#background-tile).

If you are making an MTS, I recommend that you make at least two textures: one for the object, and one for the background.

## Software

Any art software, Photoshop-like tool, MS Paint, or even a photo of your neighbor's dog can be used to make a texture. I use [Affinity](https://www.affinity.studio/download) and Blender together to design textures, or browse stock photos from the internet; anything works.

## Foreground Texture

![]({{ '/assets/images/gif1.gif' | relative_url }}){: width="40%" .float-right .mr-4 }

There's technically no difference between a foreground vs. background texture, and you can use a single image for both. However, especially for mapped-texture stereograms, it's advisable to make the foreground a different pattern from the background to make it stand out more. Additionally, because textures will overlap with themselves (see [theory]({% link docs/theory.md %})), textures should involve only small parts of the image and not span the entire width of the stereogram.

The best textures are transparent PNG images that align with your depth map. For example, the Frog Demo depth map and texture sit perfectly on top of one another, and the background of the frog is transparent.

The [template]({% link docs/tutorial/depth-map.md %}#software) files I provided have built-in functionality to convert whatever 3D model you're using into a color-rendered image, provided that the model includes its own textures. 

![]({{ '/assets/images/diagram6.png' | relative_url }}){: width="20%" .float-left .mr-4 .mb-6 }

{: .note }
If you're following along with the Frog Demo, un-toggle the `Switch` checkbox in the `Nodes` window at the bottom of the screen, press `Z` then `R` to preview the full-color textured render, then use `F12` to render the texture. You should get an image similar to the example one at the top of this page.

### Subtle Textures
{: style="clear: both;" }

Sometimes, you may not want your 3D object to be so conspicuous, but you may still want to include subtle texture hints for the viewer, like outlines, animal eyes, or ambient edge shadows/highlights. In that case, you can use your graphic design software of choice to create a more subtle texture.

Here's an example:

![]({{ '/assets/images/tutorial_frog_texture_2.png' | relative_url }}){: width="50%" }

As you can see, I've replaced the shape of the frog with a green paisley pattern and kept the eye detail. 

### Outlines

One popular way many stereogram artists subtly make their object stand out more from the background without making it too obvious is by using outlines. If you look closely, you can see that I've added a slight green outline to the frog.

## Background Tile

![]({{ '/assets/images/bgtile1.jpg' | relative_url }}){: width="30%" .float-right .ml-4 .mb-8}

For an MTS, if your texture has transparency, you will probably want a background pattern that will sit behind your primary texture and fill in the gaps and empty space.

If you're making a classic, unmapped stereogram, this background tile will form the texture of your entire stereogram, including both foreground and background. 

Similarly to the foreground texture, the background tile can be anything. In the case of making [subtle textures]({% link docs/tutorial/texture.md %}#subtle-textures), you can make your background tile and foreground texture to use very similar colors, so that they blend in with one another.

Here is the paisley pattern I used for the Frog that I will use for the background as well:

<p></p>
{: style="clear: both;" }
