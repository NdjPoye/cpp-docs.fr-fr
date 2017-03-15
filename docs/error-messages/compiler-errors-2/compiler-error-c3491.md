---
title: "Erreur du compilateur C3491 | Microsoft Docs"
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
  - "C3491"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3491"
ms.assetid: 7f0e71b2-46a0-4d25-bd09-6158a280f509
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3491
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'variable' : impossible de modifier une capture par valeur dans une expression lambda non mutable  
  
 Une expression lambda non mutable ne peut pas modifier la valeur d’une variable capturée par valeur.  
  
### Pour corriger cette erreur  
  
-   Déclarez votre expression lambda avec le mot clé `mutable`, ou  
  
-   Passez la variable par référence à la liste de capture de l’expression lambda.  
  
## Exemple  
 L’exemple suivant génère l’erreur C3491, car le corps d’une expression lambda non mutable modifie la variable de capture `m` :  
  
```  
// C3491a.cpp int main() { int m = 55; [m](int n) { m = n; }(99); // C3491 }  
```  
  
## Exemple  
 L’exemple suivant résout l’erreur C3491 en déclarant l’expression lambda avec le mot clé `mutable` :  
  
```  
// C3491b.cpp int main() { int m = 55; [m](int n) mutable { m = n; }(99); }  
```  
  
## Voir aussi  
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)