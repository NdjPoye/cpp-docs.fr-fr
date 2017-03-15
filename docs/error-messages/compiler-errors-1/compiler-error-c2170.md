---
title: "Erreur du compilateur C2170 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2170"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2170"
ms.assetid: d5c663f0-2459-4e11-a8bf-a52b62f3c71d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C2170
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : non déclaré comme fonction, ne peut pas être intrinsèque  
  
### Pour résoudre le problème en vérifiant les causes possibles suivantes  
  
1.  Le pragma `intrinsic` est utilisé pour un élément autre qu'une fonction.  
  
2.  Le pragma `intrinsic` est utilisé pour une fonction sans forme intrinsèque.