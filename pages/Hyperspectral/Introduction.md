---
title: Introduction
description: Introduction
permalink: Introduction_HSI.html
---

# Hyperspectral représentation
Une image standard RVB est représentée comme une donnée tridimensionnelle avec deux dimensions spatiales et une dimension comportant les 3 canaux R, V, B. Pour une image hyperspectrale, on retrouve ces deux dimensions spatiales, auquel est ajoutée une dimension spectrale composé de multiples canaux correspondant à des longueurs d'onde du spectre électromagnétique, c'est pourquoi on la représente par un cube de données. 

Les capteurs spectroscopiques peuvent utiliser différentes gammes du spectre électromagnétique (ultraviolet, visible, infrarouge, rayons X). Ceux-ci enregistrent des informations physiques, chimiques et biologiques sur les échantillons analysés, on parle de propriétés structurales.

# Le spectre électromagnétique

Le spectre électromagnétique est divisé en plusieurs gammes spectrales en fonction des modes d'interaction entre les rayonnements et la matière (molécules, atomes, électrons). Banwell \cite{Banwell1994a} propose de le diviser en sept zones principales qui sont synthétisées dans la figure :
* Les ondes radio-électriques peuvent interagir avec le spin des particules en les inversant, comme par exemple avec les noyaux atomiques ou les électrons célibataires. L'étude de ces deux phénomènes est appelée respectivement résonance magnétique nucléaire (RMN), résonance de spin électronique (RSE) ou la résonance paramagnétique électronique (RPE).
* Les micro-ondes sont capables d'influer sur la vitesse de rotation des molécules, c'est pourquoi son étude se nomme spectroscopie rotationnelle.
* Les infrarouges (IR) s'intéressent aux vibration des liaisons moléculaires, d'où le nom de spectroscopie vibrationnelle. Deux groupes principaux existent dans cette zone, la spectroscopie infrarouge et la spectroscopie Raman. La première est aussi subdivisée en trois zones d'après la norme ISO 20473 \cite{ISO2007}, ou communément subdivisée en cinq zones.
* Les ultraviolets et le visible (UV-visible) excitent les électrons de valence (externe) des atomes ou molécules pour les transitions des états électroniques, on parle de spectroscopie électronique. Deux méthodes principales existent dans cette gamme, la spectroscopie UV-Visible et la spectroscopie de fluorescence UV-Visible (EEM, avec excitation laser LIF, ou en temps résolu TRES). 
* Les rayons X permettent aussi de faire de la spectroscopie électronique, mais au niveau des électrons de cœur ou proche du noyau atomique. Cette gamme peut aussi être divisée en trois méthodes principales, les spectroscopies d'absorption ou de diffraction des rayons X (DRX) et la spectroscopie de fluorescence des rayons X.
* Les rayons gamma influent sur les transitions d'énergie au sein des noyaux des atomes. Elle est aussi représentée par deux méthodes principales, la spectrométrie gamma et la spectrométrie de Mössbauer.

# Spectroscopic acquisition
Le type d'acquisition est aussi spécifique du capteur et de la problématique à résoudre :
* des analyses ponctuelles permettent d'avoir une idée globale de la composition de l'échantillon,
* une analyse continue sur une ligne permet d'avoir une tendance sur la variabilité de l'échantillon suivant cet axe,
* une cartographie en effectuant une analyse point par point sur la totalité de l'échantillon permet de connaitre la variabilité dans les deux directions de l'échantillon,
* une image qui est obtenue par l'acquisition d'une ligne pour obtenir comme précédemment la variabilité globale de l'échantillon.

# Hyperspectral acquisition
Comme on vient de le voir, la cartographie par de multiple acquisitions spectroscopiques puet permettre d'obtenir une iamge hyperspectrale,  c'est cette méthode est appelée point-scan ou whiskbroom. Le plus souvent l'échantillon va se déplacer dans les deux directions et le capteurs est fixe pour estimer l'image hyperspectrale de l'ensemble de l'échantillon. Elle permet d'avoir une résolution spatiale élevée pour un échantillon de taille variable, mais nécessite un temps d'acquisition souvent important. 

Deux autres méthodes existent pour obtenir une image hyperspectrale :
* L'acquisition d'une ligne permettant d'obtenir plusieurs pixels sur une dimension spatiale de l'échantillon, c'est ce que l'on appelle la méthode pushbroom. Ensuite, le plus souvent l'échantillon se déplace dans une direction linéaire et le capteur est fixe, on acquiert ainsi de multiples lignes qui vont créer l'image hyperspectrale. Cette méthode est rapide, facile à automatiser, mais est limité avec la résolution spatiale d'une ligne.
* La dernière méthode consiste à acquérir une image de l'échantillon à chaque longueur d'onde, elle est appelée plan-scan. Ainsi le capteur et l'échantillon sont fixes. Cette méthode est très rapide, mais est est limité spatialement comme l'ensemble est fixe, et ainsi la résolution spatiale est aussi impactée.

En laboratoire ces trois méthodes d'acquisition peuvent etre employées, mais sur le terrain ou en aéroporté la méthode pushbroom est préférée.

