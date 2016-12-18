---
title: "Op&#233;rateur de n&#233;gation logique&#160;: ! | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "!"
  - "Not"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "! d'opérateur"
  - "négation logique"
  - "NOT (opérateur)"
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateur de n&#233;gation logique&#160;: !
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
! cast-expression  
```  
  
## Notes  
 L'opérateur de négation logique \(**\!**\) inverse la signification de son opérande.  L'opérande doit être de type arithmétique ou pointeur \(ou une expression qui a pour valeur le type arithmétique ou pointeur\).  L'opérande est implicitement converti en type `bool`.  Le résultat est **true** si l'opérande converti est **false** ; le résultat est **false** si l'opérande converti est **true**.  Le résultat est de type `bool`.  
  
 Pour une expression *e*, l'expression unaire **\!***e* équivaut à l'expression **\(***e* `==` 0\), sauf si des opérateurs surchargés sont impliqués.  
  
## Mot clé Operator pour \!  
 L'opérateur **not** est l'équivalent textuel de **\!**.  Il existe deux moyens d'accéder à l'opérateur **not** dans vos programmes : inclure le fichier d'en\-tête `iso646.h` ou compiler avec l'option du compilateur [\/Za](../build/reference/za-ze-disable-language-extensions.md) \(désactivation des extensions de langage\).  
  
## Exemple  
  
```  
// expre_Logical_NOT_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main() {  
   int i = 0;  
   if (!i)  
      cout << "i is zero" << endl;  
}  
```  
  
## Voir aussi  
 [Expressions avec opérateurs unaires](../cpp/expressions-with-unary-operators.md)   
 [Opérateurs C\+\+](../misc/cpp-operators.md)   
 [Opérateurs, priorité et associativité C\+\+](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Opérateurs arithmétiques unaires](../c-language/unary-arithmetic-operators.md)