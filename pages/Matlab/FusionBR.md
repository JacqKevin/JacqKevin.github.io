---
title: Fusion at low resolution
description: Fusion toolboxes
permalink: FusionBR.html
sidebar: Matlab_sidebar
---

Pour corriger les déformations de surface des échantillons entre les acquisitions (1), il faut recaler les images. Dans le cas d'image de télédétection, cela est plutôt simple grâce au georéférencement des pixels. Dans le cas d'image de laboratoire, le plus simple et de les coréférencer, c'est à dire d'acquérir les images avec plusieurs capteurs simultanément ou avec un délai court entre eux. Dans les autres cas, en laboratoire et sur le terrain, il faut des méthodes pour recaler les images. Pour cela, il existe essentiellement deux familles de méthodes \cite{Nasreddine2010,Bloch2006} :

<ul>
<li> La première se base sur les intensités des images et est appelée approche iconique. Pour cela, les méthodes utilisent une distance entre les images et cherchent à la minimiser en la déformant sans tenir compte des structures géométriques mais seulement avec les intensités. Dans le cas d'images multi-capteurs, les intensités peuvent être reliées par une relation mathématique non-linéaire. </li>
<li> La seconde utilise les caractéristiques des images, comme des courbes, des lignes, des points, on parle d'approche géométrique. Il est possible de le faire manuellement avec des points de repère ou automatiquement avec des algorithmes qui vont les détecter, comme par exemple le Speeded Up Robust Features (SURF) \cite{Bay2006} et le Scale-Invariant Feature Transform (SIFT) \cite{Lowe1999}. Ces algorithmes estiment des descripteurs ou points de contrôle à l'échelle globale de l'image. Des versions locales ont ensuite été développées et sont plus performantes pour tenir compte des variations locales de l'échantillon qui sont souvent différentes des variations globales \cite{CeLiu2011,Brigot2017}. Ces descripteurs 2D ont ensuite été généralisés pour des images 3D \cite{Yi2008,Xu2008}, et plus spécifiquement pour des images hyperspectrales \cite{Al-khafaji2018}. Une fois que les points de contrôle ont été définis, un modèle de déformation est estimé pour minimiser la distance entre ces points. Une image sert de base et l'autre image est donc déformée en conséquence pour être calée spatialement sur la première. </li>
</ul>
