---
title: "Erreur du compilateur C3484 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3484"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3484"
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C3484
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\-\>' attendu avant le type de retour  
  
 Vous devez indiquer `->` avant le type de retour d’une expression lambda.  
  
### Pour corriger cette erreur  
  
-   Indiquez `->` avant le type de retour.  
  
## Exemple  
 L’exemple suivant génère l’erreur C3484 :  
  
```  
// C3484a.cpp int main() { return []() . int { return 42; }(); // C3484 }  
```  
  
## Exemple  
 L’exemple suivant résout l’erreur C3484 en fournissant `->` avant le type de retour de l’expression lambda :  
  
```  
// C3484b.cpp int main() { return []() -> int { return 42; }(); }  
```  
  
## Voir aussi  
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)