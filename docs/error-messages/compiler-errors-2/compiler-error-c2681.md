---
title: "Erreur du compilateur C2681 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2681"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2681"
ms.assetid: eb42da6d-8d2c-43fd-986b-e73e2b004885
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C2681
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : type d'expression non valide pour 'nom'  
  
 Un opérateur de casting a essayé d'effectuer une conversion depuis un type non valide.  Par exemple, si vous utilisez l'opérateur [dynamic\_cast](../../cpp/dynamic-cast-operator.md) pour convertir une expression en un type pointeur, l'expression source doit être un pointeur.  
  
 L'exemple suivant génère l'erreur C2681 :  
  
```  
// C2681.cpp  
class A { virtual void f(); };  
  
void g(int i) {  
    A* pa;  
    pa = dynamic_cast<A*>(i);  // C2681  
}  
```