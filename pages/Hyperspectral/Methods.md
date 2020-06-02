---
title: Methods
description: Methods
permalink: Methods_HSI.html
---

Description soon

![Worflow](/images/Worflow.jpg)

# Les méthodes univariées ou multi-longueurs d'onde

Une première approche pour extraire des informations à partir de données spectrales est de chercher des zones caractéristiques correspondant à une ou quelques longueur(s) d'onde. On parle dans ce cas d'approches univariées avec une approche spectrale locale plutôt que globale.
Les énergies d'absorption ou d'excitation dans les gammes présentées précédemment sont quantifiées à des niveaux d'énergie connues. Il est donc possible de créer des tables qui référencent les composés ou liaisons chimiques associées à ces énergies ou longueurs d'onde. Comme c'est le cas avec les spectroscopies moyen-infrarouge, la fluorescence UV-visible ou des rayons X. Dans certaines gammes cela est compliqué à réaliser du fait de la superposition de nombreuses propriétés et de la résolution spectrale des capteurs, comme en spectroscopie proche-infrarouge.
Il faut tout de même utiliser ces indices avec précaution, car plusieurs composés chimiques peuvent interagir dans les mêmes zones spectrales et la résolution spectrale peut ne pas être suffisamment fine pour distinguer ces composés. Il existe aussi de nombreux indices développés en télédétection pour des données RGB ou multispectrales, mais qui sont très peu utilisés en spectroscopie de laboratoire, car l'information recherchée n'est pas la même.
Ces indices sont semi-quantitatifs et peuvent etre calibrés par la suite à partir de modèles de régression en estimant un lien avec une méthode analytique de référence. On parle de la régression linéaire simple (RLS) qui estime une relation entre une variable expliquée ($y$, analytique) et une variable explicative ($x$, spectral).

# Les régressions multivariées
Plutôt que d'étudier des zones spectrales spécifiques pour un composé ou une liaison chimique, des approches globales qui utilisent l'ensemble du spectre ont été développées et se nomment méthodes multivariées. Une information bio-physico-chimique peut se retrouver dans différentes zones du spectre, elle peut aussi être en lien avec un autre composé corrélé, ou au contraire perturbé par un autre. Ces méthodes globales peuvent ainsi retrouver toutes ces informations ce qui permet de créer des modèles de prédictions performants.
		
Les principales méthodes de régression que l'on trouve dans la littérature ou qui se développent sont présentées ci-dessous et peuvent être schématisées avec la figure \ref{fig:multi}. Davantage d'informations sont disponibles dans le livre de Tufféry \cite{Tuffery2012}. 

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