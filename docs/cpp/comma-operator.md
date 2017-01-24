---
title: "Op&#233;rateur virgule&#160;: , | Microsoft Docs"
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
  - "%2C"
  - ","
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "virgule (opérateur)"
ms.assetid: 38e0238e-19da-42ba-ae62-277bfdab6090
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateur virgule&#160;: ,
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Permet le regroupement de deux instructions lorsque l'une d'elles est attendue.  
  
## Syntaxe  
  
```  
  
expression , expression  
```  
  
## Notes  
 L'opérateur virgule présente une associativité de gauche à droite.  Deux expressions séparées par une virgule sont évaluées de gauche à droite.  L'opérande gauche est toujours évalué et tous les effets secondaires sont terminés avant l'évaluation de l'opérande droite.  
  
 Les virgules peuvent être utilisées comme séparateurs dans certains contextes, par exemple les listes d'arguments de fonction.  Ne confondez pas l'utilisation de la virgule comme séparateur avec son utilisation comme opérateur. Ces deux utilisations sont entièrement différentes.  
  
 Prenons l'exemple de l'expression  
  
 *e1* , *e2*  
  
 Le type et la valeur de l'expression sont le type et la valeur de *e2*. Le résultat de l'évaluation de *e1* est ignoré.  Le résultat est une l\-value si l'opérande droite est une l\-value.  
  
 Alors que la virgule est normalement utilisée comme séparateur \(par exemple dans les arguments réels des fonctions ou les initialiseurs d'agrégat\), l'opérateur virgule et ses opérandes doivent être placés entre parenthèses.  Par exemple :  
  
```  
func_one( x, y + 2, z );  
func_two( (x--, y + 2), z );  
```  
  
 Dans l'appel de fonction à `func_one` ci\-dessus, trois arguments, séparés par des virgules, sont passés : `x`, `y + 2` et `z`.  Dans l'appel de fonction à `func_two`, les parenthèses forcent le compilateur à interpréter la première virgule comme l'opérateur d'évaluation séquentielle.  Cet appel de fonction passe deux arguments à `func_two`.  Le premier argument est le résultat de l'opération d'évaluation séquentielle `(x--, y + 2)`, qui a la valeur et le type de l'expression `y + 2`. Le second argument est `z`.  
  
## Exemple  
  
```  
// cpp_comma_operator.cpp  
#include <stdio.h>  
int main () {  
   int i = 10, b = 20, c= 30;  
   i = b, c;  
   printf("%i\n", i);  
  
   i = (b, c);  
   printf("%i\n", i);  
}  
```  
  
  **20**  
**30**   
## Voir aussi  
 [Expressions avec opérateurs binaires](../cpp/expressions-with-binary-operators.md)   
 [Opérateurs C\+\+](../misc/cpp-operators.md)   
 [Opérateurs, priorité et associativité C\+\+](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Opérateur d'évaluation séquentielle](../c-language/sequential-evaluation-operator.md)