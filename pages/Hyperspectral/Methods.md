---
title: Methods
description: Methods
permalink: Methods_HSI.html
---

Description soon

![Worflow](/images/Worflow.jpg)

## Les méthodes semi-quantitatives

Une première approche pour extraire des informations à partir de données spectrales est de chercher des zones caractéristiques correspondant à une ou quelques longueur(s) d'onde. On parle dans ce cas d'approches univariées avec une approche spectrale locale plutôt que globale.
Les énergies d'absorption ou d'excitation dans les gammes présentées précédemment sont quantifiées à des niveaux d'énergie connues. Il est donc possible de créer des tables qui référencent les composés ou liaisons chimiques associées à ces énergies ou longueurs d'onde. Comme c'est le cas avec les spectroscopies moyen-infrarouge, la fluorescence UV-visible ou des rayons X. Dans certaines gammes cela est compliqué à réaliser du fait de la superposition de nombreuses propriétés et de la résolution spectrale des capteurs, comme en spectroscopie proche-infrarouge.
Il faut tout de même utiliser ces indices avec précaution, car plusieurs composés chimiques peuvent interagir dans les mêmes zones spectrales et la résolution spectrale peut ne pas être suffisamment fine pour distinguer ces composés. Il existe aussi de nombreux indices développés en télédétection pour des données RGB ou multispectrales, mais qui sont très peu utilisés en spectroscopie de laboratoire, car l'information recherchée n'est pas la même.
Ces indices sont semi-quantitatifs et peuvent etre calibrés par la suite à partir de modèles de régression en estimant un lien avec une méthode analytique de référence. On parle de la régression linéaire simple (RLS) qui estime une relation entre une variable expliquée ($y$, analytique) et une variable explicative ($x$, spectral).

## Les méthodes quantitatives
Plutôt que d'étudier des zones spectrales spécifiques pour un composé ou une liaison chimique, des approches globales qui utilisent l'ensemble du spectre ont été développées et se nomment méthodes multivariées. Une information bio-physico-chimique peut se retrouver dans différentes zones du spectre, elle peut aussi être en lien avec un autre composé corrélé, ou au contraire perturbé par un autre. Ces méthodes globales peuvent ainsi retrouver toutes ces informations ce qui permet de créer des modèles de prédictions performants.
		
Les principales méthodes de régression que l'on trouve dans la littérature ou qui se développent sont présentées ci-dessous et peuvent être schématisées avec la figure \ref{fig:multi}. Davantage d'informations sont disponibles dans le livre de Tufféry \cite{Tuffery2012}. 

{% include image.html file="Multi.jpg" %}

<ul>
<li> Les méthodes linéaires : </li>
<ul>
<li> La régression linéaire multiple (RLM) est similaire à la RLS, la différence réside dans la multitude de variables explicatives ($X$) qui correspondent à une donnée spectrale à plusieurs longueurs d'onde. </li>
<li> La régression sur composantes principales (PCR) \cite{Jolliffe1982} est une RLM qui utilise comme variables explicatives les composantes principales ($PC$) de l'analyse en composantes principales (ACP) \cite{Pearson1901}. Les PCs correspondent aux regroupements des variables explicatives $X$ portant des informations similaires. L'ACP permet ainsi de réduire la taille des données spectrales en regroupant les $X$ corrélées. L'ACP calcule un nouveau repère géométrique, différent de l'espace spectral, qui est orienté suivant des axes indépendants expliquant la variabilité des données explicatives. </li>
<li> La régression des moindres carrés partiels (PLSR) \cite{Wold1984} (qui peut également être non linéaire). La régression PLS estime des variables latentes (VLs) qui correspondent aux regroupements des variables explicatives $X$ liées à celles à expliquer $Y$. Elle estime donc aussi un nouveau repère géométrique, qui s'oriente suivant des axes indépendants qui expliquent la variabilité des données explicatives $X$ tout en maximisant la corrélation entre $X$ et $Y$. C'est une des méthodes les plus utilisées en traitement de données spectroscopiques (chimiométrie). </li>
</ul>
<li> Les méthodes non linéaires : </li>
<ul>
<li> La régression multivariée par spline adaptative (MARS) \cite{Friedman1991} permet de modéliser des non-linéarités grâce à des règles, on parle d'une méthode non-paramétrique. Pour cela, elle utilise des partitionnements récursifs pour estimer des sous-zones pouvant être modélisées par des fonctions linéaires. Un modèle MARS peut donc être représenté par une succession de règles conduisant à des modèles linéaires terminaux. </li>
<li> Les machines à vecteurs de support (SVM) \cite{Vapnik1998} utilisent un espace de grandes dimensions pour estimer un hyperplan (n>2) linéaire afin de répondre à un problème non linéaire. L'hyperplan linéaire estimé subit ensuite une transformation inverse pour revenir dans l'espace initiale non-linéaire. </li>
<li> Les réseaux de neurones artificiels (ANN) \cite{McCulloch1943,Rosenblatt1958} cherche à reproduire la capacité du cerveau à apprendre. Cette méthode repose sur un ensemble d’unités fondamentales interconnectées, les neurones. Un réseau est un ensemble de couches de neurones qui fonctionne, les unes à la suite des autres. Chaque neurone reçoit une partie des informations qu’il traite et il communique les résultats avec ses plus proches voisins de la couche de neurones suivante. Le réseau le plus simple comporte trois couches, une d'entrée, une de calcul ou couche cachée et une couche de sortie. </li>
<li> Les réseaux d'apprentissage profond sont des méthodes qui se développent dans tous les domaines et aussi récemment en analyse de données spectroscopiques. C'est une méthode proche de l'ANN, la différence est que le réseau profond comporte plusieurs couches cachées et un nombre de neurones souvent important \cite{Ivakhnenko1965,Schmidhuber2015}. </li>
</ul>
</ul>
D'un point de vue mathématique, on fait la différence entre un vecteur avec une lettre minuscule ($x$,$y$) et une matrice avec une lettre majuscule ($X$,$Y$). 

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