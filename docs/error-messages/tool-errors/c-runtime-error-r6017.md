---
title: "R6017 d’erreur d’ex&#233;cution C | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6017"
ms.assetid: df3ec5f5-6771-4648-ba06-0e26c6a1cc6a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur d&#39;ex&#233;cution C R6017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

erreur de verrouillage multithread inattendue  
  
 Le processus a obtenu une erreur inattendue alors qu'il essayait d'accéder à un verrou multithread d'exécution C sur une ressource système.  
  
 Cette erreur se produit généralement quand le processus modifie par inadvertance les données du tas au moment de l'exécution.  Cependant, elle peut aussi être provoquée par une erreur interne lors de l'exécution ou dans le code du programme d'exploitation.