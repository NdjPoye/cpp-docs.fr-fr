---
title: "Erreur du compilateur C2553 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2553"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2553"
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2553
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction\_base' : le type de retour de la fonction virtuelle de substitution diffère de 'fonction\_substitution'  
  
 Une fonction contenue dans une classe dérivée a essayé de substituer une fonction virtuelle dans une classe de base, mais la fonction de la classe dérivée ne possédait pas le même type de retour que la fonction de la classe de base.  Une signature de fonction de substitution doit correspondre à la signature de la fonction substituée.  
  
 L'exemple suivant génère l'erreur C2553 :  
  
```  
// C2553.cpp  
// compile with: /clr /c  
ref struct C {  
   virtual void f();  
};  
  
ref struct D : C {  
   virtual int f() override ;   // C2553   
  
   // try the following line instead  
   // virtual void f() override;  
};  
```