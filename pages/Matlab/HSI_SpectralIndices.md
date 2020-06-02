---
title: Spectroscopic and Remote Sensing indices
description: Estimation of several chemical parameters based on literature indices. Some were created from spectroscopic and hyperspectral devices, others from remote sensing (multi- and hyper-spectral sensors).
permalink: HSI_SpectralIndices.html
sidebar: Matlab_sidebar
---

# Toolbox
The mandatory data to use this toolbox are a hyperspectral image (M), the corresponding RGB image (RGB), depth (dm), and wavelength (wl). Then, the toolbox will find with wl if it is VNIR or SWIR data. Then, it will propose to you all the possible indices that you can choose to estimate. Finally, an image correlation between the selected indices is made at the end.

## VNIR example
Here we can see an example with lamination. White laminae present higher values that correspond to the diatoms in spring and summer. Whereas dark laminae corresponding to winter have the lowest values.

{% include image.html file="Chloro.jpg" %}

The correlation matrix shows that even if 18 indices are related to chlorophylls and 3 to oxides, they don't have the same trend, so it must be chosen wisely.

{% include image.html file="Corr_VNIR_Indice.jpg" %}

## SWIR example

The reflectance at 1935 nm highlights the moisture abundance, with higher values corresponding to low moisture abundance and inversely. So light deposits seem to have lower moisture than dark ones.

{% include image.html file="Moisture.jpg" %}

The correlation matrix shows that several indices are highly correlated.

{% include image.html file="Corr_SWIR_Indice.jpg" %}