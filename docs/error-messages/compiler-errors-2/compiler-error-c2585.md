---
title: "Erreur du compilateur C2585 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2585"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2585"
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur du compilateur C2585
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la conversion explicite vers 'type' est ambiguë  
  
 La conversion du type peut produire plusieurs résultats.  
  
### Pour résoudre le problème en vérifiant les causes possibles suivantes  
  
1.  La conversion à partir d'un type classe ou structure basée sur l'héritage multiple.  Si le type hérite de la même classe de base plusieurs fois, la fonction ou l'opérateur de conversion doit utiliser la résolution de portée \(`::`\) pour spécifier quelles seront les classes héritées à utiliser dans la conversion.  
  
2.  Un opérateur et un constructeur de conversion ont été définis en effectuant la même conversion.