---
title: "Erreur du compilateur C2245 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2245"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2245"
ms.assetid: 08aaeadf-10ec-485a-b2a6-6e775289082b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C2245
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

fonction membre 'function' inexistante spécifiée en tant que friend \(la signature de la fonction membre ne correspond à aucune surcharge\)  
  
 Une fonction spécifiée comme friend est introuvable par le compilateur.  
  
 L’exemple suivant génère l’erreur C2245 :  
  
```  
// C2245.cpp // compile with: /c class B { void f(int i); }; class A { int m_i; friend void B::f(char);   // C2245 // try the following line instead // friend void B::f(int); }; void B::f(int i) { A a; a.m_i = 0; }  
```