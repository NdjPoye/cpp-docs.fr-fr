---
title: "Erreur d&#39;ex&#233;cution C R6018 | Microsoft Docs"
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
  - "R6018"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6018"
ms.assetid: f6dd40d1-a119-4d8b-b39e-97350ea23349
caps.latest.revision: 7
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur d&#39;ex&#233;cution C R6018
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

erreur de tas inattendue  
  
 Le programme a rencontré une erreur inattendue pendant l'exécution d'une opération de gestion de la mémoire.  
  
 Cette erreur se produit généralement quand le programme modifie par inadvertance les données du tas au moment de l'exécution.  Cependant, elle peut aussi être provoquée par une erreur interne lors de l'exécution ou dans le code du programme d'exploitation.  
  
 Si le compilateur fournit une bibliothèque contenant `_heapchk` et `_heapwalk`, vous pouvez utiliser ces fonctions pour identifier cette erreur.