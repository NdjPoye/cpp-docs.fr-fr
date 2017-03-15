---
title: "Erreur du compilateur C3496 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3496"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3496"
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C3496
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'this' est toujours capturé par valeur : '&' ignoré  
  
 Vous ne pouvez pas capturer le pointeur `this` par référence.  
  
### Pour corriger cette erreur  
  
-   Capturez le pointeur `this` par valeur.  
  
## Exemple  
 L’exemple suivant génère l’erreur C3496, car une référence au pointeur `this` se trouve dans la liste de capture d’une expression lambda :  
  
```  
// C3496.cpp // compile with: /c class C { void f() { [&this] {}(); // C3496 } };  
```  
  
## Voir aussi  
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)