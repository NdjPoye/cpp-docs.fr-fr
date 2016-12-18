---
title: "&#201;valuateur d&#39;expression, erreur CXX0024 | Microsoft Docs"
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
  - "CXX0024"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0024"
  - "CXX0024"
ms.assetid: eca6adbd-8ff2-4f51-a1cc-a2e9d5d0a47d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &#201;valuateur d&#39;expression, erreur CXX0024
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l'opération requiert une l\-value  
  
 Une expression qui ne produit pas une l\-value est spécifiée pour une opération qui requiert une lvalue.  
  
 Une l\-value \(appelée ainsi parce qu'elle apparaît à gauche \(« left »\) d'une instruction d'assignation\) est une expression qui fait référence à un emplacement mémoire.  
  
 Par exemple, `buffer[count]` est une l\-value valide car elle pointe vers un emplacement mémoire spécifique.  La comparaison logique `zed != 0` n'est pas une l\-value valide parce que son évaluation produit la valeur TRUE \(Vrai\) ou FALSE \(Faux\) et non une adresse mémoire.  
  
 Erreur identique à CAN0024.