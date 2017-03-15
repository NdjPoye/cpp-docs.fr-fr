---
title: "Erreur du compilateur C2695 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2695"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2695"
ms.assetid: 3f6f2091-c38b-40ea-ab6c-f1846f5702d7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C2695
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction1' : la fonction virtuelle de substitution ne diffère de 'fonction2' que par la convention d'appel  
  
 La signature d'une fonction dans une classe dérivée ne peut pas substituer une fonction dans une classe de base et modifier la convention d'appel.  
  
 L'exemple suivant génère l'erreur C2695 :  
  
```  
// C2695.cpp  
class C {  
   virtual void __fastcall func();  
};  
  
class D : public C {  
   virtual void __clrcall func();   // C2695  
};  
```