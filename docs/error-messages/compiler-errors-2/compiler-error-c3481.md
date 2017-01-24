---
title: "Erreur du compilateur C3481 | Microsoft Docs"
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
  - "C3481"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3481"
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3481
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : variable de capture lambda introuvable  
  
 Le compilateur n’a pas pu trouver la définition d’une variable que vous avez transmise à la liste de capture d’une expression lambda.  
  
### Pour corriger cette erreur  
  
-   Supprimez la variable de la liste de capture de l’expression lambda.  
  
## Exemple  
 L’exemple suivant génère l’erreur C3481, car la variable `n` n’est pas définie :  
  
```  
// C3481.cpp int main() { [n] {}(); // C3481 }  
```  
  
## Voir aussi  
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)