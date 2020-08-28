---
title: Introduction
description: Introduction
permalink: Introduction_HSI.html
---

## Hyperspectral representation
A conventional RGB image is represented as three-dimensional data with two spatial dimensions and one dimension containing the 3 channels R, G, B. These channels correspond normal integration of wavelengths around 611nm, 549nm and 464nm respectively (CIE1999). For a hyperspectral image, we find these two spatial dimensions, to which is added a spectral dimension composed of multiple channels corresponding to wavelengths of the electromagnetic spectrum, which is why it is represented by a data cube. 

Spectroscopic sensors can use different ranges of the electromagnetic spectrum (ultraviolet, visible, infrared, X-rays). They record physical, chemical and biological information about the samples being analysed, known as structural properties.

Thus hyperspectral imaging benefits from the advantages of: 
<ul>
<li>imaging with data spatialization and structure visualization, </li>
<li> as well as spectroscopy with the biological-physical-chemical characteristic of the sample properties. </li>
</ul>

<center>
{% include image.html file="HSI.jpg" %}
</center>

```markdown
CIE (1999) IEC 61966-2-1:1999: Multimedia Systems and Equipment - Colour Measurement and Management - Part 2-1: Colour Management - Default RGB Colour Space - SRGB
```

## The electromagnetic spectrum

The electromagnetic spectrum is divided into several spectral ranges according to the modes of interaction between radiation and matter (molecules, atoms, electrons). Banwell proposes to divide it into seven main areas which are synthesized in the figure below (Banwell1994):
<ul>
<li> Radio waves can interact with the spin of particles by inverting them, for example with atomic nuclei or single electrons. The study of these two phenomena is called nuclear magnetic resonance (NMR), electron spin resonance (ESR) or electron paramagnetic resonance (EPR) respectively. </li>
<li> Microwaves are capable of influencing the rotational speed of molecules, which is why his study is called rotational spectroscopy. </li>
<li> Infrared (IR) is concerned with the vibration of molecular bonds, hence the name vibrational spectroscopy. Two main groups exist in this area, infrared spectroscopy and Raman spectroscopy. The first is also subdivided into three areas according to ISO 20473 (long- or far-, mid- and near-infrared, ISO2007), or commonly subdivided into five areas (far-, long wave-, mid wave-, short wave-, near-infrared). </li>
<li> The ultraviolet and the visible (UV-visible) excite the valence (external) electrons of atoms or molecules for the transitions of the electron states, we speak of electron spectroscopy. Two main methods exist in this range, UV-Visible spectroscopy and UV-Visible fluorescence spectroscopy (EEM, with laser excitation LIF , or resolved time TRES). </li>
<li> X-rays can also be used for electron spectroscopy, but only at the core electrons or near the atomic nucleus. This range can also be divided into three main methods, X-ray absorption or diffraction (XRD) spectroscopy and X-ray fluorescence spectroscopy. </li>
<li> Gamma rays affect energy transitions within the nuclei of atoms. It is also represented by two main methods, gamma spectrometry and Mössbauer spectrometry. </li>
</ul>

<center>
{% include image.html file="Spectre-electromagnetique-en-energie-frequence-longueur-et-nombre-donde-Les-modes.png" caption="Schematic electromagnetic spectrum proposed by Banwell" %}
</center>

```markdown
Banwell, C.N., McCash, E.M. (1994) Fundamentals of Molecular Spectroscopy McGraw-Hill

ISO (2007) ISO 20473:2007 - Optics and Photonics — Spectral Bands
```

## Spectroscopic acquisition method
The type of acquisition is also specific to the sensor and the problem to be solved :
<ul>
<li> discrete spot analyses give an overall idea of the composition of the sample, </li>
<li> a continuous analysis on a line allows to have a trend on the variability of the sample along this axis, </li>
<li> a mapping by performing a point-by-point analysis on the whole sample allows to know the variability in both directions of the sample, </li>
<li> an image that is obtained by acquiring a line to obtain, as before, the overall variability of the sample. </li>
</ul>

## Hyperspectral acquisition method
As we have just seen, mapping by multiple spectroscopic acquisitions can allow to obtain a hyperspectral image, this method is called point-scan or whiskbroom. Most often the sample will move in both directions and the sensor is fixed to estimate the hyperspectral image of the whole sample. It allows a high spatial resolution for a sample of variable size, but requires an acquisition time that is often important. 

Two other methods exist to obtain a hyperspectral image:
<ul>
<li> The acquisition of a line allowing to obtain several pixels on a spatial dimension of the sample is called the pushbroom method. Then, most often the sample moves in a linear direction and the sensor is fixed, thus acquiring multiple lines that will create the hyperspectral image. This method is fast, easy to automate, but is limited with the spatial resolution of one line. </li>
<li> The last method consists in acquiring an image of the sample at each wavelength, it is called plan-scan. Thus the sensor and the sample are fixed. This method is very fast, but is spatially limited as the whole is fixed, and thus the spatial resolution is also impacted. </li>
</ul>

In the laboratory these three acquisition methods can be used, but in the field or airborne the pushbroom method is preferred.

### Analysis protocol used in the laboratory

<iframe src="https://www.protocols.io/widgets/doi?uri=null" style="width: 520px; height: 300px; border: 1px solid transparent;"></iframe>

```markdown
Butz, C., Grosjean, M., Fischer, D., Wunderle, S., Tylmann, W., Rein, B. (2015) Hyperspectral imaging spectroscopy: a promising method for the biogeochemical analysis of lake sediments. Journal of Applied Remote Sensing 9: 1–20

Van Exem, A. (2018) Reconstructions de Changements Environnementaux Dans Les Archives Lacustres Par Imagerie Hyperspectrale.
```