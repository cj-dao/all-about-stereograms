---
layout: default
title: Stereogram Software
parent: How to Make Your Own
nav_order: 3
---

# Stereogram Software
{: .no_toc }

![]({{ '/assets/images/mts-website-icon.png' | relative_url }}){: width="40%" .float-right .ml-4 }

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}

Stereogram software is at the core of stereogram making, as it is what makes your texture 3D. It takes the texture input and applies a series of iterative depth-dependent pixel-shifts based on the provided depth map (see [theory]({% link docs/theory.md %})).

## MTS Software

Unfortunately, there's not a lot of stereogram software out there. 

The go-to website many first-time Magic Eye viewers find is [easystereogrambuilder.com](https://www.easystereogrambuilder.com/). It's free and intuitive, and also provides dozens of pre-made textures and depth maps. However, it's low-resolution, doesn't allow you to change any settings, and most crucially does not support mapped-texture stereograms, which is what the vast majority of high-quality stereograms today are.

3Dimka has links to more professional stereogram software on [hidden-3d.com](https://hidden-3d.com/index.php?id=software). It's somewhat outdated and is Windows-only, and the full version (Stereographic Suite) needed a paid license key the last time I checked; but it offers much more granular control.

The rest of this guide uses [Mapped Texture Stereogram Creator](https://mapped-stereogram-maker.web.app/), a website I coded for the purpose of making MTS design free, accessible, and open source to everyone. 

{: .note }
MTS Creator is still in development. It has bugs, and also is missing some common features like oversampling, which I may add in the future.

## How to Use the Mapped Texture Stereogram Creator

![]({{ '/assets/images/diagram7.png' | relative_url }})

Using MTS Creator is simple:

1. Upload the [texture]({% link docs/tutorial/texture.md %}).
2. Upload the [depth map]({% link docs/tutorial/depth-map.md %}).
3. Optionally upload the [background tile]({% link docs/tutorial/texture.md %}#background-tile).
4. Click `Generate Stereogram`.

Click to see the result:

<details markdown="block">
<summary>Using the Frog Demo texture</summary>

![]({{ '/assets/images/example1.png' | relative_url }})

</details>
<p></p>
<details markdown="block">
<summary>Using the subtle texture</summary>

![]({{ '/assets/images/example2.png' | relative_url }})

If you look closely, you can see that the frog does not have an outline on its back; this is due to the way textures overlap. See [Advanced Techniques]({% link docs/tutorial/advanced.md %}#layering) for more details.


</details>

---

### Using MTS Creator for Classic Stereograms

If you want to create classic un-mapped stereograms, MTS can do that as well. 

Select `Use background as texture` and make sure that you have a background tile uploaded.

<details markdown="block">
<summary>Click to see result</summary>

![]({{ '/assets/images/example3.png' | relative_url }})

</details>

---

### Settings

MTS Creator offers a settings panel to adjust various aspects of the stereogram. Other programs typically have these settings as well, although they may be named differently (e.g. "Depth %" or "Repeats").

#### Max Depth

The further two adjacent repeats are separated, the further back it will appear (see [theory]({% link docs/theory.md %})). `Max Depth` sets the separation value, in pixels, of the furthest parts of the stereogram (corresponding to black on the depth map).

If this value is too high, it may be difficult for viewers to focus far back enough to resolve the stereogram. If it is too low, viewers may focus too far and cause the objects to duplicate.

A good rule of thumb is to adjust the values so that there are ~3-4 repeats in the final image.

#### Min Depth

`Min Depth`, on the other hand, determines the separation value of the closest parts of the stereogram (white on the depth map). Since closer = less separation, this value should always be lower than `Max Depth`.

If this value is too high, it may be difficult for viewers to shift their focus from foreground to background. If it is too low, the stereogram might appear flat or compressed due to lack of depth.

#### Overlap Style

As you may have noticed, the textures in an MTS overlap (again, see [theory]({% link docs/theory.md %}#the-overlap-problem)). What happens when they overlap can be customized.

* The default behavior is `Blend`, which averages out two overlapping tiles (i.e. transparency).
* The other options are `Right-` or `Left-dominant`, which cause whichever texture tile is on the right or left to overwrite the previous tile.

Which option you use depends on the type of texture. If you want all parts of your texture to be visible, it can be a good idea to use `Blend`. Making a classic stereogram, however, requires using either `Right-` or `Left-dominant` modes, so that the repeating background tiles do not blur into one another.

{: .tip}
Not all textures lend themselves well to overlapping. Many professional stereograms you see online, especially animal-themed MTS, have the animal diagonally posed with the head pointed up. This lets key parts of the texture avoid overlapping.

#### Cross View

Enabling `Cross-View` switches the stereogram from wall-eyed to cross-eyed. This essentially inverts the depth.

#### Outlines

[MTS Creator](https://mapped-stereogram-maker.web.app/) has the option to automatically generate [outlines]({% link docs/tutorial/texture.md %}#outlines). This is useful if you're making a classic stereogram, and/or you don't want to go through the trouble of using graphic design software to make a separate texture.

Here is the same classic stereogram as above, but with `Generate Outlines` enabled:

<details markdown="block">
<summary>Click to view</summary>

![]({{ '/assets/images/example4.png' | relative_url }})

</details>

### Demos
