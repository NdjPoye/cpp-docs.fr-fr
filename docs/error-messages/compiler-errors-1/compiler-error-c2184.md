---
title: "Erreur du compilateur C2184 | Microsoft Docs"
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
  - "C2184"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2184"
ms.assetid: 80fc8bff-7d76-4bde-94d2-01d84bb6824a
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2184
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : type interdit pour l’expression \_\_except, il doit s’agir d’un type intégral  
  
 Un type a été utilisé dans une instruction [\_\_except](../../c-language/try-except-statement-c.md), mais ce type n’est pas autorisé.  
  
 L’exemple suivant génère l’erreur C2184 :  
  
```  
// C2184.cpp void f() { int * p; __try{} __except(p){};   // C2184 }  
```  
  
 Solution possible :  
  
```  
// C2184b.cpp // compile with: /c void f() { int i = 0; __try{} __except(i){}; }  
```