---
title: Preprocessing
description: Preprocessing
permalink: Preprocessing_HSI.html
---

## Sensor Normalization

Generally, the hyperspectral image unity is reflectance (R). According to Beer-Lambert law, the chemical concentration of a compound is related to the absorbance (A). Thus, the hyperspectral image can be converted into pseudo-absorbance with the formula: A=log(1/R).

## Conversion

Hyperspectral in refelctance

## Spectral preprocessing

{% include image.html file="Preprocessing.jpg" %}

In this toolbox, four main preprocessing are used, also nine combinations of them. Thus, thirteen preprocessing and the raw data are compared to find an optimal one. They allow to reduce noise and highlight relevant spectral information to predict the interest variable(s).

Detrending is used to remove the baseline. Multiplicative Scatter Correction (MSC) and Standard Normal Variate (SNV) are used to correct the spectra from light scattering. The Savitzky–Golay filter is used to derivate the spectra and to reduce additive effects (baseline offset and slope).

```markdown
Vidal, M., Amigo, J. M. (2012) Pre-processing of hyperspectral images. Essential steps before image analysis. Chemometrics and Intelligent Laboratory Systems 117: 138–148

Rinnan, Å., Berg, F. van den, Engelsen, S.B. (2009) Review of the most common preprocessing techniques for near-infrared spectra. TrAC Trends in Analytical Chemistry 28: 1201–1222

Barnes, R.J., Dhanoa, M.S., Lister, S.J. (1989) Standard Normal Variate Transformation and De-Trending of Near-Infrared Diffuse Reflectance Spectra. Applied Spectroscopy 43: 772–777

Savitzky, A., Golay, M.J.E. (1964) Smoothing and Differentiation of Data by Simplified Least Squares Procedures. Analytical Chemistry 36: 1627–1639
```

## Spectral normalization
Second spectral processing can be used to normalized the signal base on the mean and standard deviation of the hyperspectral image. Thus, centering or autoscaling can be chosen by the user.

## Data reduction

On peut les réduire pour accélérer le temps de calcul, cela est souvent réalisé avec une ACP ou une MNF afin d'enlever les variables redondantes et corrélées (colinéaires). Ou encore en sélectionnant des longueurs d'onde discriminantes pour une variable à prédire avec des algorithmes de sélection de variables. 

## Spatial preprocessing

Comme dans le cas de la création d'un modèle multivarié, les images nécessitent un ou des prétraitements pour réduire le bruit ou mettre en avant les structures, comme des normalisations, lissages, dérivées ou rehaussements de contraste. Et il faut aussi prendre garde à leurs effets qui peuvent faire disparaitre des structures intéressantes ou au contraire en créer.

