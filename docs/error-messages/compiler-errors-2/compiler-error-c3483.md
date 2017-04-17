---
title: "Erreur du compilateur C3483 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3483"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3483"
ms.assetid: 18b3a2c5-dfc9-4661-9653-08a5798474cf
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C3483
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' figure déjà dans la liste de capture lambda  
  
 Vous avez passé plusieurs fois la même variable à la liste de capture d’une expression lambda.  
  
### Pour corriger cette erreur  
  
-   Supprimez toutes les instances supplémentaires de la variable de la liste de capture.  
  
## Exemple  
 L’exemple suivant génère l’erreur C3483, car la variable `n` apparaît plusieurs fois dans la liste de capture de l’expression lambda :  
  
```  
// C3483.cpp int main() { int m = 6, n = 5; [m,n,n] { return n + m; }(); // C3483 }  
```  
  
## Voir aussi  
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)