---
title: "Avertissement NMAKE U4004 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U4004"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U4004"
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement NMAKE U4004
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

règles trop nombreuses pour la cible 'nomcible'  
  
 Plusieurs blocs de description ont été spécifiés pour la cible donnée en utilisant comme séparateurs des signes des deux\-points simples \(**:**\).  NMAKE a exécuté les commandes du premier bloc de description et ignoré les blocs suivants.  
  
 Pour spécifier la même cible dans plusieurs dépendances, utilisez comme séparateur des signes des deux\-points doubles \(`::`\) dans chaque ligne de dépendance.