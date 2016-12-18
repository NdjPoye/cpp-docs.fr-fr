---
title: "Op&#233;rateur AND logique&#160;: &amp;&amp; | Microsoft Docs"
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
  - "&&"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "&& (opérateur)"
  - "AND (opérateur)"
  - "opérateur logique AND"
ms.assetid: 50cfa664-a8c4-4b31-9bab-2f80d7cd2d1f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateur AND logique&#160;: &amp;&amp;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
expression   
&&  
 expression  
  
```  
  
## Notes  
 L'opérateur logique AND \(**&&**\) retourne la valeur booléenne **true** si les deux sont **true** et retourne sinon **false**.  Les opérandes sont convertis implicitement vers le type `bool` avant leur évaluation, et le résultat est de type `bool`.  L'opérateur logique présente une associativité de gauche à droite.  
  
 Les opérandes de l'opérateur logique AND n'ont pas besoin d'être du même type, mais ils doivent être de type intégral ou de type pointeur.  Les opérandes sont souvent des expressions relationnelles ou d'égalité.  
  
 Le premier opérande est complètement évalué et tous les effets secondaires sont terminés avant de continuer l'évaluation de l'expression AND logique.  
  
 Le deuxième opérande est évalué uniquement si le premier opérande a la valeur true \(une valeur différente de zéro\).  Cette évaluation élimine l'évaluation inutile du deuxième opérande lorsque l'expression AND logique est false.  Vous pouvez utiliser cette évaluation de court\-circuit pour empêcher le déréférencement du pointeur NULL, comme indiqué dans l'exemple suivant :  
  
```  
char *pch = 0;  
...  
(pch) && (*pch = 'a');  
```  
  
 Si `pch` est null \(0\), le côté droit de l'expression n'est jamais évalué.  Par conséquent, l'assignation via un pointeur null est impossible.  
  
## Mot clé Operator pour &&  
 L'opérateur **and** est le texte équivalent de **&&**.  Il existe deux moyens d'accéder à l'opérateur **and** dans vos programmes : inclure le fichier d'en\-tête `iso646.h` ou compiler avec l'option de compilateur [\/Za](../build/reference/za-ze-disable-language-extensions.md) \(désactivation des extensions de langage\).  
  
## Exemple  
  
```  
// expre_Logical_AND_Operator.cpp  
// compile with: /EHsc  
// Demonstrate logical AND  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   int a = 5, b = 10, c = 15;  
   cout  << boolalpha  
         << "The true expression "  
         << "a < b && b < c yields "  
         << (a < b && b < c) << endl  
         << "The false expression "  
         << "a > b && b < c yields "  
         << (a > b && b < c) << endl;  
}  
```  
  
## Voir aussi  
 [Opérateurs logiques](../misc/logical-operators.md)   
 [Opérateurs C\+\+](../misc/cpp-operators.md)   
 [Opérateurs, priorité et associativité C\+\+](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Opérateurs logiques C](../c-language/c-logical-operators.md)