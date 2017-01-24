---
title: "Erreur du compilateur C3495 | Microsoft Docs"
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
  - "C3495"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3495"
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3495
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : une capture lambda doit avoir une durée de stockage automatique  
  
 Vous ne pouvez pas capturer une variable qui n’a pas de durée de stockage automatique, telle qu’une variable qui est marquée `static` ou `extern`.  
  
### Pour corriger cette erreur  
  
-   Ne passez pas une variable `static` ni `extern` à la liste de capture de l’expression lambda.  
  
## Exemple  
 L’exemple suivant génère l’erreur C3495, car la variable `static``n` figure dans la liste de capture d’une expression lambda :  
  
```  
// C3495.cpp int main() { static int n = 66; [&n]() { return n; }(); // C3495 }  
```  
  
## Voir aussi  
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)   
 [\(NOTINBUILD\) Spécificateurs de classe de stockage](http://msdn.microsoft.com/fr-fr/10b3d22d-cb40-450b-994b-08cf9a211b6c)