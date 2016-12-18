---
title: "Op&#233;rateurs relationnels&#160;: &lt;, &gt;, &lt;= et &gt;=  | Microsoft Docs"
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
  - "<"
  - ">"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "< (opérateur)"
  - "<= (opérateur)"
  - "> (opérateur)"
  - ">= (opérateur)"
  - "supérieur à (opérateurs)"
  - "supérieur ou égal à (opérateurs)"
  - "inférieur à (opérateur)"
  - "inférieur ou égal à (opérateur)"
  - "opérateurs relationnels, syntaxe"
ms.assetid: d346b53d-f14d-4962-984f-89d39a17ca0f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateurs relationnels&#160;: &lt;, &gt;, &lt;= et &gt;= 
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
        expression < expression  
expression > expression  
expression <= expression  
expression >= expression  
```  
  
## Notes  
 Les opérateurs relationnels binaires déterminent les relations suivantes :  
  
-   Inférieur à \(**\<**\)  
  
-   Supérieur à \(**\>**\)  
  
-   Inférieur ou égal à \(**\<\=**\)  
  
-   Supérieur ou égal à \(**\>\=**\)  
  
 Les opérateurs relationnels ont une associativité de gauche à droite.  Les deux opérandes des opérateurs relationnels doivent être de type arithmétique ou pointeur.  Ils génèrent des valeurs de type `bool`.  La valeur retournée est **false** \(0\) si la relation dans l'expression est false ; sinon, la valeur retournée est **true** \(1\).  
  
## Exemple  
  
```  
// expre_Relational_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   cout  << "The true expression 3 > 2 yields: "  
         << (3 > 2) << endl  
         << "The false expression 20 < 10 yields: "  
         << (20 < 10) << endl;  
}  
```  
  
 Les expressions dans l'exemple précédent doivent être placées entre parenthèses, car l'opérateur d'insertion de flux \(**\<\<**\) a une priorité plus élevée que les opérateurs relationnels.  Par conséquent, la première expression sans parenthèses est évaluée comme suit :  
  
```  
(cout << "The true expression 3 > 2 yields: " << 3) < (2 << "\n");  
```  
  
 Les conversions arithmétiques habituelles traitées dans [Conversions arithmétiques](../misc/arithmetic-conversions.md) sont appliquées aux opérandes de types arithmétiques.  
  
## Comparaison des pointeurs  
 Lorsque deux pointeurs vers des objets du même type sont comparés, le résultat est déterminé par l'emplacement des objets pointés figurant dans l'espace d'adressage du programme.  Les pointeurs peuvent également être comparés à une expression constante qui correspond à 0 ou à un pointeur de type void \*.  Si une comparaison de pointeur est effectuée par rapport à un pointeur de type void \*, l'autre pointeur est implicitement converti en type void \*.  Ensuite la comparaison est effectuée.  
  
 Deux pointeurs de types différents ne peuvent pas être comparés à moins que :  
  
-   Un type est un type de classe dérivé de l'autre type.  
  
-   Au moins un des pointeurs est explicitement converti \(cast\) pour taper void \*.  \(L'autre pointeur est implicitement converti en type void \* pour la conversion.\)  
  
 Deux pointeurs du même type qui pointent vers le même objet ont la garantie d'être de comparer une valeur égale.  Si deux pointeurs vers des membres non statique d'un objet sont comparés, les règles suivantes s'appliquent :  
  
-   Si le type de classe n'est pas une union, et si les deux membres ne sont pas séparés par un *access\-specifier* de type public, protected ou private, le pointeur vers le membre déclaré en dernier fera une comparaison supérieure à celle du pointeur vers le membre déclaré avant.  \(Pour plus d'informations sur *access\-specifier*, consultez la section Syntaxe dans [Spécificateurs d'accès](../misc/access-specifiers.md).\)  
  
-   Si les deux membres sont séparés par *access\-specifier*, les résultats sont non définis.  
  
-   Si le type de classe est une union, les pointeurs vers les données membres de cette union comparent une valeur égale.  
  
 Si les deux pointeurs pointent vers des éléments du même tableau ou vers l'avant dernier élément du tableau, le pointeur vers l'objet avec l'indice le plus élevé compare une valeur supérieure.  La comparaison des pointeurs est garantie comme étant valide uniquement lorsque les pointeurs font référence à des objets du même tableau ou à l'emplacement situé après la fin du tableau.  
  
## Voir aussi  
 [Expressions avec opérateurs binaires](../cpp/expressions-with-binary-operators.md)   
 [Opérateurs C\+\+](../misc/cpp-operators.md)   
 [Opérateurs, priorité et associativité C\+\+](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Opérateurs relationnels et d'égalité C](../c-language/c-relational-and-equality-operators.md)