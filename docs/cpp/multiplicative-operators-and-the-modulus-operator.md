---
title: "Op&#233;rateurs de multiplication&#160;et op&#233;rateur modulo | Microsoft Docs"
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
  - "%"
  - "/"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "% (opérateur)"
  - "* (opérateur)"
  - "opérateurs arithmétiques (C++), opérateurs de multiplication"
  - "division (opérateur)"
  - "division (opérateur), opérateurs de multiplication"
  - "Modulo (opérateur), C+"
  - "opérateur de multiplication (C++), opérateurs de multiplication"
  - "opérateurs de multiplication (C++)"
  - "opérateurs (C++), de multiplication"
ms.assetid: b53ea5da-d0b4-40dc-98f3-0aa52d548293
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateurs de multiplication&#160;et op&#233;rateur modulo
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
expression * expression   
expression / expression   
expression % expression  
```  
  
## Notes  
 Les opérateurs de multiplication sont :  
  
-   Multiplication \(**\***\)  
  
-   Division \(**\/**\)  
  
-   Modulo \(reste de division\) \(`%`\)  
  
 Ces opérateurs binaires ont une associativité de droite à gauche.  
  
 Les opérateurs de multiplication prennent des opérandes de types arithmétiques.  L'opérateur Modulo \(`%`\) a une exigence plus stricte dans le sens où ses opérandes doivent être de type intégral. \(Pour obtenir le reste d'une division à virgule flottante, utilisez la fonction runtime [fmod](../c-runtime-library/reference/fmod-fmodf.md).\) Les conversions abordées dans la rubrique [Conversions arithmétiques](../misc/arithmetic-conversions.md) sont appliquées aux opérandes, et le résultat est du type converti.  
  
 L'opérateur de multiplication montre le résultat de la multiplication du premier opérande par le second.  
  
 L'opérateur de division montre le résultat de la division du premier opérande par le second.  
  
 L'opérateur Modulo obtient le reste donné par l'expression suivante, où *e1* est le premier opérande et *e2* le second : *e1* – \(*e1* \/ *e2*\) \* *e2*, où les deux sont des types intégraux.  
  
 La division par 0 dans une division ou une expression de modulo est éliminée et provoque une erreur d'exécution.  Par conséquent, les expressions suivantes génèrent des résultats indéterminés et erronés :  
  
```  
i % 0  
f / 0.0  
```  
  
 Si les deux opérandes pour une expression de multiplication, de division ou de modulo ont le même signe, le résultat est positif.  Sinon, le résultat est négative.  Le résultat du signe d'une opération modulo est défini par l'implémentation.  
  
> [!NOTE]
>  Étant donné que les conversions exécutées par les opérateurs de multiplication ne fournissent pas de conditions de dépassement de capacité positif ou de dépassement de capacité négatif, les informations peuvent être perdues si le résultat d'une opération de multiplication ne peut pas être représenté dans le type des opérandes après conversion.  
  
## Section spécifique à Microsoft  
 Dans Microsoft C\+\+, le résultat d'une expression de modulo est toujours le même que le signe du premier opérande.  
  
## FIN de la section spécifique à Microsoft  
 Si la division calculée de deux entiers est incorrecte et qu'un seul opérande est négatif, le résultat est le plus grand entier \(en amplitude, sans tenir compte du signe\) qui est inférieur à la valeur exacte que l'opérateur de division produirait.  Par exemple, la valeur calculée de –11 \/ 3 is –3,666666666.  Le résultat de cette division intégrale est \-3.  
  
 La relation entre les opérateurs de multiplication est indiquée par l'identité \(*e1* \/ *e2*\) \* *e2* \+ *e1* % *e2* \=\= *e1*.  
  
## Exemple  
 Le programme suivant montre les opérateurs de multiplication.  Notez que l'un ou l'autre des opérandes de `10 / 3` doit faire l'objet d'un cast explicite vers le type `float` pour éviter toute troncation afin que les deux opérandes soient de type `float` avant la division.  
  
```  
// expre_Multiplicative_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
int main() {  
   int x = 3, y = 6, z = 10;  
   cout  << "3 * 6 is " << x * y << endl  
         << "6 / 3 is " << y / x << endl  
         << "10 % 3 is " << z % x << endl  
         << "10 / 3 is " << (float) z / x << endl;  
}  
```  
  
## Voir aussi  
 [Expressions avec opérateurs binaires](../cpp/expressions-with-binary-operators.md)   
 [Opérateurs C\+\+](../misc/cpp-operators.md)   
 [Opérateurs, priorité et associativité C\+\+](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Opérateurs de multiplication C](../c-language/c-multiplicative-operators.md)