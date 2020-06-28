---
title: Fusion
description: Fusion toolboxes
permalink: Fusion_HSI.html
sidebar: home_sidebar
---

As we have seen, each spectral domain brings its own biophysical-chemical information that can be found in others. This is why combining different data sets from several spectral domains is of interest to improve the characterization of samples. Depending on the type of sensor, the methods used are different, which is why this section is divided into two parts dealing with image (2D) and signal (1D) fusion.

<center>
{% include image.html file="Fusion_Methods.jpg" %}
</center>
		
Image fusion methods must overcome two main difficulties, (1) the modification of the sample surface area between acquisitions and (2) the non-homogeneity of the resolutions. These are issues that are mainly studied in the fields of remote sensing (field studies) and medical (more complete diagnosis of a patient) to agglomerate multisensor data. The field of analytical chemistry is also beginning to take an interest in this area, drawing on the methods developed in these two fields.

```markdown
de Juan, A. (2018) Hyperspectral image analysis. When space meets Chemistry. Journal of Chemometrics 32: 1–13

de Juan, A., Gowen, A., Duponchel, L., Ruckebusch, C. (2019) Image Fusion. In: Data Fusion Methodology and Applications 311–344.
```

## Image fusion

### Fusion at high resolution

The homogenization of the resolutions (2) can be carried out at several levels. Either at the lowest of the resolutions, which is done in the registration step (1), we can speak of low resolution merging, which corresponds to a combination of the data sets. Or advanced fusion approaches are used for high-resolution fusion. These methods can be grouped into three families according to the type of information merged. 

<center>
{% include image.html file="Fus.jpg" %}
</center>

```markdown
Dasarathy, B.V. (1997) Sensor fusion potential exploitation-innovative architectures and illustrative applications. Proceedings of the IEEE 85: 24–38

Ghassemian, H. (2016) A review of remote sensing image fusion methods. Information Fusion 32: 75–89

Martin, A. (2005) La fusion d’informations. Cours ENSIETA
```

<ul>
<li> Low-level or pixel-level fusion consists of merging the raw information after the acquisition, so all information is retained. Then, the composite sensor is pre-processed before creating a quantitative or qualitative predictive model. </li>
<li>  Mid-level or attribute-level merging represents the merging of reduced initial data, such as with a PCA, or de-mixing, or segmentation methods. This allows to keep global information about the sample, and to remove noise, as well as potentially local information if checks are not performed. Finally, a quantitative or qualitative model is created.  </li>
<li>  High-level or decision-level merging is the merging of data extracted from the initial data, such as with machine learning or regression methods. Each sensor is therefore pre-processed, then a quantitative or qualitative model is created to estimate abundance or classification maps which are then merged. In the case of the study of a single property, it must be ensured that discriminating information is available in each of the sensors.  </li>
</ul>

In the case of spectroscopic data, as we have seen, spectral ranges do not always carry similar information. This is why high level fusion is interesting for the fusion of classification maps of different and complementary variables. As for example to estimate the mineralogy of a sedimentary sample that are characterizable with different spectral ranges that carry majority information. But in the case of the same variable between different sensors, it is of little interest if some of these sensors carry minority information that cannot allow a correct modeling. 

However, it is possible that minority information on a variable of interest may be contained in certain spectral ranges, and that merging it with a spectral range carrying more information may be beneficial to increase modeling performance. For this reason, pixel-level fusion methods are of interest and will be discussed in more detail later (Yokoya2017, Li2017, Loncan2015, Vivone2015). Indeed, these can be grouped in four families. The first two families were created for merging multispectral data with a panchromatic image (similar to a grayscale image), which is why these methods are called pansharpening. They were then modified for merging multi- and hyper-spectral data, which is called hypersharpening.

<center>
{% include image.html file="recap.jpg" %}
</center>

<ul>
<li> Component Substitution (CS) involves projecting low (BR) and high (HR) resolution data into another space that separates the spatial and spectral information. Then, these methods will estimate the BR components that are closest to the HR components to substitute them. The most commonly used methods are PCA (Chavez1991), ICA, Intensity-Hue-Saturation (IHS, Tu2001), Brovey transform (BT, Gillespie1987), Gram-Schmidt (GS, Laben2000, Aiazzi2007). </li>
<li>  Multi-resolution analysis (MRA) decomposes BR and HR data at several similar levels of resolution using wavelets (Khan2008, Vivone2014, Ranchin2000, Otazu2005) or Laplacian pyramids (Aiazzi2006, Aiazzi2003, Aiazzi2002, Lee2004, Alparone2007) or Gaussian pyramids. Then, transition models are computed between these different resolutions to estimate the high and low frequencies (also called details and structures) missing in the RH interpolated BR data.  </li>
<li>  Methods that use subspaces are called sparsal methods, because they use the (Yokoya2011) methods. BR and HR data are synthesized through pure components (endmembers) that can be found between the two datasets. This allows to reconstruct the BR to HR cube.</li>
<li>  The regression methods create a model linking the different spectral bands between the reduced BR and HR data to the BR, and then apply it at high resolution for the prediction of the BR to HR cube (DeJuan2019).  </li>
</ul>

New methods are emerging with the use of Bayesian approaches such as Zhang2009 or deep learning networks such as Liu2018, Dian2018, Shao2018.

```markdown
Aiazzi, B., Alparone, L., Baronti, S., Garzelli, A. (2002) Context-driven fusion of high spatial and spectral resolution images based on oversampled multiresolution analysis. IEEE Transactions on Geoscience and Remote Sensing 40: 2300–2312

Aiazzi, B., Alparone, L., Baronti, S., Garzelli, A., Selva, M. (2003) An MTF-based spectral distortion minimizing model for pan-sharpening of very high resolution multispectral images of urban areas. In: 2nd GRSS/ISPRS Joint Workshop on ‘Data Fusion and Remote Sensing over Urban Areas’ IEEE, 90–94.

Aiazzi, B., Alparone, L., Baronti, S., Garzelli, A., Selva, M. (2006) MTF-tailored Multiscale Fusion of High-resolution MS and Pan Imagery. Photogrammetric Engineering & Remote Sensing 72: 591–596

Aiazzi, B., Baronti, S., Selva, M. (2007) Improving Component Substitution Pansharpening Through Multivariate Regression of MS+Pan Data. IEEE Transactions on Geoscience and Remote Sensing 45: 3230–3239

Alparone, L.., Wald, L.., Chanussot, J.., Thomas, C.., Gamba, P.., Bruce, L.M. (2007) Comparison of Pansharpening Algorithms: Outcome of the 2006 GRS-S Data-Fusion Contest. IEEE Transactions on Geoscience and Remote Sensing 45: 3012–3021

Chavez, P.S., Sides, S.C., Anderson, J.A. (1991) Comparison of Three Different Methods to Merge Multiresolution and Multispectral Data: Landsat TM and SPOT Panchromatic. Photogrammetric Engineering and Remote Sensing 57: 295–303

de Juan, A., Gowen, A., Duponchel, L., Ruckebusch, C. (2019) Image Fusion. In: Data Fusion Methodology and Applications 311–344.

Dian, R., Li, S., Guo, A., Fang, L. (2018) Deep Hyperspectral Image Sharpening. IEEE Transactions on Neural Networks and Learning Systems 29: 5345–5355

Gillespie, A.R., Kahle, A.B., Walker, R.E. (1987) Color enhancement of highly correlated images. II. Channel ratio and “chromaticity” transformation techniques. Remote Sensing of Environment 22: 343–365

Khan, M.M., Chanussot, J., Condat, L., Montanvert, A. (2008) Indusion: Fusion of Multispectral and Panchromatic Images Using the Induction Scaling Technique. IEEE Geoscience and Remote Sensing Letters 5: 98–102

Laben, C.A., Brower, B. V. (2000) Process for enhancing the spatial resolution of multispectral imagery using pan-sharpening. U.S. Patent 6,011,875

Lee, C.K., Ko, E.J., Kim, K.W., Kim, Y.J. (2004) Partial Least Square Regression Method for the Detection of Polycyclic Aromatic Hydrocarbons in the Soil Environment Using Laser-Induced Fluorescence Spectroscopy. Water, Air, & Soil Pollution 158: 261–275

Li, S., Kang, X., Fang, L., Hu, J., Yin, H. (2017) Pixel-level image fusion: A survey of the state of the art. Information Fusion 33: 100–112

Liu, Y., Chen, X., Wang, Z., Wang, Z.J., Ward, R.K., Wang, X. (2018) Deep learning for pixel-level image fusion: Recent advances and future prospects. Information Fusion 42: 158–173

Loncan, L., de Almeida, L.B., et al. (2015) Hyperspectral Pansharpening: A Review. IEEE Geoscience and Remote Sensing Magazine 3: 27–46

Otazu, X., Gonzalez-Audicana, M., Fors, O., Nunez, J. (2005) Introduction of sensor spectral response into image fusion methods. Application to wavelet-based methods. IEEE Transactions on Geoscience and Remote Sensing 43: 2376–2385

Ranchin, T., Wald, L. (2000) Fusion of high spatial and spectral resolution images: the ARSIS concept and its implementation. Photogrammetric Engineering and Remote Sensing 66: 49–61

Shao, Z., Cai, J. (2018) Remote Sensing Image Fusion with Deep Convolutional Neural Network. IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing 11: 1656–1669

Tu, T.-M., Su, S.-C., Shyu, H.-C., Huang, P.S. (2001) A new look at IHS-like image fusion methods. Information Fusion 2: 177–186

Vivone, G., Restaino, R., Dalla Mura, M., Licciardi, G., Chanussot, J. (2014) Contrast and Error-Based Fusion Schemes for Multispectral Image Pansharpening. IEEE Geoscience and Remote Sensing Letters 11: 930–934

Vivone, G., Alparone, L., et al. (2015) A Critical Comparison Among Pansharpening Algorithms. IEEE Transactions on Geoscience and Remote Sensing 53: 2565–2586

Yokoya, N., Yairi, T., Iwasaki, A. (2011) Coupled non-negative matrix factorization (CNMF) for hyperspectral and multispectral data fusion: Application to pasture classification. In: 2011 IEEE International Geoscience and Remote Sensing Symposium IEEE, 1779–1782.

Yokoya, N., Grohnfeldt, C., Chanussot, J. (2017) Hyperspectral and Multispectral Data Fusion: A comparative review of the recent literature. IEEE Geoscience and Remote Sensing Magazine 5: 29–56

Zhang, Y., De Backer, S., Scheunders, P. (2009) Noise-Resistant Wavelet-Based Bayesian Fusion of Multispectral and Hyperspectral Images. IEEE Transactions on Geoscience and Remote Sensing 47: 3834–3843
```

### Fusion at low resolution

To correct surface distortions of the samples between acquisitions (1), the images must be resized. In the case of remote sensing images, this is quite simple thanks to the georeferencing of the pixels. In the case of laboratory images, the simplest way is to co-reference them, i.e. to acquire the images with several sensors simultaneously or with a short delay between them. In other cases, in the laboratory and in the field, methods are needed to registered the images. For this, there are essentially two families of methods (Nasreddine2010, Malandain2006):

<ul>
<li> he first is based on the intensities of the images and is called the iconic approach. For this, the methods use a distance between the images and seek to minimize it by distorting it without taking into account the geometric structures but only with the intensities. In the case of multi-sensor images, the intensities can be linked by a non-linear mathematical relationship. </li>
<li> The second one uses the characteristics of the images, such as curves, lines, points, we talk about a geometric approach. It is possible to do it manually with reference points or automatically with algorithms that will detect them, such as the Speeded Up Robust Features (SURF, Bay2006) and the Scale-Invariant Feature Transform (SIFT, Lowe1999). These algorithms estimate descriptors or control points at the global image scale. Local versions have then been developed and are more powerful to take into account local variations in the sample which are often different from the global variations (Liu2011, Brigot2017). These 2D descriptors were then generalized for 3D images, and more specifically for hyperspectral images. Once the control points have been defined, a deformation model is estimated to minimize the distance between these points. One image is used as a base and the other image is then deformed accordingly to be spatially aligned with the first one. </li>
</ul>

```markdown
Bay, H., Tuytelaars, T., Van Gool, L. (2006) SURF: Speeded Up Robust Features. In: 9th European Conference on Computer Vision Graz, Autriche, Springer, Berlin, Heidelberg, 404–417.

Brigot, G. (2017) Prédire La Structure Des Forêts à Partir d’images PolInSAR Par Apprentissage de Descripteurs LIDAR.

Liu, C., Yuen, J., Torralba, A. (2011) SIFT Flow: Dense Correspondence across Scenes and Its Applications. IEEE Transactions on Pattern Analysis and Machine Intelligence 33: 978–994

Lowe, D.G. (1999) Object recognition from local scale-invariant features. In: Proceedings of the Seventh IEEE International Conference on Computer Vision IEEE, 1150–1157 vol.2.

Malandain, G. (2006) Les Mesures de Similarité Pour Le Recalage Des Images Médicales. Universite de Nice Sophia-Antipolis.

Nasreddine, K. (2010) Recalage de Signaux et Reconnaissance de Formes : Application à l’analyse Des Otolithes de Poissons. Université de Bretagne occidentale - Brest.
```

## Signal alignment

Description soon