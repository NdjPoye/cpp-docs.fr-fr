---
title: "Avertissement du compilateur (niveau 1) C4630 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4630"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4630"
ms.assetid: d8926376-7acc-4fc7-8438-6f0de3468870
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau 1) C4630
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbole' : spécificateur de classe de stockage 'extern' non conforme sur définition de membre  
  
 Une donnée membre ou une fonction membre est définie comme `extern`.  Les membres ne peuvent pas être externes, contrairement aux objets entiers.  Le compilateur ignore le mot clé `extern`.  L'exemple suivant génère l'erreur C4630 :  
  
```  
// C4630.cpp  
// compile with: /W1 /LD  
class A {  
   void func();  
};  
  
extern void A::func() {   // C4630, remove 'extern' to resolve  
}  
```