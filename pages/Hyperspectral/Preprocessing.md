---
title: Preprocessing
description: Preprocessing
permalink: Preprocessing_HSI.html
---

# Spectral

Afin d'améliorer les capacités de régression, il est souvent nécessaire de prétraiter les données. On peut les réduire pour accélérer le temps de calcul, cela est souvent réalisé avec une ACP afin d'enlever les variables redondantes et corrélées (colinéaires). Ou encore en sélectionnant des longueurs d'onde discriminantes pour une variable à prédire avec des algorithmes de sélection de variables. Il est aussi possible de débruiter le signal ou de mettre en avant les informations discriminantes avec des prétraitements spectraux, comme des corrections de ligne de base, des dérivées ou des normalisations \cite{Rinnan2009,Vidal2012,Asadzadeh2016}. Il faut vérifier leurs pertinences sur les signaux, car ils peuvent faire disparaitre ou créer des informations \cite{Oliveri2019,Rinnan2014,Engel2013}.

# Spatial

Comme dans le cas de la création d'un modèle multivarié, les images nécessitent un ou des prétraitements pour réduire le bruit ou mettre en avant les structures, comme des normalisations, lissages, dérivées ou rehaussements de contraste. Et il faut aussi prendre garde à leurs effets qui peuvent faire disparaitre des structures intéressantes ou au contraire en créer.

