---
title: "Erreur du compilateur C2251 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2251"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2251"
ms.assetid: fefe050c-f8d3-4316-b237-8007dbcdd3bf
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C2251
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L’espace de noms 'namespace' n’a pas de membre 'member' \- Voulez\-vous utiliser 'member' ?  
  
 Le compilateur n’a pas pu trouver d’identificateur dans l’espace de noms spécifié.  
  
 L’exemple suivant génère l’erreur C2251 :  
  
```  
// C2251.cpp // compile with: /c namespace A { namespace B { void f1(); } using namespace B; } void A::f1() {}   // C2251 void A::B::f1() {}   // OK  
```