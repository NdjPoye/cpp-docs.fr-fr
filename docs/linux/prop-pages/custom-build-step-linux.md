---
title: "Étape de build personnalisée, propriétés (Linux C++) | Microsoft Docs"
ms.custom: 
ms.date: 10/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77a9c1fb-7c41-4a9b-9418-18ac17ce4e74
author: mikeblome
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.IVCEventTool.CommandLine
- VC.Project.IVCEventTool.Description
- VC.Project.IVCEventTool.ExcludedFromBuild
- VC.Project.VCConfiguration.BuildLogFile
ms.openlocfilehash: 77d483e9d4dc74cbe9ba2736a26561bb410fa6ca
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="custom-build-step-properties-linux-c"></a>Étape de build personnalisée, propriétés (Linux C++)


Propriété | Description
--- | ---
Ligne de commande | Commande à exécuter par l'étape de génération personnalisée.
Description | Message qui s'affiche lors de l'exécution de l'étape de génération personnalisée.
Sorties | Fichier de sortie généré lors de l'étape de génération personnalisée. Ce paramètre est requis afin que les générations incrémentielles fonctionnent correctement.
Dépendances supplémentaires | Liste délimitée par les points-virgules de tous les fichiers d'entrée supplémentaires à utiliser pour l'étape de génération personnalisée.
Exécutez après et exécutez avant | Ces options définissent le moment de l'exécution de l'étape de génération personnalisée dans le processus de génération, par rapport aux cibles répertoriées. Les cibles le plus souvent répertoriées sont BuildGenerateSources, BuildCompile, et BuildLink, car elles constituent des étapes majeures dans le processus de génération. Les cibles souvent répertoriées sont Midl, CLCompile, et Link.
Considérer la sortie en tant que contenu | Cette option n'est significative que pour Windows Store ou les applications Windows Phone, qui incluent tous les fichiers de contenu du package .appx.