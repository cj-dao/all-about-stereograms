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

## Foreground Texture

### Handling Texture Overlapping

### Subtle Textures

### Outlines

## Background Tile

For an MTS, if your texture has transparency, you will probably want a background pattern that will sit behind your primary texture and fill in the gaps and empty space.

If you're making a classic, unmapped stereogram, this background tile will form the texture of your entire stereogram, including both foreground and background. 
