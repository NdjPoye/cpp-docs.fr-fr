---
title: "&#201;valuateur d&#39;expression, erreur CXX0019 | Microsoft Docs"
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
  - "CXX0019"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0019"
  - "CXX0019"
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &#201;valuateur d&#39;expression, erreur CXX0019
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

cast de type incorrect  
  
 L'évaluateur d'expression C ne peut pas effectuer la conversion de type telle qu'elle est spécifiée.  
  
 Erreur identique à CAN0019.  
  
### Pour résoudre le problème en vérifiant les causes possibles suivantes  
  
1.  Le type spécifié est inconnu.  
  
2.  Il y a trop de niveaux de types pointeur.  Par exemple, la conversion de type  
  
    ```  
    (char **)h_message  
    ```  
  
     ne peut pas être évaluée par l'évaluateur d'expression C.