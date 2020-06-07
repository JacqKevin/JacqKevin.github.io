---
title: Preprocessing
description: Preprocessing
permalink: Preprocessing_HSI.html
---

## Sensor Normalization

Generally, reflectance of the sample are acquire with HSI. It need to be calibrated with a white and a dark to be defined in percentage of reflectance. This step is called data normalization.

## Conversion

According to Beer-Lambert law, the chemical concentration of a compound is related to the absorbance (A). Thus, the hyperspectral image can be converted into pseudo-absorbance with the formula: A=log(1/R).

## Spectral preprocessing

<center>
{% include image.html file="Preprocessing.jpg" %}
</center>

In this toolbox, four main preprocessing are used, also nine combinations of them. Thus, thirteen preprocessing and the raw data are compared to find an optimal one. They allow to reduce noise and highlight relevant spectral information to predict the interest variable(s) (Vidal2012, Rinnan2009).

Detrending is used to remove the baseline (Barnes1989). Multiplicative Scatter Correction (MSC) and Standard Normal Variate (SNV, Barnes1989) are used to correct the spectra from light scattering. The Savitzky–Golay filter is used to derivate the spectra and to reduce additive effects (baseline offset and slope, Savitzky1964).

Then it is necessary to be careful with their effects which can make interesting wavelength structures disappear or on the contrary artificially create them.

```markdown
Vidal, M., Amigo, J. M. (2012) Pre-processing of hyperspectral images. Essential steps before image analysis. Chemometrics and Intelligent Laboratory Systems 117: 138–148

Rinnan, Å., Berg, F. van den, Engelsen, S.B. (2009) Review of the most common preprocessing techniques for near-infrared spectra. TrAC Trends in Analytical Chemistry 28: 1201–1222

Barnes, R.J., Dhanoa, M.S., Lister, S.J. (1989) Standard Normal Variate Transformation and De-Trending of Near-Infrared Diffuse Reflectance Spectra. Applied Spectroscopy 43: 772–777

Savitzky, A., Golay, M.J.E. (1964) Smoothing and Differentiation of Data by Simplified Least Squares Procedures. Analytical Chemistry 36: 1627–1639
```

## Spectral normalization
Second spectral processing can be used to normalized the signal base on the mean and standard deviation of the hyperspectral image. Thus, centering or autoscaling can be chosen by the user.

## Data reduction

They can be reduced to speed up computation time, this is often done with PCA or MNF to remove redundant and correlated (collinear) variables. Or by selecting discriminating and remove irrelevant or noisy wavelengths for a variable to be predicted with variable selection algorithms. 

```markdown
Pearson, K. (1901) On lines and planes of closest fit to systems of points in space. Philosophical Magazine 2: 559–572

Green, A.A., Berman, M., Switzer, P., Craig, M.D. (1988) A Transformation for Ordering Multispectral Data in Terms of Image Quality with Implications for Noise Removal. IEEE Transactions on Geoscience and Remote Sensing 26: 65–74

Xiaobo, Z., Jiewen, Z., Povey, M.J.W., Holmes, M., Hanpin, M. (2010) Variables selection methods in near-infrared spectroscopy. Analytica Chimica Acta 667: 14–32
```

## Spatial preprocessing

As with the creation of a multivariate model, the images require pre-processing to reduce noise or highlight structures, such as normalizations, smoothing, derivatives or contrast enhancements. And also be careful of their effects which can make interesting structures disappear or on the contrary artificially create them.

