---
title: Supervised Classifications
description: Supervised Classifications
permalink: HSI_SupervisedClassifications.html
sidebar: Matlab_sidebar
---

# Supervised classification Toolbox
The mandatory data to use this toolbox are a hyperspectral image (M), the corresponding RGB image (RGB), depth (d), and wavelength (wl). Then, a function will help you to create a training labelled map, or use a labelled vector. Finnaly, functions will estimate discrimination models. Others functions can be used to estimate deposit chronicles.

<a href="https://github.com/JacqKevin/HSI_SupervisedClassification">
  HSI_SupervisedClassification repository
</a>

If you use this toolbox, we would appreciate a reference to one of the following papers:

# Worflow

Soon!

## Reflectance or pseudo-absorbance
Generally, the hyperspectral image unity is reflectance (R). According to Beer-Lambert law, the chemical concentration of a compound is related to the absorbance (A). Thus, the hyperspectral image can be converted into pseudo-absorbance with the formula: A=log(1/R).

## Training set
A labelled map or vector is used to extract training pixel. It must have the dimension of the hyperspectral image.

## Spectral preprocessing

{% include image.html file="Preprocessing.jpg" %}

In this toolbox, four main preprocessing are used, also nine combinations of them. Thus, thirteen preprocessing and the raw data are compared to find an optimal one. They allow to reduce noise and highlight relevant spectral information to predict the interest variable(s).

Detrending is used to remove the baseline. Multiplicative Scatter Correction (MSC) and Standard Normal Variate (SNV) are used to correct the spectra from light scattering. The Savitzky–Golay filter is used to derivate the spectra and to reduce additive effects (baseline offset and slope).

The use can select one them to estimate the discrimination model.

```markdown
Vidal, M., Amigo, J. M. (2012) Pre-processing of hyperspectral images. Essential steps before image analysis. Chemometrics and Intelligent Laboratory Systems 117: 138–148

Rinnan, Å., Berg, F. van den, Engelsen, S.B. (2009) Review of the most common preprocessing techniques for near-infrared spectra. TrAC Trends in Analytical Chemistry 28: 1201–1222

Barnes, R.J., Dhanoa, M.S., Lister, S.J. (1989) Standard Normal Variate Transformation and De-Trending of Near-Infrared Diffuse Reflectance Spectra. Applied Spectroscopy 43: 772–777

Savitzky, A., Golay, M.J.E. (1964) Smoothing and Differentiation of Data by Simplified Least Squares Procedures. Analytical Chemistry 36: 1627–1639
```

## Normalization
A second spectral processing can be used to normalized the signal base on the mean and standard deviation of the hyperspectral image. Thus, centering or autoscaling can be chosen by the user.

## Discrimination methods

* Decision Tree (DT)
* Random Forest (RF)
* Artificial Neural Network (ANN)
* 1D Convolutionnal Neural Network (CNN-1D)
* Linear Discriminant Analysis (LDA)
* Quadratic Discriminant Analysis (QDA)
* Partial least Squares Discriminant Analysis(PLS-DA)

## Variable selection and Reduce model estimation

Available soon