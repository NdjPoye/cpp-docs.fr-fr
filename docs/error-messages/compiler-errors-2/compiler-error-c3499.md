---
title: "Erreur du compilateur C3499 | Microsoft Docs"
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
  - "C3499"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3499"
ms.assetid: 6717de5c-ae0f-4024-bdf2-b5598009e7b6
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3499
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

une expression lambda dont le type de retour spécifié est void ne peut pas retourner de valeur  
  
 Le compilateur génère cette erreur quand une expression lambda qui spécifie `void` comme type de retour retourne une valeur, ou quand une expression lambda contient plusieurs instructions et retourne une valeur, mais ne spécifie pas son type de retour.  
  
### Pour corriger cette erreur  
  
-   Ne retournez pas une valeur à partir de l’expression lambda ; ou  
  
-   Fournissez le type de retour de l’expression lambda ; ou  
  
-   Combinez les instructions qui composent le corps de l’expression lambda dans une instruction unique.  
  
## Exemple  
 L’exemple suivant génère l’erreur C3499, car le corps d’une expression lambda contient plusieurs instructions et retourne une valeur, mais l’expression lambda ne spécifie pas le type de retour :  
  
```  
// C3499a.cpp int main() { [](int x) { int n = x * 2; return n; } (5); // C3499 }  
```  
  
## Exemple  
 L’exemple suivant montre deux résolutions possibles pour l’erreur C3499. La première résolution fournit le type de retour de l’expression lambda. La seconde résolution combine les instructions qui composent le corps de l’expression lambda dans une instruction unique.  
  
```  
// C3499b.cpp int main() { // Possible resolution 1: // Provide the return type of the lambda expression. [](int x) -> int { int n = x * 2; return n; } (5); // Possible resolution 2: // Combine the statements that make up the body of // the lambda expression into a single statement. [](int x) { return x * 2; } (5); }  
```  
  
## Voir aussi  
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)