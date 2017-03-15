---
title: "&#201;valuateur d&#39;expression, erreur CXX0015 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0015"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0015"
  - "CXX0015"
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# &#201;valuateur d&#39;expression, erreur CXX0015
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

expression trop complexe \(dépassement de capacité de la pile\)  
  
 L'expression est trop complexe ou trop imbriquée pour la quantité de stockage dont dispose l'évaluateur d'expression C.  
  
 Le dépassement de la pile se produit généralement à cause d'un nombre excessif de calculs en attente.  
  
 Réorganisez l'expression pour que chacun de ses éléments puisse être évalué tout de suite, sans attendre le calcul d'autres parties de l'expression.  
  
 Décomposez l'expression en plusieurs commandes.  
  
 Erreur identique à CAN0015.