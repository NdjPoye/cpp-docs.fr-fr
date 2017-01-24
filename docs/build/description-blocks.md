---
title: "Blocs de description | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "blocs, description"
  - "blocs de description"
  - "programme NMAKE, blocs de description"
ms.assetid: 1321f228-d389-40ac-b0cd-4f6e9293602b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Blocs de description
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un bloc de description est une ligne de dépendance suivie facultativement par un bloc de commandes :  
  
```  
targets... : dependents...  
    commands...  
```  
  
 Une ligne de dépendance définit une ou plusieurs cibles et aucun ou plusieurs dépendants.  Une cible doit être placée au début de la ligne.  Séparez les cibles des dépendants par deux\-points \(:\) ; les espaces et les tabulations sont admis.  Pour scinder la ligne, placez une barre oblique inverse \(\\\) après une cible ou un dépendant.  Si la cible n'existe pas, possède un horodatage antérieur à celui d'un dépendant ou correspond à une [pseudocible](../build/pseudotargets.md), NMAKE exécute les commandes.  Si un dépendant représente une cible ailleurs et n'existe pas ou est obsolète par rapport à ses propres dépendants, NMAKE met à jour ce dépendant avant d'actualiser le dépendant en cours.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
 [Cibles](../build/targets.md)  
  
 [Dépendants](../build/dependents.md)  
  
## Voir aussi  
 [Référence NMAKE](../build/nmake-reference.md)