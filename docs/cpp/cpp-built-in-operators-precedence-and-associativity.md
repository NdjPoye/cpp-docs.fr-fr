---
title: "Les opérateurs C++ intégrés, priorité et associativité | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators (C++), hierarchy
- operator precedence
- precedence, operators
- operators (C++), associativity
- multiple operators [C++]
- associativity of operators [C++]
- operators [C++], precedence
- evaluation order
- hierarchy, operator
ms.assetid: 95c1f0ba-dad8-4034-b039-f79a904f112f
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 6c45b0d3ff2aaee6763b73949727dcde5ee744bc
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="c-built-in-operators-precedence-and-associativity"></a>Les opérateurs C++ intégrés, priorité et associativité
Le langage C++ inclut tous les opérateurs C et en ajoute plusieurs nouveaux. Les opérateurs spécifient une évaluation à effectuer sur un ou plusieurs opérandes.  
  
 La priorité des opérateurs spécifie l'ordre des opérations des expressions qui contiennent plusieurs opérateurs. L'associativité des opérateurs spécifie si, dans une expression contenant plusieurs opérateurs ayant la même priorité, un opérande est groupé avec celui situé à sa gauche ou celui situé à sa droite. Le tableau suivant indique la priorité et l'associativité des opérateurs C++ (de priorité décroissante). Les opérateurs ayant le même numéro de priorité ont une priorité identique, à moins qu'une autre relation soit explicitement forcée par des parenthèses.  
  
### <a name="c-operator-precedence-and-associativity"></a>Priorité des opérateurs C++ et associativité  
  
|Description des opérateurs|Opérateur|  
|--------------------------|--------------|  
|`Group 1 precedence, no associativity`|  
|[Résolution de portée](../cpp/scope-resolution-operator.md)|`::`|  
|`Group 2 precedence, left to right associativity`|  
|[Sélection de membre (objet ou pointeur)](../cpp/member-access-operators-dot-and.md)|`. or ->`|  
|[Indice de tableau](../cpp/subscript-operator.md)|`[ ]`|  
|[Appel de fonction](../cpp/function-call-operator-parens.md)|`( )`|  
|[Incrément suffixé](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|`++`|  
|[Décrément suffixé](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|`--`|  
|[Nom de type](../cpp/typeid-operator.md)|`typeid( )`|  
|[Conversion de type de constante](../cpp/const-cast-operator.md)|`const_cast`|  
|[Conversion de type dynamique](../cpp/dynamic-cast-operator.md)|`dynamic_cast`|  
|[Conversion de type réinterprété](../cpp/reinterpret-cast-operator.md)|`reinterpret_cast`|  
|[Conversion de type statique](../cpp/static-cast-operator.md)|`static_cast`|  
|`Group 3 precedence, right to left associativity`|  
|[Taille de l’objet ou un type](../cpp/sizeof-operator.md)|`sizeof`|  
|[Incrément préfixé](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|`++`|  
|[Décrément préfixé](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|`--`|  
|[Complément à 1](../cpp/one-s-complement-operator-tilde.md)|`~`|  
|[Not logique](../cpp/logical-negation-operator-exclpt.md)|`!`|  
|[Négation unaire](../cpp/unary-plus-and-negation-operators-plus-and.md)|`-`|  
|[Plus unaire](../cpp/unary-plus-and-negation-operators-plus-and.md)|`+`|  
|[Adresse](../cpp/lvalue-reference-declarator-amp.md)|`&`|  
|[Indirection](../cpp/indirection-operator-star.md)|`*`|  
|[Création d’objet](../cpp/new-operator-cpp.md)|`new`|  
|[Détruire un objet](../cpp/delete-operator-cpp.md)|`delete`|  
|[Cast](../cpp/cast-operator-parens.md)|`Cast: ()`|  
|`Group 4 precedence, left to right associativity`|  
|[Pointeur vers membre (objets ou pointeurs)](../cpp/pointer-to-member-operators-dot-star-and-star.md)|`.* or ->*`|  
|`Group 5 precedence, left to right associativity`|  
|[Multiplication](../cpp/multiplicative-operators-and-the-modulus-operator.md)|`*`|  
|[Division](../cpp/multiplicative-operators-and-the-modulus-operator.md)|`/`|  
|[Modulo](../cpp/multiplicative-operators-and-the-modulus-operator.md)|`%`|  
|`Group 6 precedence, left to right associativity`|  
|[Ajout](../cpp/additive-operators-plus-and.md)|`+`|  
|[Soustraction](../cpp/additive-operators-plus-and.md)|`-`|  
|`Group 7 precedence, left to right associativity`|  
|[Décalage vers la gauche](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|`<<`|  
|[Décalage vers la droite](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|`>>`|  
|`Group 8 precedence, left to right associativity`|  
|[Inférieur à](../cpp/relational-operators-equal-and-equal.md)|`<`|  
|[Supérieur à](../cpp/relational-operators-equal-and-equal.md)|`>`|  
|[Inférieur ou égal à](../cpp/relational-operators-equal-and-equal.md)|`<=`|  
|[Supérieur ou égal à](../cpp/relational-operators-equal-and-equal.md)|`>=`|  
|`Group 9 precedence, left to right associativity`|  
|[Égalité](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|`==`|  
|[Inégalité](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|`!=`|  
|`Group 10 precedence left to right associativity`|  
|[Opération de bits AND](../cpp/bitwise-and-operator-amp.md)|`&`|  
|`Group 11 precedence, left to right associativity`|  
|[Opérateur de bits OR exclusif](../cpp/bitwise-exclusive-or-operator-hat.md)|`^`|  
|`Group 12 precedence, left to right associativity`|  
|[Opérateur de bits OR inclusif](../cpp/bitwise-inclusive-or-operator-pipe.md)|`&#124;`|  
|`Group 13 precedence, left to right associativity`|  
|[AND logique](../cpp/logical-and-operator-amp-amp.md)|`&&`|  
|`Group 14 precedence, left to right associativity`|  
|[OR logique](../cpp/logical-or-operator-pipe-pipe.md)|`&#124;&#124;`|  
|`Group 15 precedence, right to left associativity`|  
|[Conditionnel](../cpp/conditional-operator-q.md)|`? :`|  
|`Group 16 precedence, right to left associativity`|  
|[Attribution](../cpp/assignment-operators.md)|`=`|  
|[Assignation de multiplication](../cpp/assignment-operators.md)|`*=`|  
|[Assignation de division](../cpp/assignment-operators.md)|`/=`|  
|[Assignation de modulo](../cpp/assignment-operators.md)|`%=`|  
|[Assignation d’addition](../cpp/assignment-operators.md)|`+=`|  
|[Assignation de soustraction](../cpp/assignment-operators.md)|`-=`|  
|[Assignation de décalage vers la gauche](../cpp/assignment-operators.md)|`<<=`|  
|[Assignation de décalage vers la droite](../cpp/assignment-operators.md)|`>>=`|  
|[Assignation d’opération AND au niveau du bit](../cpp/assignment-operators.md)|`&=`|  
|[Au niveau du bit assignation d’opération OR inclusive](../cpp/assignment-operators.md)|`&#124;=`|  
|[Au niveau du bit assignation OR exclusive](../cpp/assignment-operators.md)|`^=`|  
|`Group 17 precedence, right to left associativity`|  
|[expression throw](../cpp/try-throw-and-catch-statements-cpp.md)|`throw`|  
|`Group 18 precedence, left to right associativity`|  
|[Virgule](../cpp/comma-operator.md)|`,`|  
  
## <a name="see-also"></a>Voir aussi  
[Surcharge d'opérateur](operator-overloading.md)



