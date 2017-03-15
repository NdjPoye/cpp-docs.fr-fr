---
title: "Op&#233;rateur OR logique&#160;: || | Microsoft Docs"
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
  - "||"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "|| (opérateur)"
  - "opérateur logique OR"
  - "OR (opérateur)"
  - "OR (opérateur), logique"
ms.assetid: 31837c99-2655-4bf3-8ded-f13b7a9dc533
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateur OR logique&#160;: ||
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
logical-or-expression   
||  
 logical-and-expression  
  
```  
  
## Notes  
 L'opérateur OR logique \(`||`\) retourne la valeur booléenne **true** si un ou les deux opérandes ont la valeur **true**, et retourne **false** dans le cas contraire.  Les opérandes sont convertis implicitement vers le type `bool` avant leur évaluation, et le résultat est de type `bool`.  L'opérateur OR logique présente une associativité de gauche à droite.  
  
 Les opérandes de l'opérateur OR logique ne sont pas nécessairement du même type, mais ils doivent être de type intégral ou pointeur.  Les opérandes sont souvent des expressions relationnelles ou d'égalité.  
  
 Le premier opérande doit être complètement évalué et tous les effets secondaires terminés pour que l'évaluation de l'expression OR logique se poursuive.  
  
 Le second opérande est évalué seulement si le premier opérande équivaut à false \(0\).  Cela permet d'éviter l'évaluation inutile du second opérande lorsque l'expression OR logique a pour valeur true.  
  
```  
printf( "%d" , (x == w || x == y || x == z) );  
```  
  
 Dans l'exemple ci\-dessus, si `x` est égal à `w`, à `y` ou à `z`, le second argument de la fonction `printf` équivaut à true et la valeur 1 est affichée.  Dans le cas contraire, il équivaut à false et la valeur 0 est affichée.  Dès que l'une des conditions équivaut à true, l'évaluation cesse.  
  
## Mot clé d'opérateur pour &#124;&#124;  
 L'opérateur **or** est l'équivalent textuel de `||`.  Il existe deux manières d'accéder à l'opérateur **or** dans vos programmes : en incluant le fichier d'en\-tête `iso646.h` ou en compilant avec l'option [\/Za](../build/reference/za-ze-disable-language-extensions.md) \(Désactivation des extensions de langage\) du compilateur.  
  
## Exemple  
  
```  
// expre_Logical_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate logical OR  
#include <iostream>  
using namespace std;  
int main() {  
   int a = 5, b = 10, c = 15;  
   cout  << boolalpha  
         << "The true expression "  
         << "a < b || b > c yields "  
         << (a < b || b > c) << endl  
         << "The false expression "  
         << "a > b || b > c yields "  
         << (a > b || b > c) << endl;  
}  
```  
  
## Voir aussi  
 [Opérateurs logiques](../misc/logical-operators.md)   
 [Opérateurs C\+\+](../misc/cpp-operators.md)   
 [Opérateurs, priorité et associativité C\+\+](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Opérateurs logiques C](../c-language/c-logical-operators.md)