---
title: "Étape de build personnalisée, propriétés (Linux C++) | Microsoft Docs"
ms.custom: 
ms.date: 10/17/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77a9c1fb-7c41-4a9b-9418-18ac17ce4e74
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: b46ee18fce79c0e1954d37a87f6380c73870fa12
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="custom-build-step-properties-linux-c"></a>Étape de build personnalisée, propriétés (Linux C++)

Propriété | Description
--- | ---
Ligne de commande | Commande à exécuter par l'étape de génération personnalisée.
Description | Message qui s'affiche lors de l'exécution de l'étape de génération personnalisée.
Sorties | Fichier de sortie généré lors de l'étape de génération personnalisée. Ce paramètre est requis afin que les générations incrémentielles fonctionnent correctement.
Dépendances supplémentaires | Liste délimitée par les points-virgules de tous les fichiers d'entrée supplémentaires à utiliser pour l'étape de génération personnalisée.
Exécutez après et exécutez avant | Ces options définissent le moment de l'exécution de l'étape de génération personnalisée dans le processus de génération, par rapport aux cibles répertoriées. Les cibles le plus souvent répertoriées sont BuildGenerateSources, BuildCompile, et BuildLink, car elles constituent des étapes majeures dans le processus de génération. Les cibles souvent répertoriées sont Midl, CLCompile, et Link.
Considérer la sortie en tant que contenu | Cette option est significative uniquement pour les applications du Microsoft Store ou Windows Phone, qui comprennent tous les fichiers de contenu du package .appx.