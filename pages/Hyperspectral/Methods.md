---
title: Methods
description: Methods
permalink: Methods_HSI.html
---

![Worflow](/images/Worflow.jpg)

## Semi-quantitative methods

A first approach to extracting information from spectral data is to search for characteristic areas corresponding to one or a few wavelength(s). In this case we speak of univariate approaches with a local rather than global spectral approach.

Absorption or excitation energies in the ranges presented above are quantified at known energy levels. It is therefore possible to create tables that reference the compounds or chemical bonds associated with these energies or wavelengths. As is the case with medium-infrared spectroscopy, UV-visible fluorescence or X-rays. In some ranges this is complicated to achieve because of the superposition of many properties and the spectral resolution of the sensors, as in near-infrared spectroscopy.

Caution should be used with these indices, however, as several chemical compounds may interact in the same spectral regions and the spectral resolution may not be fine enough to distinguish these compounds. There are also many indices developed in remote sensing for multispectral data, but which are used very little in laboratory spectroscopy because the information sought is not the same.

These indices are semi-quantitative and can be subsequently calibrated from regression models by estimating a link with a reference analytical method. This is known as simple linear regression (SLR), which estimates a relationship between an explained variable ($y$, analytical) and an explanatory variable ($x$, spectral).

## Quantitative methods

Rather than studying specific spectral regions for a compound or chemical bond, global approaches that use the entire spectrum have been developed and are called multivariate methods. Bio-physical-chemical information can be found in different areas of the spectrum, it can also be related to another correlated compound, or on the contrary, it can be perturbed by another. These global methods can thus find all this information, which makes it possible to create efficient prediction models.
		
The main regression methods that can be found in the literature or that are being developed are presented below and can be schematized with the figure below. More information is available in Tuffery's book (Tufféry2012). 

<center>
{% include image.html file="Multi.jpg" %}
</center>

<ul>
<li> Linear methods: </li>
<ul>
<li> Multiple linear regression (MLR) is similar to SLR, the difference lies in the multitude of explanatory variables ($X$) that correspond to spectral data at several wavelengths. </li>
<li> Principal component regression (PCR, Jolliffe1982) is an RLM that uses as explanatory variables the principal components ($PC$) of the principal component analysis (PCA, Pearson1901). PCs correspond to groupings of $X$ explanatory variables with similar information. Thus, PCA reduces the size of the spectral data by grouping the correlated $X$. The PCA calculates a new geometric landmark, different from spectral space, which is oriented along independent axes explaining the variability of the explanatory data. </li>
<li> Partial least squares regression (PLSR) defined by Wold (Wold1984) (which may also be non-linear) estimates latent variables (LVs) that correspond to groupings of the $X$ explanatory variables related to those to be explained $Y$. It therefore also estimates a new geometric benchmark, which is oriented along independent axes that explain the variability of the $X$ explanatory data while maximizing the correlation between $X$ and $Y$. This is one of the most widely used methods in spectroscopic data processing (chemometrics). </li>
</ul>
<li> Non-linear methods: </li>
<ul>
<li> Multivariate adaptive spline regression (MARS) created by Friedman (Friedman1991) allows non-linearities to be modelled using rules, a non-parametric method. To do this, it uses recursive partitioning to estimate subfields that can be modeled by linear functions. A MARS model can therefore be represented by a succession of rules leading to terminal linear models. </li>
<li> Support Vector Machines (SVM, Vapnik1998) use a large dimensional space to estimate a linear (n>2) hyperplane to solve a nonlinear problem. The estimated linear hyperplane then undergoes an inverse transformation to return to the initial nonlinear space. </li>
<li> Artificial Neural Networks (ANN, McCulloch1943, Rosenblatt1958) seeks to reproduce the brain's ability to learn. This method relies on a set of interconnected fundamental units, the neurons. A network is a set of layers of neurons that function, one after the other. Each neuron receives some of the information it processes and communicates the results to its closest neighbours in the next layer of neurons. The simplest network consists of three layers, one input layer, one computational or hidden layer and one output layer. </li>
<li> Deep learning networks are methods that are developing in all fields and also recently in spectroscopic data analysis. It is a method close to ANN, the difference is that the deep network has several hidden layers and an often large number of neurons (Ivakhnenko1965, Schmidhuber2015). </li>
</ul>
</ul>
From a mathematical point of view, we make the difference between a vector with a lower case letter ($x$,$y$) and a matrix with an upper case letter ($X$,$Y$). 

```markdown
Tufféry, S. (2012) Data Mining et Statistique Décisionnelle : L’intelligence Des Données Éd. Technip

Jolliffe, I.T. (1982) A Note on the Use of Principal Components in Regression. Journal of the Royal Statistical Society. Series C (Applied Statistics) 31: 300–303

Pearson, K. (1901) On lines and planes of closest fit to systems of points in space. Philosophical Magazine 2: 559–572

Wold, S., Ruhe, A., Wold, H., Dunn, III, W.J. (1984) The Collinearity Problem in Linear Regression. The Partial Least Squares (PLS) Approach to Generalized Inverses. SIAM Journal on Scientific and Statistical Computing 5: 735–743

Friedman, J.H. (1991) Multivariate Adaptive Regression Splines. The Annals of Statistics 19: 1–67

Vapnik, V.N. (1998) Statistical Learning Theory Wiley

McCulloch, W.S., Pitts, W. (1943) A logical calculus of the ideas immanent in nervous activity. The Bulletin of Mathematical Biophysics 5: 115–133

Rosenblatt, F. (1958) The Perceptron: A Probabilistic Model for Information Storage and Organization in The Brain. Psychological Review 65: 386–408

Ivakhnenko, A., Lapa, V.G. (1965) Cybernetic Predicting Devices New York, CCM Information Corp.

Schmidhuber, J. (2015) Deep Learning in Neural Networks: An Overview. Neural Networks 61: 85–117
```

## Estimation of pure signals (endmembers)

From the spectroscopic data, chemical fingerprints of compounds can be obtained if the sample is pure and homogeneous. In the case of multi- or hyper-spectral images, it is the inhomogeneity of the sample that is studied, and is then characterized through the different compounds it contains by estimating pure signals, also called endmembers (EM) (Bioucas-Dias2012, Keshava2003). These are referred to as unmixing methods for the extraction of pure signals. There are three main groups of methods for estimating these pure signals:

<ul>
<li> Geometric methods are based on the possibility of finding a geometric shape that frames the data set. </li>
<ul>
<center>
{% include image.html file="EM.jpg" %}
</center>
<li> The standard principle is based on the assumption that a spectroscopic signal is the sum of sub-signals corresponding to constituents of the sample. Many methods exist and can be described as the determination of a simplex (n-dimensional triangle) that encompasses all the data, and its extremities correspond to the EMs. The best known methods are Pixel Purity Index (PPI, Boardman1993), N-FINDR (Winter1999), Vertex Component Analysis (VCA, Nascimento2005).  </li>
<li> We can also use the opposite hypothesis, i.e. find in the case of a globally homogeneous sample, pixels different from the majority. With a calculation of the distances, we can highlight them. For example, the algorithm of Kennard and Stone (Kennard1969) is used to find the most different spectra in a dataset. </li>
</ul>
<li> Statistical or blind source separation methods are used when the pure signals are very mixed in each pixel. This means that each HSI pixel consists of several sources. Geometric methods are not efficient enough in this case to find poles that are representative of reality. Whereas statistical methods, via a longer calculation time, can estimate them. We can cite the methods: Independent Component Analysis (ICA, Comon1994, Rutledge2013) and Multivariate Curve Resolution Alternating Least Square (MCR-ALS, Jaumot2015) which are used in different studies. </li>
<li> Finally, there are parsimonious or sparse methods that use sample knowledge through libraries or pure spectra. These methods will estimate the proportion of these signatures in each of the spectra. For example, we find the algorithms: Fully Constrained Least Squares (FCLS, Heinz2001), Sparse Unmixing by Variable Splitting and Augmented Lagrangian (SUnSAL, Bioucas-Dias201). </li>
</ul>

Then these EMs allow us to estimate their abundances in each of the spectra from a similarity calculation based on distance. In the case of an image, this makes it possible to estimate an abundance map of these EMs and thus see their variations.
		
These pure signals are often compared to libraries or pure sample spectra to characterize them. Several libraries exist, such as those from the USGS (Kokaly2017), CSIRO (Lau2017), ECOSTRESS (Meerdink2019), or others integrated into commercial software (ENVI).

These methods are widely used in remote sensing to discriminate the main entities (roads, buildings, forests, rivers) or ground geology with multi- and hyper-spectral data. They are also widely used to characterize minerals present in geological samples, such as sedimentary cores, and thus determine the origin of sediments.

```markdown
Bioucas-Dias, J.M., Plaza, A., Dobigeon, N., Parente, M., Du, Q., Gader, P., Chanussot, J. (2012) Hyperspectral Unmixing Overview: Geometrical, Statistical, and Sparse Regression-Based Approaches. IEEE Journal of selected topics in applied earth observations and remote sensing 5: 354–379

Keshava, N. (2003) A Survey of Spectral Unmixing Algorithms. Lincoln Laboratory Journal 14: 55–78

Boardman, J.W. (1993) Automating spectral unmixing of AVIRIS data using convex geometry concepts. In: 4th Annual JPL Airborne Geoscience Workshop 11–14.

Winter, M.E. (1999) N-FINDR: an algorithm for fast autonomous spectral end-member determination in hyperspectral data. In: Descour, M. R. & Shen, S. S. (eds) Proc. SPIE 3753, Imaging Spectrometry V International Society for Optics and Photonics, 266–275.

Nascimento, J.M.P., Dias, J.M.B. (2005) Vertex Component Analysis: A Fast Algorithm to Unmix Hyperspectral Data. IEEE Transactions on Geoscience and Remote Sensing 43: 898–910

Kennard, R.W., Stone, L.A. (1969) Computer Aided Design of Experiments. Technometrics 11: 137–148

Comon, P. (1994) Independent component analysis, A new concept? Signal Processing 36: 287–314

Rutledge, D.N., Jouan-Rimbaud Bouveresse, D. (2013) Independent Components Analysis with the JADE algorithm. TrAC Trends in Analytical Chemistry 50: 22–32

Jaumot, J., de Juan, A., Tauler, R. (2015) MCR-ALS GUI 2.0: New features and applications. Chemometrics and Intelligent Laboratory Systems 140: 1–12

Heinz, D.C., Chein-I-Chang (2001) Fully constrained least squares linear spectral mixture analysis method for material quantification in hyperspectral imagery. IEEE Transactions on Geoscience and Remote Sensing 39: 529–545

Bioucas-Dias, J.M., Plaza, A., Dobigeon, N., Parente, M., Du, Q., Gader, P., Chanussot, J. (2012) Hyperspectral Unmixing Overview: Geometrical, Statistical, and Sparse Regression-Based Approaches. IEEE Journal of selected topics in applied earth observations and remote sensing 5: 354–379

Kokaly, R.F., Clark, R.N., et al. (2017) USGS Spectral Library Version 7

Lau, I.C., LeGras, M., Laukamp, C., Mason, P., Warren, P. (2017) CSIRO Shortwave Infrared Spectral Library – Evaluation and Status Report 2017 Report EP175249

Meerdink, S.K., Hook, S.J., Roberts, D.A., Abbott, E.A. (2019) The ECOSTRESS spectral library version 1.0. Remote Sensing of Environment 230: 111196
```

## Classification methods

Data can also be grouped in a qualitative way, called classification or pattern recognition. Partial knowledge of the data can be obtained and used, known as supervised classification or discrimination, to estimate, for example, the presence or absence of a compound, or high-medium-high levels of abundance. In the case of unknown data, we speak of unsupervised classification or clustering. These methods can be applied to both the spatial and spectral dimensions.

<center>
{% include image.html file="classif.jpg" %}
</center>

### Unsupervised methods (clustering)

<ul>
<li> Principal Component Analysis (PCA) allows you to reduce the data and thus quickly visualize their main variabilities. A similar approach called Minimum Noise Fraction (MNF) keeps the most informative and least noisy components. </li>
<li> The K-means or K-medoids methods estimate representative centers of a K number of groups. An advanced method using fuzzy rules has been developed, C-fuzzy means (FCM, Dunn1973). </li>
<li> Hierarchical classifications are divided into two families, those that aggregate (hierarchical ascending classification HAC) and those that divide (hierarchical descending classification HDC) (Ward1963). In the case of HAC, the data are agglomerated from one group to the next according to a distance criterion until a single group is obtained, and vice versa for HDC. The result is a dendrogram that can be cut at a certain level defining the number of groups. </li>
</ul>

```markdown
Dunn, J.C. (1973) A Fuzzy Relative of the ISODATA Process and Its Use in Detecting Compact Well-Separated Clusters. Journal of Cybernetics 3: 32–57

Ward, J.H. (1963) Hierarchical Grouping to Optimize an Objective Function. Journal of the American Statistical Association 58: 236–244
```

### Supervised methods (discrimination)

<ul>
<li> The k-nearest neighbors method (KNN) is a nonparametric method that estimates a probability of belonging to a group according to a rule, which here is the distance from the surrounding individuals (Hart1968). It calculates the distance between an "unknown" sample and all known ones. Then this new sample is classified in a group with its closest K neighbors. There are several approaches to improve these predictions, such as adding fuzzy rules with the KNN-fuzzy method (Keller1985), or using the theory of belief functions EkNN (Evidential KNN, Denoeux1995, Shafer1976).  </li>
<li> Linear Discriminant Analysis (LDA) looks for the axis that best separates the groups (Fisher1936). This can be seen as a correspondence with PCA and PLS. It can use non-linear functions, as with Quadratic Discriminant Analysis (QDA). There is also a similar approach called PLS-DA (partial least squares discriminant analysis), or Soft independent modelling by class analogy (SIMCA). </li> % A terminer
<li> Decision trees (DTs) are non-parametric methods based on the creation of a binary choice decision tree (Breiman1984). For an explanatory variable, the algorithm will determine rules to separate one or several groups. At the end of it a set of rules on several variables is created, and this forms a tree, where we find at the node level the binary decision and at the leaf level the estimated class. A training with several decision trees allows to create a forest of decision trees (RF) (TinKamHo1995), then the majority rules are kept. </li>
<li> Multivariate adaptive spline regression (MARS), previously mentionned, created by Friedman (Friedman1991) allows non-linearities to be modelled using rules, a non-parametric method. To do this, it uses recursive partitioning to estimate subfields that can be modeled by linear functions. A MARS model can therefore be represented by a succession of rules leading to terminal linear models. </li>
<li> Support Vector Machines (SVM, Vapnik1998) use a large dimensional space to estimate a linear (n>2) hyperplane to solve a nonlinear problem. The estimated linear hyperplane then undergoes an inverse transformation to return to the initial nonlinear space. </li>
<li> Artificial Neural Networks (ANN, McCulloch1943, Rosenblatt1958) seeks to reproduce the brain's ability to learn. This method relies on a set of interconnected fundamental units, the neurons. A network is a set of layers of neurons that function, one after the other. Each neuron receives some of the information it processes and communicates the results to its closest neighbours in the next layer of neurons. The simplest network consists of three layers, one input layer, one computational or hidden layer and one output layer. </li>
<li> The deep networks, as previously mentioned, are composed of several layers made up of an often large number of neurons (Ivakhnenko1965, Schmidhuber2015). These methods are widely used in the case of image learning. Indeed, they will represent them thanks to their compositions, such as intensity levels, finite (edges of an object) and coarse (a region, a shape, an object) structures. We are talking here about learning at different levels of abstraction which is a function of the depth of the network. </li>
</ul>

Due to the complexity of multi- and hyper-spectral data, it is mainly non-linear methods (SVM, ANN, CNN) that are used to classify each pixel from labelled areas. In order to reduce this complexity and the computation time, two processing proposals are used. Some reduce the data with demixing algorithms (VCA, ICA). Others use the spatial dimension with neighbouring pixels around the pixel to be classified or superpixels.

```markdown
Hart, P. (1968) The condensed nearest neighbor rule. IEEE Transactions on Information Theory 14: 515–516

Keller, J.M., Gray, M.R., Givens, J.A. (1985) A fuzzy K-nearest neighbor algorithm. IEEE Transactions on Systems, Man, and Cybernetics SMC-15: 580–585

Denoeux, T. (1995) A k-nearest neighbor classification rule based on Dempster-Shafer theory. IEEE Transactions on Systems, Man, and Cybernetics 25: 804–813

Shafer, G. (1976) A Mathematical Theory of Evidence Princeton University Press

Fisher, R.A. (1936) The Use of Multiple Measurements in Taxonomic Problems. Annals of Eugenics 7: 179–188

Breiman, L., Friedman, J.H., Olshen, R.A., Stone, C.J. (1984) Classification And Regression Trees Routledge

Ho, T.K. (1995) Random decision forests. In: Proceedings of 3rd International Conference on Document Analysis and Recognition IEEE Comput. Soc. Press, 278–282.

Friedman, J.H. (1991) Multivariate Adaptive Regression Splines. The Annals of Statistics 19: 1–67

Vapnik, V.N. (1998) Statistical Learning Theory Wiley

McCulloch, W.S., Pitts, W. (1943) A logical calculus of the ideas immanent in nervous activity. The Bulletin of Mathematical Biophysics 5: 115–133

Rosenblatt, F. (1958) The Perceptron: A Probabilistic Model for Information Storage and Organization in The Brain. Psychological Review 65: 386–408

Ivakhnenko, A., Lapa, V.G. (1965) Cybernetic Predicting Devices New York, CCM Information Corp.

Schmidhuber, J. (2015) Deep Learning in Neural Networks: An Overview. Neural Networks 61: 85–117
```

## Image segmentation

An image carries information about the structures making up a scene or sample. Methods exist to characterize them, called segmentation. They can be grouped into two families:
<ul>
<li> Geometric methods that estimate structures in the image using a morphological operator. </li>
<ul>
<li> Laminae can be detected using intensity maxima or minima with methods such as H-maxima, or the watershed method (Vincent1991) which considers an image as a topographic relief and will detect their boundaries by "flooding" the image. If the laminae could be characterized by colour ranges, multi-level thresholding could be performed, but since the colours vary along the sample, adaptive thresholding should be considered to extract each lamina (Zuiderveld1994). It is also possible to detect lamina boundaries, which are more or less sharp breaks, with derivatives or gradients, or by modeling the boundary with the Hough transform (Hough1959, Duda1972) for example. The detection of laminae is often performed with a 1D signal along the sample, as it can be sufficiently informative if it is not very noisy. If this is not the case, 1D signals can be multiplied with overlap and then re-associated. It is also possible to use the whole image, but often the laminates are not characterizable over the whole width of the sample, so the different "pieces" have to be put together to reconstruct it, which is not an easy task. The work of Gan (Gan2013) on the subject, proposes to use basic morphological operators such as erosion and dilation to reattach or separate these areas. </li>
<li> For granulometry, the methods are similar with the detection of breaks between grains through gradients or the watershed. </li>
</ul>
<li> Statistical methods that estimate similarities or trends in the image. </li>
<ul>
<li> In the case of the detection of laminates, which are redundant and periodic phenomena, approaches based on Fourier transform or wavelets can be used. </li>
<li> For particle size estimation, the most commonly used approach is based on autocorrelation, which estimates internal dependencies in the image, since neighboring pixels of the same particle are dependent. </li>
</ul>
</ul>

```markdown
Vincent, L., Soille, P. (1991) Watersheds in digital spaces: an efficient algorithm based on immersion simulations. IEEE Transactions on Pattern Analysis and Machine Intelligence 13: 583–598

Zuiderveld, K. (1994) Contrast Limited Adaptive Histogram Equalization. In: Graphics Gems IV Academic Press, 474–485.

Hough, P.V.C. (1959) Machine Analysis of Bubble Chamber Pictures. In: Proc. Int. Conf. High Energy Accelerators and Instrumentation 554–558.

Duda, R.O., Hart, P.E. (1972) Use of the Hough transformation to detect lines and curves in pictures. Communications of the ACM 15: 11–15

Gan, S.Q., Scholz, C.A. (2013) Extracting paleoclimate signals from sediment laminae: An automated 2-D image processing method. Computers & Geosciences 52: 345–355
```
