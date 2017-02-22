---
title: "Erreur du compilateur C2537 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2537"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2537"
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C2537
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'spécificateur' : spécification de liaison non conforme  
  
 Causes possibles :  
  
1.  Le spécificateur de liaison n'est pas pris en charge.  Seul le spécificateur de liaison "C" est pris en charge.  
  
2.  La liaison "C" est spécifiée pour plusieurs fonctions dans un ensemble de fonctions surchargées.  Cela n'est pas autorisé.  
  
 L'exemple suivant génère l'erreur C2537 :  
  
```  
// C2537.cpp  
// compile with: /c  
extern "c" void func();   // C2537  
extern "C" void func2();   // OK  
```