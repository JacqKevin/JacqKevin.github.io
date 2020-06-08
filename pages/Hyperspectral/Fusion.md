---
title: Fusion
description: Fusion toolboxes
permalink: Fusion_HSI.html
---

Comme on a pu le voir, chaque domaine spectral apporte des informations bio-physico-chimiques qui lui sont propres et qui peuvent se retrouver dans d'autres. C'est pourquoi combiner différents jeux de données de plusieurs domaines spectraux est intéressant pour améliorer la caractérisation des échantillons. En fonction du type de capteur, les méthodes employées sont différentes, c'est pourquoi cette section est divisée en deux parties qui traitent de la fusion d'image (2D) et de signaux (1D).

<center>
{% include image.html file="Fusion_Methods.jpg" %}
</center>
		
Les méthodes de fusion d'image doivent pallier deux principales difficultés, (1) la modification de la surface des échantillons entre les acquisitions et (2) la non-homogénéité des résolutions. Ce sont des questions qui sont principalement étudiées dans les domaines de la télédétection (étude des terrains) et du médical (diagnostic plus complet d'un patient) pour agglomérer des données multicapteurs. Le domaine de la chimie analytique commence aussi à s'y intéresser en s'inspirant des méthodes développées dans ces deux domaines \cite{DeJuan2019, DeJuan2018}. 

## Image fusion

### Fusion at high resolution

L'homogénéisation des résolutions (2) peut être effectuée à plusieurs niveaux. Soit à la plus basse des résolutions, ce qui est effectué lors de l'étape de recalage (1), on peut parler de fusion à basse résolution, qui correspond à une combinaison des jeux de données. Soit on utilise des approches de fusion avancées pour une fusion à haute résolution. Ces méthodes peuvent être regroupées en trois familles suivant le type d'information fusionnée \cite{Dasarathy1997,Martin2005,Ghassemian2016}. Elles peuvent être représentées par la figure \ref{fig:fus}.

<center>
{% include image.html file="Fus.jpg" %}
</center>

<ul>
<li> La fusion de bas niveau ou au niveau pixel consiste à fusionner les informations brutes après l'acquisition, ainsi toutes les informations sont retenues. Ensuite, le capteur composite est prétraité avant la création d'un modèle prédictif quantitatif ou qualitatif. </li>
<li>  La fusion de niveau moyen ou au niveau des attributs représente la fusion des données initiales réduites, comme par exemple avec une ACP, ou des méthodes de démélange, ou de segmentation. Ceci permet de garder des informations globales sur l'échantillon, et d'enlever le bruit, ainsi que potentiellement des informations locales si des vérifications ne sont pas effectuées. Enfin, un modèle quantitatif ou qualitatif est créé.  </li>
<li>  La fusion de haut niveau ou au niveau décision consiste en la fusion de données extraites des données initiales, comme par exemple avec les méthodes d'apprentissage automatique ou de régression. Chaque capteur est donc prétraité, puis un modèle quantitatif ou qualitatif est créé pour estimer des cartes d'abondance ou de classification qui sont ensuite fusionnées. Dans le cas, de l'étude d'une unique propriété, il faut s'assurer que des informations discriminantes soient disponibles dans chacun des capteurs.  </li>
</ul>

Dans le cas des données spectroscopiques, comme on a pu le voir les gammes spectrales ne portent pas toujours des informations similaires. C'est pourquoi la fusion de haut niveau est intéressante pour la fusion de cartes de classification de variables différentes et complémentaires. Comme par exemple pour estimer la minéralogie d'un échantillon sédimentaire qui sont caractérisables avec différentes gammes spectrales qui portent des informations majoritaires. Mais dans le cas d'une même variable entre différents capteurs, cela a peu d'intérêt si certains de ces capteurs portent des informations minoritaires qui ne peuvent permettre une modélisation correcte. 

Il se peut tout de même que des informations minoritaires sur une variable d'intérêt soient contenues dans certaines gammes spectrales, et que leur fusion avec une gamme spectrale portant des informations plus nombreuses, soit bénéfique pour augmenter les performances de modélisation. C'est pourquoi les méthodes de fusion au niveau pixel sont intéressantes et seront mieux détaillées par la suite \cite{Yokoya2017,Li2017,Loncan2015,Vivone2015}. En effet, celles-ci peuvent être regroupées dans quatre familles que l'on peut schématiser avec la figure \ref{fig:recap}. Les deux premières familles ont été créées pour la fusion de données multispectrales avec une image panchromatique (similaire à une image en niveau de gris), c'est pourquoi ces méthodes sont appelées pansharpening. Elles ont ensuite été modifiées pour la fusion de données multi- et hyper-spectrales, on parle d'hypersharpening.

<center>
{% include image.html file="recap.jpg" %}
</center>

<ul>
<li> La substitution de composantes (CS) consiste à projeter les données basses (BR) et hautes (HR) résolutions dans un autre espace qui sépare les informations spatiales et spectrales.  Ensuite, ces méthodes vont estimer les composantes BR qui sont les plus proches de celles à HR pour les substituer. Les méthodes les plus utilisées sont l'ACP \cite{Chavez1991}, l'ICA, Intensity-Hue-Saturation (IHS) \cite{Tu2001}, Brovey transform (BT) \cite{Gillespie1987}, Gram-Schmidt (GS) \cite{Laben2000,Aiazzi2007}. </li>
<li>  L'analyse multirésolution (MRA) décompose les données BR et HR à plusieurs niveaux de résolution similaires en utilisant des ondelettes \cite{Khan2008,Vivone2014,Ranchin2000,Otazu2005} ou des pyramides laplaciennes \cite{Aiazzi2006,Aiazzi2003,Aiazzi2002,Lee2004,Alparone2007} ou gaussiennes. Ensuite, des modèles de passage sont calculés entre ces différentes résolutions pour estimer les hautes et basses fréquences (aussi appelées détails et structures) manquantes dans les données BR interpolées à HR.  </li>
<li>  Les méthodes qui utilisent des sous espaces sont appelées méthodes sparses, car elles utilisent les méthodes de démélange \cite{Yokoya2011a}. Les données BR et HR sont synthétisées à travers des composantes pures (endmembers) qui peuvent se retrouver entre les deux jeux de données. Cela permet de reconstruire le cube BR à HR.  </li>
<li>  Les méthodes de régression créent un modèle liant les différentes bandes spectrales entre les données BR et HR réduite à la BR, pour ensuite l'appliquer à haute résolution pour la prédiction du cube BR à HR \cite{DeJuan2019}. </li>
</ul>

De nouvelles méthodes émergent avec l'utilisation d'approches bayésiennes \cite{YifanZhang2009} ou de réseaux d'apprentissage profond \cite{Liu2018,Dian2018,Shao2018}.

### Fusion at low resolution

Pour corriger les déformations de surface des échantillons entre les acquisitions (1), il faut recaler les images. Dans le cas d'image de télédétection, cela est plutôt simple grâce au georéférencement des pixels. Dans le cas d'image de laboratoire, le plus simple et de les coréférencer, c'est à dire d'acquérir les images avec plusieurs capteurs simultanément ou avec un délai court entre eux. Dans les autres cas, en laboratoire et sur le terrain, il faut des méthodes pour recaler les images. Pour cela, il existe essentiellement deux familles de méthodes \cite{Nasreddine2010,Bloch2006} :

<ul>
<li> La première se base sur les intensités des images et est appelée approche iconique. Pour cela, les méthodes utilisent une distance entre les images et cherchent à la minimiser en la déformant sans tenir compte des structures géométriques mais seulement avec les intensités. Dans le cas d'images multi-capteurs, les intensités peuvent être reliées par une relation mathématique non-linéaire. </li>
<li> La seconde utilise les caractéristiques des images, comme des courbes, des lignes, des points, on parle d'approche géométrique. Il est possible de le faire manuellement avec des points de repère ou automatiquement avec des algorithmes qui vont les détecter, comme par exemple le Speeded Up Robust Features (SURF) \cite{Bay2006} et le Scale-Invariant Feature Transform (SIFT) \cite{Lowe1999}. Ces algorithmes estiment des descripteurs ou points de contrôle à l'échelle globale de l'image. Des versions locales ont ensuite été développées et sont plus performantes pour tenir compte des variations locales de l'échantillon qui sont souvent différentes des variations globales \cite{CeLiu2011,Brigot2017}. Ces descripteurs 2D ont ensuite été généralisés pour des images 3D \cite{Yi2008,Xu2008}, et plus spécifiquement pour des images hyperspectrales \cite{Al-khafaji2018}. Une fois que les points de contrôle ont été définis, un modèle de déformation est estimé pour minimiser la distance entre ces points. Une image sert de base et l'autre image est donc déformée en conséquence pour être calée spatialement sur la première. </li>
</ul>

## Signal alignment