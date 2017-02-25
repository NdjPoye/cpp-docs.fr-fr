---
title: "Erreur du compilateur C2602 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2602"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2602"
ms.assetid: 6c07a40e-537e-4954-b5c5-1e0e58fe1952
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2602
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe::Identificateur' n'est pas membre d'une classe de base de 'classe'  
  
 Impossible d'accéder à `Identifier`, car il ne s'agit pas d'un membre hérité d'une quelconque classe de base.  
  
 L'exemple suivant génère l'erreur C2602 :  
  
```  
// C2602.cpp  
// compile with: /c  
struct X {  
   int x;  
};  
struct A {  
   int a;  
};  
struct B : public A {  
   X::x;   // C2602 B is not derived from X  
   A::a;   // OK  
};  
```