---
title: "Op&#233;rateurs suffix&#233;s d&#39;incr&#233;mentation et de d&#233;cr&#233;mentation&#160;: ++ et -- | Microsoft Docs"
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
  - "--"
  - "++"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "-- (opérateur), opérateurs de décrément suffixés"
  - "++ (opérateur), opérateurs d'incrément suffixés"
  - "opérateurs de décrémentation"
  - "opérateurs de décrémentation, syntaxe"
  - "opérateur d'incrémentation, syntaxe"
  - "opérateurs de sélection de membres"
  - "opérateurs (C++), suffixés"
  - "opérateurs suffixés"
ms.assetid: 0204d5c8-51b0-4108-b8a1-074c5754d89c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateurs suffix&#233;s d&#39;incr&#233;mentation et de d&#233;cr&#233;mentation&#160;: ++ et --
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
      postfix-expression   
      ++  
postfix-expression ––  
```  
  
## Notes  
 C\+\+ fournit des opérateurs d'incrémentation et de décrémentation préfixés et suffixés. Cette section décrit uniquement les opérateurs d'incrémentation et de décrémentation suffixés. \(Pour plus d'informations, reportez\-vous à la rubrique [Opérateurs d'incrémentation et de décrémentation préfixés](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md).\) La différence entre les deux tient au fait que dans la notation suffixée, l'opérateur figure après *postfix\-expression*, tandis que dans la notation préfixée, l'opérateur figure avant *expression*. L'exemple suivant montre un opérateur d'incrémentation suffixé :  
  
```  
i++;  
```  
  
 L'application de l'opérateur d'incrémentation suffixé \(`++`\) entraîne l'augmentation de la valeur de l'opérande d'une unité du type approprié.  De façon similaire, l'application de l'opérateur de décrémentation suffixé \(**––**\) entraîne la diminution de la valeur de l'opérande d'une unité du type approprié.  
  
 Il est important de noter qu'une expression d'incrémentation ou de décrémentation suffixée prend la valeur de l'expression **avant** l'application de l'opérateur respectif.  L'opération d'incrémentation ou de décrémentation se produit **après** l'évaluation de l'opérande.  Ce problème survient uniquement lorsque l'opération d'incrémentation ou de décrémentation suffixée intervient dans le contexte d'une plus grande expression.  
  
 Lorsqu'un opérateur suffixé est appliqué à un argument de fonction, il n'est pas garanti que la valeur de cet argument sera incrémentée ou décrémentée avant d'être passée à la fonction.  Pour plus d'informations, reportez\-vous à la section 1.9.17 de la norme C\+\+.  
  
 L'application de l'opérateur d'incrémentation suffixé à un pointeur vers un tableau d'objets de type **long** ajoute en fait quatre à la représentation interne du pointeur.  Ce comportement fait que le pointeur, qui référençait auparavant le *n*\-ième élément du tableau, référence à présent le \(*n*\+1\)\-ième élément.  
  
 Les opérandes des opérateurs d'incrémentation et de décrémentation suffixés doivent être des valeurs l\-value modifiables \(non **const**\) de type arithmétique ou pointeur.  Le type du résultat est identique à celui de *postfix\-expression*, mais ce n'est plus une l\-value.  
  
 L'opérande d'un opérateur d'incrémentation suffixé peut également être de type `bool`, auquel cas l'opérande est évalué puis défini sur **true**.  L'opérande d'un opérateur de décrémentation suffixé ne peut pas être de type `bool`.  
  
 Le code suivant illustre l'opérateur d'incrémentation suffixé :  
  
```  
// expre_Postfix_Increment_and_Decrement_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main() {  
   int i = 10;  
   cout << i++ << endl;  
   cout << i << endl;  
}  
```  
  
 Les opérations d'incrémentation et de décrémentation suffixées sur les types énumérés ne sont pas prises en charge :  
  
```  
enum Compass { North, South, East, West );  
Compass myCompass;  
for( myCompass = North; myCompass != West; myCompass++ ) // Error  
```  
  
## Voir aussi  
 [Expressions suffixées](../cpp/postfix-expressions.md)   
 [Opérateurs C\+\+](../misc/cpp-operators.md)   
 [Opérateurs, priorité et associativité C\+\+](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Opérateurs suffixés d'incrémentation et de décrémentation C](../c-language/c-postfix-increment-and-decrement-operators.md)