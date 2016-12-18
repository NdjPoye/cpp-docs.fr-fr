---
title: "Avertissement du compilateur (niveau&#160;4) C4913 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4913"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4913"
ms.assetid: b94aa52e-6029-4170-9134-017714931546
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;4) C4913
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**l'opérateur binaire défini par l'utilisateur ',' existe mais aucune surcharge n'a pu convertir tous les opérandes, opérateur binaire intégré par défaut ',' utilisé**  
  
 Un appel à l’opérateur virgule intégré s’est produit dans un programme où figure également un opérateur virgule surchargé. Une conversion censée être terminée n’a pas été effectuée.  
  
 Le code suivant génère l’avertissement C4913 :  
  
```  
// C4913.cpp // compile with: /W4 struct A { }; struct S { }; struct B { // B() { } // B(S &s) { s; } }; B operator , (A a, B b) { a; return b; } int main() { A a; B b; S s; a, b;   // OK calls user defined operator a, s;   // C4913 uses builtin comma operator // uncomment the conversion code in B to resolve. }  
```