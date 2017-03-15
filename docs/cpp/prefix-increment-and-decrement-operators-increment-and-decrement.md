---
title: "Op&#233;rateurs pr&#233;fix&#233;s d&#39;incr&#233;mentation et de d&#233;cr&#233;mentation&#160;: ++ et -- | Microsoft Docs"
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
  - "-- (opérateur), opérateurs de décrément préfixés"
  - "++ (opérateur), opérateurs d'incrément préfixés"
  - "opérateurs de décrémentation"
  - "opérateurs de décrémentation, syntaxe"
  - "opérateur d'incrémentation, syntaxe"
  - "opérateurs (C++), décrément"
  - "opérateurs (C++), incrément"
ms.assetid: 45ea7fc7-f279-4be9-a216-1d9a0ef9eb7b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateurs pr&#233;fix&#233;s d&#39;incr&#233;mentation et de d&#233;cr&#233;mentation&#160;: ++ et --
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
++ unary-expression –– unary-expression  
```  
  
## Notes  
 L'opérateur de pré\-incrémentation \(`++`\) ajoute une valeur incrémentée à son opérande. Cette valeur est le résultat de l'expression.  L'opérande doit être une l\-value autre que de type **const**.  Le résultat est une l\-value du même type que l'opérande.  
  
 L'opérateur de pré\-décrémentation \(**––**\) est analogue à l'opérateur de pré\-incrémentation sauf que l'opérande est décrémenté par un et que le résultat est cette valeur décrémentée.  
  
 Les opérateurs préfixés et suffixés d'incrémentation et de décrémentation affectent leurs opérandes.  La différence principale qui les distingue est lorsque l'incrémentation ou la décrémentation se produit dans l'évaluation d'une expression.  \(Pour plus d'informations, reportez\-vous à la rubrique [Opérateurs suffixés d'incrémentation et de décrémentation](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md).\) Dans leur forme suffixée, l'incrémentation ou la décrémentation ont lieu avant que la valeur ne soit utilisée dans l'évaluation de l'expression. Par conséquent, la valeur de l'expression est différente de la valeur de l'opérande.  Dans leur forme suffixée, l'incrémentation ou la décrémentation ont lieu après que la valeur ne soit utilisée dans l'évaluation de l'expression. Par conséquent, la valeur de l'expression est identique à la valeur de l'opérande.  Par exemple, le programme suivant affiche `++i = 6` :  
  
```  
// expre_Increment_and_Decrement_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   int i = 5;  
   cout << "++i = " << ++i << endl;  
}  
```  
  
 Un opérande de type intégral ou virgule flottante est incrémenté ou décrémenté par la valeur 1 entière.  Le type du résultat est identique au type d'opérande.  Un opérande de type pointeur est incrémenté ou décrémenté par la taille de l'objet qu'il adresse.  Un pointeur incrémenté pointe vers l'objet suivant. Un pointeur décrémenté pointe vers l'objet précédent.  
  
 Étant donné que les opérateurs d'incrémentation et de décrémentation ont des effets secondaires, l'utilisation d'expressions avec les opérateurs d'incrémentation ou de décrémentation dans une [macro de préprocesseur](../preprocessor/macros-c-cpp.md) peut entraîner des résultats indésirables.  Considérez cet exemple :  
  
```  
// expre_Increment_and_Decrement_Operators2.cpp  
#define max(a,b) ((a)<(b))?(b):(a)  
  
int main()  
{  
   int i = 0, j = 0, k;  
   k = max( ++i, j );  
}  
```  
  
 La macro se développe pour donner :  
  
```  
k = ((++i)<(j))?(j):(++i);  
```  
  
 Si `i` est supérieur ou égal à `j` ou inférieur à `j` par 1, il est incrémenté deux fois.  
  
> [!NOTE]
>  Les fonctions inline C\+\+ sont préférables aux macros dans de nombreux cas car elles éliminent des effets secondaires tels que ceux décrits ici et permettent au langage d'effectuer une vérification de type plus complète.  
  
## Voir aussi  
 [Expressions avec opérateurs unaires](../cpp/expressions-with-unary-operators.md)   
 [Opérateurs C\+\+](../misc/cpp-operators.md)   
 [Opérateurs, priorité et associativité C\+\+](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Opérateurs préfixés d'incrémentation et de décrémentation](../c-language/prefix-increment-and-decrement-operators.md)