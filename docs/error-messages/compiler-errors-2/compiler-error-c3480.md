---
title: "Erreur du compilateur C3480 | Microsoft Docs"
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
  - "C3480"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3480"
ms.assetid: 7b2e055a-9604-4d13-861b-b38bda1a6940
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3480
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'variable' : une variable de capture lambda doit provenir d’une portée de fonction englobante  
  
 La variable de capture lambda ne provient pas d’une portée de fonction englobante.  
  
### Pour corriger cette erreur  
  
-   Supprimez la variable de la liste de capture de l’expression lambda.  
  
## Exemple  
 L’exemple suivant génère l’erreur C3480, car la variable `global` ne provient pas d’une portée de fonction englobante :  
  
```  
// C3480a.cpp int global = 0; int main() { [&global] { global = 5; }(); // C3480 }  
```  
  
## Exemple  
 L’exemple suivant résout l’erreur C3480 en supprimant la variable `global` de la liste de capture de l’expression lambda :  
  
```  
// C3480b.cpp int global = 0; int main() { [] { global = 5; }(); }  
```  
  
## Voir aussi  
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)