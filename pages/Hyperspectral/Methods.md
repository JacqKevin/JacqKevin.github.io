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

{% include image.html file="Multi.jpg" %}

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

## L'estimation de signaux purs

A partir des données spectroscopiques, on peut obtenir des empreintes chimiques de composés si l'échantillon est pur et homogène, comme celle du minéral Illite de la figure \ref{fig:zonesdiscri}. Dans le cas d'images multi- ou hyper-spectrales, c'est l'inhomogénéité de l'échantillon qui est étudiée, et est ensuite caractérisée à travers les différents composés qu'il contient en estimant des signaux purs, aussi appelés endmembers (EM) \cite{Bioucas-Dias2012,Keshava2003}. On parle de méthodes de démélange pour l'extraction de signaux purs. Il existe trois groupes principaux de méthodes pour estimer ces signaux purs :

<ul>
<li> Les méthodes dites géométriques se basent sur la possibilité de trouver une forme géométrique qui encadrent l'ensemble des données. </li>
<ul>
{% include image.html file="EM.jpg" %}
<li> Le principe standard repose sur l'hypothèse qu'un signal spectroscopique est la somme de sous-signaux correspondant à des constituants de l'échantillon. De nombreuses méthodes existent et peuvent être décrites comme la détermination d'un simplexe (triangle à n-dimensions) qui englobe toutes les données, et ses extrémités correspondent aux EMs. Les méthodes les plus connues sont l'indice de pureté du pixel (PPI) \cite{Boardman1993}, N-FINDR \cite{Winter1999}, Vertex Component Analysis (VCA) \cite{Nascimento2005}. </li>
<li> On peut aussi utiliser l'hypothèse inverse, c'est à dire trouver dans le cas d'un échantillon globalement homogène, des pixels différents de la majorité. Avec un calcul des distances, on peut les mettre en avant. Comme par exemple, l'algorithme de Kennard et Stone \cite{Kennard1969} est utilisé pour trouver les spectres les plus différents dans un jeu de données. </li>
</ul>
<li> Les méthodes dites statistiques ou séparation de sources à l'aveugle sont utilisées lorsque les signaux purs sont très mélangés dans chaque pixel. C'est à dire que chaque pixel de l'IHS est constitué de plusieurs sources. Les méthodes géométriques ne sont pas assez performantes dans ce cas pour trouver des pôles représentatifs de la réalité. Alors que les méthodes statistiques, via un temps de calcul plus important, peuvent les estimer. On peut citer les méthodes : Analyse en Composantes Indépendantes (ICA) \cite{Comon1994,Rutledge2013} et Multivariate Curve Resolution Alternating Least Square (MCR-ALS) \cite{Jaumot2015} qui sont utilisées dans différentes études. </li>
<li> Enfin, on trouve les méthodes parcimonieuses ou sparse qui utilisent les connaissances sur les échantillons grâce à des librairies ou spectres purs. Ces méthodes vont estimer la proportion de ces signatures dans chacun des spectres. Par exemple, on trouve les algorithmes : Fully Constrained Least Squares (FCLS) \cite{Heinz2001}, Sparse Unmixing by Variable Splitting and Augmented Lagrangian (SUnSAL) \cite{Bioucas-Dias2010}. </li>
</ul>

Ensuite ces EMs permettent d'estimer leurs abondances dans chacun des spectres à partir d'un calcul de similarité sur la base d'une distance. Dans le cas d'une image, ceci permet d'estimer une carte d'abondance de ces EMs et ainsi voir leurs variations.
		
Ces signaux purs sont souvent comparés à des librairies ou à des spectres d'échantillon pur pour les caractériser. Plusieurs librairies existent, comme celles de l'USGS \cite{Kokaly2017}, CSIRO \cite{Lau2017}, ECOSTRESS \cite{Meerdink2019}, ou encore d'autres intégrées dans des logiciels commerciaux (ENVI).

Ces méthodes sont très utilisées en télédétection pour discriminer les principales entités (routes, bâtiments, forêts, rivières) ou la géologie au sol avec des données multi- et hyper-spectrales. Elles sont aussi très utilisées pour caractériser les minéraux présents dans des échantillons géologiques, comme les carottes sédimentaires et ainsi déterminer l'origine des sédiments. L'annexe \ref{SyntheseBiblioEM}, avec les tableaux \ref{tab:RecapEM1} et \ref{tab:RecapEM2}, récapitulent quelques exemples d'applications de ce type de méthode pour l'analyse des échantillons environnementaux.

## La segmentation des images

Une image porte des informations sur les structures composant une scène ou un échantillon. Des méthodes existent pour les caractériser, on parle de segmentation. Elles peuvent être regroupées dans deux familles :
<ul>
<li> Les méthodes géométriques qui estiment à partir d'opérateur morphologique des structures dans l'image. </li>
<ul>
<li> Les lamines peuvent être détectées grâce à des maxima ou minima d'intensité avec des méthodes comme H-maxima, ou encore la méthode de la ligne de partage des eaux \cite{Vincent1991} qui considère une image comme un relief topographique et qui va détecter les limites de ceux-ci en "inondant" l'image. Si les lamines pouvaient être caractérisées par des gammes de couleurs, on pourrait effectuer un seuillage à plusieurs niveaux, mais comme les couleurs varient le long de l'échantillon, il faudrait envisager un seuillage adaptatif pour extraire chaque lamine \cite{Zuiderveld1994}. Il est également possible de détecter les limites de lamines, qui sont des ruptures plus ou moins nettes, avec des dérivées ou des gradients, ou en modélisant la limite avec la transformée de Hough \cite{Hough1959,Duda1972} par exemple. La détection des lamines est souvent réalisée avec un signal 1D le long de l'échantillon, car il peut être suffisamment informatif s'il n'est pas très bruité. Dans le cas contraire, il est possible de multiplier les signaux 1D avec du recouvrement puis de les ré-associer. On peut également utiliser la totalité de l'image, mais souvent les lamines ne sont pas caractérisables sur toute la largeur de l'échantillon, il faut donc rassembler les différents "morceaux" pour la reconstituer, ce qui n'est pas une tâche aisée. Les travaux de Gan \cite{Gan2013} sur le sujet, propose d'utiliser les opérateurs morphologiques de base comme l'érosion et la dilatation pour rattacher ou séparer ces zones (figure \ref{fig:erosiondilation}). </li>
<li> Pour la granulométrie, les méthodes sont similaires avec la détection des ruptures entre les grains grâce à des gradients ou la ligne de partage des eaux. </li>
</ul>
<li> Les méthodes statistiques qui estiment des similarités ou tendances dans l'image.  </li>
<ul>
<li> Dans le cas de la détection de lamines qui sont des phénomènes redondants et périodiques, on peut utiliser des approches basées sur la transformée de Fourier ou sur les ondelettes. </li>
<li> Pour l'estimation de la granulométrie, l'approche la plus utilisée est basée sur l'autocorrélation qui estime les dépendances internes dans l'image, puisque les pixels voisins d'une même particule sont dépendants. </li>
</ul>
</ul>

## Les méthodes de classification

Les données peuvent aussi être regroupées de manière qualitative, on parle de classification ou de reconnaissance de formes. On peut avoir des connaissances partielles des données et les utiliser, on parle de classification supervisée ou discrimination qui permettent d'estimer par exemple : la présence ou l'absence d'un composé, ou des niveaux d'abondances haut-moyen-élevé. Dans le cas de données inconnues, on parle de classification non-supervisée ou clustering. Ces méthodes peuvent s'appliquer aussi bien sur la dimension spatiale que spectrale.

{% include image.html file="classif.jpg" %}

### Les méthodes non supervisées (clustering)

<ul>
<li> L'Analyse en Composantes Principales (ACP) permet de réduire les données et ainsi de visualiser rapidement leurs principales variabilités. Une approche similaire appelée Minimum Noise Fraction (MNF) permet de garder les composantes les plus informatives et les moins bruitées. </li>
<li> Les méthodes des K-moyennes (K-means) ou des K-médianes (K-medoids) estiment des centres représentatifs d'un nombre K de groupes \cite{Steinhaus1956}. Une méthode avancée utilisant des règles floues a été développée, C-moyennes floues (FCM) \cite{Dunn1973}. </li>
<li> Les classifications hiérarchiques se divisent en deux familles, celles qui agglomèrent (classification ascendante hiérarchique CAH) et celles qui divisent (classification descendante hiérarchique CDH) \cite{Ward1963}. Dans le cas de la CAH, les données sont agglomérées de proche en proche suivant un critère de distance jusqu'à obtenir un groupe unique, et inversement pour la CDH. Le résultat est un dendrogramme qui peut être coupé à un certain niveau définissant le nombre de groupes. </li>
</ul>

### Les méthodes supervisées (discrimination)

<ul>
<li> La méthode des K plus proches voisins (KNN) est une méthode non paramétrique qui estime une probabilité d’appartenance à un groupe suivant une règle, qui est ici la distance avec les individus environnants \cite{Hart1968}. Elle calcule la distance entre un échantillon « inconnu » avec tous ceux connus. Puis ce nouvel échantillon est classé dans un groupe avec ses K voisins les plus proches. Il existe plusieurs approches pour améliorer ces prédictions, comme rajouter des règles floues avec la méthode KNN-floue \cite{Keller1985}, ou utiliser la théorie des fonctions de croyance EkNN (Evidential KNN) \cite{Denoeux1995,Shafer1976}. </li>
<li> L'analyse linéaire discriminante (LDA) cherche l’axe permettant de séparer au mieux les groupes \cite{Fisher1936}. On peut y voir une correspondance avec l’ACP et la PLS. Elle peut utiliser des fonctions non linéaires, comme avec l'Analyse Discriminante Quadratique. Une approche similaire appelée PLS-DA (discriminant analysis). </li>
<li> Les arbres de décision (DT) sont des méthodes non paramétriques qui reposent sur la création d’un arbre de décision à choix binaire \cite{Breiman1984}. Pour une variable explicative l’algorithme va déterminer des règles pour séparer un ou des groupes. À la fin de celui-ci un ensemble de règles sur plusieurs variables est créé, et cela forme un arbre, où l'on trouve au niveau d’un nœud la décision binaire et au niveau des feuilles la classe estimée. Un apprentissage avec plusieurs arbres de décision permet de créer une forêt d'arbres décisionnels (RF) \cite{TinKamHo1995}, puis les règles majoritaires sont conservées. </li>
<li> Les réseaux profonds, comme on a pu le dire précédemment, sont composés de plusieurs couches constitués d'un nombre souvent important de neurones \cite{Ivakhnenko1965,Schmidhuber2015}. Ces méthodes sont très utilisées dans le cas d'apprentissage d'images. En effet, elles vont les représenter grâce à leurs compositions, comme les niveaux d'intensité, les structures finies (arêtes d'un objet) et grossières (une région, une forme, un objet). On parle ici d'apprentissage à différents niveaux d'abstraction qui est fonction de la profondeur du réseau. </li>
<li> Des méthodes de régression présentées précédemment peuvent aussi servir en classification : PLS-DA (discriminant analysis), MARS, SVM, ANN.  </li>
</ul>

Du fait de la complexité des données multi- et hyper-spectrale, ce sont principalement des méthodes non linéaires (SVM, ANN, CNN) qui sont employées pour classifier chaque pixel à partir de zones labellisées. Afin de réduire cette complexité et le temps de calcul, deux propositions de traitement sont utilisées. Certains réduisent les données avec des algorithmes de démélange (VCA, ICA). D'autres utilisent la dimension spatiale avec les pixels voisins autour du pixel à classifier.