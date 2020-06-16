---
title: Methods
description: Methods
permalink: Processing_Methods_HSI.html
---
<center>
{% include image.html file="Methods.jpg" %}
</center>

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

### References

#### Laboratory

<table>
    <thead>
        <tr>
            <th style="text-align:center">Sample</th>
            <th style="text-align:center">Image</th>
            <th style="text-align:center">Goal</th>
            <th style="text-align:center"><b>Methodology</b></th>
            <th style="text-align:center">Remarks</th>
        </tr>
        <tr>
            <th colspan="5" style="text-align:center">Reference</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="text-align:center">Lake sediment core</td>
            <td style="text-align:center">VNIR (HSI)</td>
            <td style="text-align:center">Comparison of watershed sample signals with EMs extracted from IHS data</td>
            <td style="text-align:center"><b>PPI+SAM</b></td>
            <td style="text-align:center">Assignment of extracted EMs using field signals</td>
        </tr>
        <tr>
            <td colspan="5" style="text-align:center">Van Exem, A., Debret, M., et al. (2019) New source-to-sink approach in an arctic catchment based on hyperspectral core-logging (Lake Linné, Svalbard). Quaternary Science Reviews 203: 128–140</td>
        </tr>
        <tr>
            <td style="text-align:center">Rock</td>
            <td style="text-align:center">VNIR+SWIR (HSI)</td>
            <td style="text-align:center">Comparison of pure sample signals with HSI spectra</td>
            <td style="text-align:center"><b>CMIM+SVM</b></td>
            <td style="text-align:center">CMIM reduces the number of EMs extracted on the basis of their similarity</td>
        </tr>
        <tr>
            <td colspan="5" style="text-align:center">Galdames, F.J., Perez, C.A., Estévez, P.A., Adams, M. (2019) Rock lithological classification by hyperspectral, range 3D and color images. Chemometrics and Intelligent Laboratory Systems 189: 138–148</td>
        </tr>
        <tr>
            <td style="text-align:center">Sedimentary rock</td>
            <td style="text-align:center">SWIR (HSI)</td>
            <td style="text-align:center">Extraction of rock EM for the creation of a library</td>
            <td style="text-align:center"><b>FCLS, SUnSAL, CLSUnSAL</b></td>
            <td style="text-align:center">Checking mineralogy with XRD</td>
        </tr>
        <tr>
            <td colspan="5" style="text-align:center">Bui, T., Orberger, B., et al. (2018) Building a Hyperspectral Library and its Incorporation into Sparse Unmixing for Mineral Identification. In: IGARSS 2018 - 2018 IEEE International Geoscience and Remote Sensing Symposium IEEE, 4261–4264.</td>
        </tr>
        <tr>
            <td style="text-align:center">Soil</td>
            <td style="text-align:center">ASTER (HSI)</td>
            <td style="text-align:center">Estimate the components on the soil</td>
            <td style="text-align:center"><b>ICA</b></td>
            <td style="text-align:center">Checking mineralogy with XRD</td>
        </tr>
        <tr>
            <td colspan="5" style="text-align:center">Ben Rabah, Z., Farah, I.R., Solaiman, B., Ben Ghzala, H. (2009) A New Spectral Unmixing Approach based on ICA and Spectral Angle Measure for Hyperspectral Images. 5th International Conference: Sciences of Electronic, Technologies of Information and Telecommunications 8</td>
        </tr>
        <tr>
            <td style="text-align:center">Soil</td>
            <td style="text-align:center">AVIRIS (HSI)</td>
            <td style="text-align:center">Estimating soil mineralogy</td>
            <td style="text-align:center"><b>RCMF, VCA, CLUnSAL</b></td>
            <td style="text-align:center">The sparse methods may not be relevant if the libraries are not in agreement with the acquired data.</td>
        </tr>
        <tr>
            <td colspan="5" style="text-align:center">Akhtar, N., Mian, A. (2017) RCMF: Robust Constrained Matrix Factorization for Hyperspectral Unmixing. IEEE Transactions on Geoscience and Remote Sensing 55: 3354–3366</td>
        </tr>
        <tr>
            <td style="text-align:center">Soil</td>
            <td style="text-align:center">VNIR+SWIR (HSI)</td>
            <td style="text-align:center">Estimation of soil mineralogy</td>
            <td style="text-align:center"><b>Mica</b></td>
            <td style="text-align:center">Comparison with the USGS library. Validation with consistent XRD data</td>
        </tr>
        <tr>
            <td colspan="5" style="text-align:center">Koerting, F., Rogass, C., et al. (2015) Drill core mineral analysis by means of the hyperspectral imaging spectrometer Hyspex, XRD and ASD in proximity of the Mýtina Maar, Czech Republic. ISPRS - International Archives of the Photogrammetry, Remote Sensing and Spatial Information Sciences XL-1-W5: 417–424</td>
        </tr>
    </tbody>
</table>

#### Remote sensing

<table>
    <thead>
        <tr>
            <th style="text-align:center">Sample</th>
            <th style="text-align:center">Image</th>
            <th style="text-align:center">Goal</th>
            <th style="text-align:center"><b>Methodology</b></th>
            <th style="text-align:center">Remarks</th>
        </tr>
        <tr>
            <th colspan="5" style="text-align:center">Reference</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="text-align:center">Bituminous soil</td>
            <td style="text-align:center">MIR + SWIR + LWIR (HSI + spectroscopy)</td>
            <td style="text-align:center">Determine the lithology of samples automatically</td>
            <td style="text-align:center"><b></b></td>
            <td style="text-align:center">Create a library with MIR to classify LWIR and SWIR pixels by co-registration.</td>
        </tr>
        <tr>
            <td colspan="5" style="text-align:center">Speta, M.A. (2016) Hyperspectral Imaging for the Characterization of Athabasca Oil Sands Core. Alberta.</td>
        </tr>
        <tr>
            <td style="text-align:center">Soil</td>
            <td style="text-align:center">AVIRIS (Airborne)</td>
            <td style="text-align:center">Estimation of soil mineralogy from drone and a library</td>
            <td style="text-align:center"><b>SAM+ANN</b></td>
            <td style="text-align:center"></td>
        </tr>
        <tr>
            <td colspan="5" style="text-align:center">Adep, R.N., Amba, S., Ramesh, H. (2017) EXhype: A tool for mineral classification using hyperspectral data. ISPRS Journal of Photogrammetry and Remote Sensing 124: 106–118</td>
        </tr>
        <tr>
            <td style="text-align:center">Soil</td>
            <td style="text-align:center">SWIR+LWIR (Airborne)</td>
            <td style="text-align:center">Estimation of soil mineralogy with the extraction of EMs with two sensors taken separately or together</td>
            <td style="text-align:center"><b>ISMA</b></td>
            <td style="text-align:center">Assignment with laboratory XRD data. By merging the two classification maps, more mineral information can be obtained.</td>
        </tr>
        <tr>
            <td colspan="5" style="text-align:center">Feng, J., Rogge, D., Rivard, B. (2018) Comparison of lithological mapping results from airborne hyperspectral VNIR-SWIR, LWIR and combined data. International Journal of Applied Earth Observation and Geoinformation 64: 340–353</td>
        </tr>
        <tr>
            <td style="text-align:center">Soil</td>
            <td style="text-align:center">AVIRIS (Airborne)</td>
            <td style="text-align:center">Comparison of EM extraction methods for characterizing soil mineralogy</td>
            <td style="text-align:center"><b>VCA, MVSA, MCR-ALS</b></td>
            <td style="text-align:center"></td>
        </tr>
        <tr>
            <td colspan="5" style="text-align:center">Zhang, X., Tauler, R. (2013) Application of Multivariate Curve Resolution Alternating Least Squares (MCR-ALS) to remote sensing hyperspectral imaging. Analytica Chimica Acta 762: 25–38</td>
        </tr>
        <tr>
            <td style="text-align:center">Soil</td>
            <td style="text-align:center">AVIRIS (Airborne)</td>
            <td style="text-align:center">Comparison of EM extraction methods for characterizing soil mineralogy</td>
            <td style="text-align:center"><b>VCA, N-FINDR, DFA</b></td>
            <td style="text-align:center"></td>
        </tr>
        <tr>
            <td colspan="5" style="text-align:center">Zhang, C., Qin, Q., Zhang, T., Sun, Y., Chen, C. (2017) Endmember extraction from hyperspectral image based on discrete firefly algorithm (EE-DFA). ISPRS Journal of Photogrammetry and Remote Sensing 126: 108–119</td>
        </tr>
        <tr>
            <td style="text-align:center">Soil</td>
            <td style="text-align:center">AVIRIS (Airborne)</td>
            <td style="text-align:center">Scene description from the estimation of EMs</td>
            <td style="text-align:center"><b>Local Rank + MCR-ALS</b></td>
            <td style="text-align:center">EM extraction taking into account the space environment with the local rank approach.</td>
        </tr>
        <tr>
            <td colspan="5" style="text-align:center">Zhang, X., de Juan, A., Tauler, R. (2016) Local rank-based spatial information for improvement of remote sensing hyperspectral imaging resolution. Talanta 146: 1–9</td>
        </tr>
        <tr>
            <td style="text-align:center">Soil</td>
            <td style="text-align:center">LIR (Airborne)</td>
            <td style="text-align:center">Determination of discriminating spectral regions</td>
            <td style="text-align:center"><b></b></td>
            <td style="text-align:center"></td>
        </tr>
        <tr>
            <td colspan="5" style="text-align:center">Hecker, C., van Ruitenbeek, F.J.A., Bakker, W.H., Fagbohun, B.J., Riley, D., van der Werff, H.M.A., van der Meer, F.D. (2019) Mapping the wavelength position of mineral features in hyperspectral thermal infrared data. International Journal of Applied Earth Observation and Geoinformation 79: 133–140</td>
        </tr>
    </tbody>
</table>

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

### References

#### Lamina detection

<table>
    <thead>
        <tr>
            <th style="text-align:center">Sample</th>
            <th style="text-align:center">Image</th>
            <th style="text-align:center"><b>Methodology</b></th>
            <th style="text-align:center">Remarks</th>
        </tr>
        <tr>
            <th colspan="4" style="text-align:center">Reference</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="text-align:center">Sediment core</td>
            <td style="text-align:center">X-ray</td>
            <td style="text-align:center"><b>Maxima and Minima detections</b></td>
            <td style="text-align:center">Detection from 3 pixels minimum. Count on the whole picture, but estimates an average variation</td>
        </tr>
        <tr>
            <td colspan="4" style="text-align:center">Damci, E., Çağatay, M.N. (2016) An automated algorithm for dating annually laminated sediments using X-ray radiographic images, with applications to Lake Van (Turkey), Lake Nautajarvi (Finland) and Byfjorden (Sweden). Quaternary International 401: 174–183</td>
        </tr>
        <tr>
            <td style="text-align:center">Sediment core</td>
            <td style="text-align:center">RGB</td>
            <td style="text-align:center"><b>Detection of maxima (year) or grey level 0 (season) shifts to 0 (season)</b></td>
            <td style="text-align:center">Average one line with a few neighbors, then cross over to the gray level. Calculate also the thickness of the laminates.</td>
        </tr>
        <tr>
            <td colspan="4" style="text-align:center">Weber, M.E., Reichelt, L., Kuhn, G., Pfeiffer, M., Korff, B., Thurow, J., Ricken, W. (2010) BMPix and PEAK tools: New methods for automated laminae recognition and counting-Application to glacial varves from Antarctic marine sediment. Geochemistry, Geophysics, Geosystems 11:</td>
        </tr>
        <tr>
            <td style="text-align:center">Sedimentary rock core</td>
            <td style="text-align:center">Gray level</td>
            <td style="text-align:center"><b>Wavelet transform, gradient edge detection, Hough transform</b></td>
            <td style="text-align:center">Segmenting laminates and estimating their deformation.</td>
        </tr>
        <tr>
            <td colspan="4" style="text-align:center">Quiniou, T., Selmaoui, N., Laporte-Magoni, C., Allenbach, M. (2007) Calculation of Bedding Angles Inclination from Drill Core Digital Images. MVA2007 IAPR Conference on Machine Vision Applications 252–255</td>
        </tr>
        <tr>
            <td style="text-align:center">Laminated samples</td>
            <td style="text-align:center">RGB</td>
            <td style="text-align:center"><b>Detection of minima and maxima</b></td>
            <td style="text-align:center">The user defines the calculation area(s).</td>
        </tr>
        <tr>
            <td colspan="4" style="text-align:center">Meyer, M.C., Faber, R., Spö Tl, C. (2006) The WinGeol Lamination Tool : new software for rapid, semi - automated analysis of laminated climate archives. The Holocene 16: 753–761</td>
        </tr>
        <tr>
            <td style="text-align:center">Sedimentary rock core</td>
            <td style="text-align:center">RGB</td>
            <td style="text-align:center"><b>Fourier or Wavelet Transform</b></td>
            <td style="text-align:center"></td>
        </tr>
        <tr>
            <td colspan="4" style="text-align:center">Selmaoui, N., Repetti, B., Laporte-Magoni, C., Allenbach, M. (2004) Image analysis for core geological descriptions: strata and granulometry detection. In: Proceedings of the 17th International Conference on Pattern Recognition IEEE, 305-310 Vol.4.</td>
        </tr>
        <tr>
            <td style="text-align:center"></td>
            <td style="text-align:center">RGB</td>
            <td style="text-align:center"><b>Hilbert transform for detecting gray level maxima and minima</b></td>
            <td style="text-align:center"></td>
        </tr>
        <tr>
            <td colspan="4" style="text-align:center">Rupf, I., Radons, G. (2004) New approaches for automated data processing of annually laminated sediments. Nonlinear Processes in Geophysics 11: 599–607</td>
        </tr>
    </tbody>
</table>

#### Grain size estimation

<table>
    <thead>
        <tr>
            <th style="text-align:center">Sample</th>
            <th style="text-align:center">Image</th>
            <th style="text-align:center"><b>Methodology</b></th>
            <th style="text-align:center">Remarks</th>
        </tr>
        <tr>
            <th colspan="4" style="text-align:center">Reference</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="text-align:center">Composite sediments</td>
            <td style="text-align:center">RGB</td>
            <td style="text-align:center"><b>Autocorrelation on greyscale image</b></td>
            <td style="text-align:center"></td>
        </tr>
        <tr>
            <td colspan="4" style="text-align:center">Cheng, Z., Liu, H. (2015) Digital grain - size analysis based on autocorrelation algorithm. Sedimentary Geology 21–31</td>
        </tr>
        <tr>
            <td style="text-align:center">Sediments</td>
            <td style="text-align:center">RGB</td>
            <td style="text-align:center"><b>Wavelet transform and its spectral density</b></td>
            <td style="text-align:center"></td>
        </tr>
        <tr>
            <td colspan="4" style="text-align:center">Buscombe, D. (2013) Transferable wavelet method for grain-size distribution from images of sediment surfaces and thin sections, and other natural granular patterns. International Association of Sedimentologists</td>
        </tr>
        <tr>
            <td style="text-align:center">Sediments</td>
            <td style="text-align:center">RGB</td>
            <td style="text-align:center"><b>Gradient and thresholding</b></td>
            <td style="text-align:center">Greyscale normalization and equalization</td>
        </tr>
        <tr>
            <td colspan="4" style="text-align:center">Baptista, P., Cunha, T.R., Gama, C., Bernardes, C. (2012) A new and practical method to obtain grain size measurements in sandy shores based on digital image acquisition and processing. Sedimentary Geology</td>
        </tr>
        <tr>
            <td style="text-align:center">Sediments</td>
            <td style="text-align:center">RGB</td>
            <td style="text-align:center"><b>Watershed</b></td>
            <td style="text-align:center"></td>
        </tr>
        <tr>
            <td colspan="4" style="text-align:center">Lewis, T., Francus, P., Bradley, R.S., Kanamaru, K. (2010) An Automated System for the Statistical Analysis of Sediment Texture and Structure at the Micro Scale</td>
        </tr>
        <tr>
            <td style="text-align:center">Sediments</td>
            <td style="text-align:center">RGB</td>
            <td style="text-align:center"><b>Autocorrelation</b></td>
            <td style="text-align:center"></td>
        </tr>
        <tr>
            <td colspan="4" style="text-align:center">Warrick, J.A., Rubin, D.M., Ruggiero, P., Harney, J.N., Draut, A.E., Buscombe, D. (2009) Cobble cam: grain-size measurements of sand to boulder from digital photographs and autocorrelation analyses. Earth Surface Processes and Landforms 34: 1811–1821</td>
        </tr>
        <tr>
            <td style="text-align:center">Sediments</td>
            <td style="text-align:center">RGB</td>
            <td style="text-align:center"><b>Autocorrelation</b></td>
            <td style="text-align:center"></td>
        </tr>
        <tr>
            <td colspan="4" style="text-align:center">Buscombe, D. (2008) Estimation of grain-size distributions and associated parameters from digital images of sediment. Sedimentary Geology 210: 1–10</td>
        </tr>
        <tr>
            <td style="text-align:center">Sediments</td>
            <td style="text-align:center">RGB</td>
            <td style="text-align:center"><b>Autocorrelation</b></td>
            <td style="text-align:center"></td>
        </tr>
        <tr>
            <td colspan="4" style="text-align:center">Barnard, P.L., Rubin, D.M., Harney, J., Mustain, N. (2007) Field test comparison of an autocorrelation technique for determining grain size using a digital ’ beachball ’ camera versus traditional methods. Sedimentary Geology 180–195</td>
        </tr>
        <tr>
            <td style="text-align:center">Fragmented rocks</td>
            <td style="text-align:center">RGB</td>
            <td style="text-align:center"><b>Gradient and Watershed</b></td>
            <td style="text-align:center"></td>
        </tr>
        <tr>
            <td colspan="4" style="text-align:center">Outal, S. (2006) Quantification Par Analyse d’images de La Granulométrie Des Roches Fragmentées : Amélioration de l’extraction Morphologique Des Surfaces, Amélioration de La Reconstruction Stéréologique. École Nationale Supérieure des Mines de Paris.</td>
        </tr>
        <tr>
            <td style="text-align:center">Sediments</td>
            <td style="text-align:center">RGB</td>
            <td style="text-align:center"><b>Top Hat and Watershed</b></td>
            <td style="text-align:center">On grayscale image</td>
        </tr>
        <tr>
            <td colspan="4" style="text-align:center">Graham, Rice, D.J., Reid, I. (2005) Automated sizing of coarse-grained sediments : image-processing procedures. Mathematical Geology 37: 1–28</td>
        </tr>
        <tr>
            <td style="text-align:center">Sediments</td>
            <td style="text-align:center">RGB</td>
            <td style="text-align:center"><b>Autocorrelation</b></td>
            <td style="text-align:center"></td>
        </tr>
        <tr>
            <td colspan="4" style="text-align:center">Rubin, D.M. (2004) A simple autocorrelation algorithm for determining grain size from digital images of sediment. Journal of Sedimentary Research 74: 160–165</td>
        </tr>
        <tr>
            <td style="text-align:center">Sediments</td>
            <td style="text-align:center">RGB</td>
            <td style="text-align:center"><b>H-maxima</b></td>
            <td style="text-align:center">On grayscale image</td>
        </tr>
        <tr>
            <td colspan="4" style="text-align:center">Selmaoui, N., Repetti, B., Laporte-Magoni, C., Allenbach, M. (2004) Coupled strata and granulometry detection on indurated cores by gray-level image analysis. Geo-Marine Letters 24: 241–251</td>
        </tr>
        <tr>
            <td style="text-align:center">Sediments, Rocks</td>
            <td style="text-align:center">RGB on microscope</td>
            <td style="text-align:center"><b>Threshold then detection</b></td>
            <td style="text-align:center"></td>
        </tr>
        <tr>
            <td colspan="4" style="text-align:center">Francus, P. (1998) An image-analysis technique to measure grain-size variation in thin sections of soft clastic sediments. Sedimentary Geology 121: 289–298</td>
        </tr>
    </tbody>
</table>