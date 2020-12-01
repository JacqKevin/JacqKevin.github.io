---
title: Hyperspectral image visualization
description: Toolbox to visualize an hyperspectral image on the spatial and/or spectral dimension.
permalink: HSI_Visualize.html
sidebar: Matlab_sidebar
---

# Visualization Toolbox
The mandatory data to use this toolbox are a hyperspectral image (M), the corresponding RGB image (RGB), depth (dm), and wavelength (wl). Then, the toolbox will estimate continuum, first derivative of the HSI.

<a href="https://github.com/JacqKevin/HSI_Visualization">
  HSI_Visualization repository
</a>

## Images
Hyperspectral images can be reduced to 3 channels to create pseudo-RGB or composite or false colour images:
* VNIR - RGB (Red Green Blue): 640 nm – 545 nm – 460 nm
* VNIR - CIR (Color InfraRed): 860 nm – 650 nm – 555 nm
* VNIR - NIR (Near InfraRed): 900 nm – 800 nm – 700 nm
* SWIR: 2162 nm – 2199 nm – 2349nm 
```markdown
Speta, M., Gingras, M.K., Rivard, B., 2016. Shortwave Infrared Hyperspectral Imaging: A Novel Method For Enhancing the Visibility of Sedimentary And Biogenic Features In Oil-Saturated Core. J. Sediment. Res. 86, 830–842. https://doi.org/10.2110/jsr.2016.54
```
* SWIR - Hydrocarbon: 1722 nm – 1760 nm – 2311 nm 
```markdown
Scafutto, R.D.P.M., de Souza Filho, C.R., Rivard, B., 2016. Characterization of mineral substrates impregnated with crude oils using proximal infrared hyperspectral imaging. Remote Sens. Environ. 179, 116–130. https://doi.org/10.1016/j.rse.2016.03.033
```
* SWIR - Hydrocarbon: 1722 nm – 2311 nm – 2349 nm 
```markdown
Scafutto, R.D.P.M., de Souza Filho, C.R., Rivard, B., 2016. Characterization of mineral substrates impregnated with crude oils using proximal infrared hyperspectral imaging. Remote Sens. Environ. 179, 116–130. https://doi.org/10.1016/j.rse.2016.03.033
```


{% include image.html file="HSIvisualize_Image.jpg" %}

-> examples soon

## Abberant pixels

{% include image.html file="HSIvisualize_Abberant.jpg" %}

## Median and standard deviation spectra

{% include image.html file="HSIvisualize_MedStdSpectra.jpg" %}

## Median raw spectra

{% include image.html file="HSIvisualize_Raw.jpg" %}

{% include image.html file="HSIvisualize_Raw3D.jpg" %}

## Median continuum removed spectra

{% include image.html file="HSIvisualize_ContinuumRemoved.jpg" %}

{% include image.html file="HSIvisualize_ContinuumRemoved3D.jpg" %}

```markdown
Clark, R.N. (1999) Spectroscopy of Rocks and Minerals, and Principles of Spectroscopy. In: Rencz, A. N. (ed.) Remote Sensing for the Earth Sciences: Manual of Remote Sensing, 3 Ed. John Wiley & Sons, Inc., 1–50.
```

## Median continuum spectra

{% include image.html file="HSIvisualize_Continuum.jpg" %}

{% include image.html file="HSIvisualize_Continuum3D.jpg" %}

## Median first derivative spectra

{% include image.html file="HSIvisualize_FDS.jpg" %}

{% include image.html file="HSIvisualize_FDS3D.jpg" %}

```markdown
Savitzky, A., Golay, M.J.E. (1964) Smoothing and Differentiation of Data by Simplified Least Squares Procedures. Analytical Chemistry 36: 1627–1639
```

## Minimum Noise Fraction image composite

{% include image.html file="HSIvisualize_MNF.jpg" %}

```markdown
Green, A.A., Berman, M., Switzer, P., Craig, M.D. (1988) A Transformation for Ordering Multispectral Data in Terms of Image Quality with Implications for Noise Removal. IEEE Transactions on Geoscience and Remote Sensing 26: 65–74
```

## Wavelength correlations

{% include image.html file="HSIvisualize_WlCorr.jpg" %}

## Clustering

{% include image.html file="HSIvisualize_Cluster.jpg" %}

## Q7/4 vs L* diagram

{% include image.html file="HSIvisualize_Q74.jpg" %}

{% include image.html file="HSIvisualize_Q74im.jpg" %}

```markdown
Debret, M., Sebag, D., Desmet, M., Balsam, W., Copard, Y., Mourier, B., Susperrigui, A.-S., Arnaud, F., Bentaleb, I., Chapron, E., Lallier-Vergès, E., Winiarski, T., 2011. Spectrocolorimetric interpretation of sedimentary dynamics: The new “Q7/4 diagram.” Earth-Science Rev. 109, 1–19. https://doi.org/10.1016/j.earscirev.2011.07.002
```