---
title: "Erreur du compilateur C3482 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3482"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3482"
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C3482
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'this' peut uniquement être utilisé en tant que capture lambda dans une fonction membre non statique  
  
 Vous ne pouvez pas passer `this` à la liste de capture d’une expression lambda qui est déclarée dans une méthode statique ou une fonction globale.  
  
### Pour corriger cette erreur  
  
-   Convertissez la fonction englobante en méthode non statique.  
  
-   Vous pouvez aussi supprimer le pointeur `this` de la liste de capture de l’expression lambda.  
  
## Exemple  
 L’exemple suivant génère l’erreur C3482 :  
  
```  
// C3482.cpp // compile with: /c class C { public: static void staticMethod() { [this] {}(); // C3482 } };  
```  
  
## Voir aussi  
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)