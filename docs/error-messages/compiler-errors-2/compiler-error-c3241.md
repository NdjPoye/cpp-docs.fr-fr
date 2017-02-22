---
title: "Erreur du compilateur C3241 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3241"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3241"
ms.assetid: 2ca14879-bba0-4a23-b22a-72cfff92d6a4
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur du compilateur C3241
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'méthode' : cette méthode n'a pas été introduite par 'interface'  
  
 Lorsque vous substituez explicitement une fonction, la signature de la fonction doit correspondre exactement à la déclaration de la fonction que vous substituez.  
  
 L'exemple suivant génère l'erreur C3241 :  
  
```  
// C3241.cpp  
#pragma warning(disable:4199)  
  
__interface IX12A {  
   void mf();  
};  
  
__interface IX12B {  
   void mf(int);  
};  
  
class CX12 : public IX12A, public IX12B { // C3241  
   void IX12A::mf(int);  
};  
```