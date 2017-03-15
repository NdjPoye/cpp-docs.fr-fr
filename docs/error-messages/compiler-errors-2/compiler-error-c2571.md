---
title: "Erreur du compilateur C2571 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2571"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2571"
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C2571
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : une fonction virtuelle ne peut figurer dans l'union 'union'  
  
 Une union est déclarée avec une fonction virtuelle.  Vous pouvez déclarer une fonction virtuelle uniquement dans une classe ou une structure.  Résolutions possibles :  
  
1.  Modifiez l'union en classe ou en structure.  
  
2.  Rendez la fonction non virtuelle.  
  
 L'exemple suivant génère l'erreur C2571 :  
  
```  
// C2571.cpp  
// compile with: /c  
union A {  
   virtual void func1();   // C2571  
   void func2();   // OK  
};  
```