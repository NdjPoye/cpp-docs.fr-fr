---
title: "Op&#233;rateurs, priorit&#233; et associativit&#233; C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "associativité des opérateurs"
  - "ordre d'évaluation"
  - "hiérarchie, d'opérateur"
  - "opérateurs multiples"
  - "opérateurs (priorité)"
  - "opérateurs (C++), associativité"
  - "opérateurs (C++), hiérarchie"
  - "opérateurs (C++), priorité"
  - "priorité, opérateurs"
ms.assetid: 95c1f0ba-dad8-4034-b039-f79a904f112f
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateurs, priorit&#233; et associativit&#233; C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le langage C\+\+ inclut tous les opérateurs C et en ajoute plusieurs nouveaux.  Les opérateurs spécifient une évaluation à effectuer sur un ou plusieurs opérandes.  
  
 La priorité des opérateurs spécifie l'ordre des opérations des expressions qui contiennent plusieurs opérateurs.  L'associativité des opérateurs spécifie si, dans une expression contenant plusieurs opérateurs ayant la même priorité, un opérande est groupé avec celui situé à sa gauche ou celui situé à sa droite.  Le tableau suivant indique la priorité et l'associativité des opérateurs C\+\+ \(de priorité décroissante\).  Les opérateurs ayant le même numéro de priorité ont une priorité identique, à moins qu'une autre relation soit explicitement forcée par des parenthèses.  
  
### Priorité des opérateurs C\+\+ et associativité  
  
|Description des opérateurs|Opérateur|  
|--------------------------------|---------------|  
|`Group 1 precedence, no associativity`|  
|[Résolution de portée](../cpp/scope-resolution-operator.md)|`::`|  
|`Group 2 precedence, left to right associativity`|  
|[Sélection de membre \(objet ou pointeur\)](../cpp/member-access-operators-dot-and.md)|`. or –>`|  
|[Indice de tableau](../cpp/subscript-operator.md)|`[ ]`|  
|[Appel de fonction](../cpp/function-call-operator-parens.md)|`( )`|  
|[Incrément suffixé](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|`++`|  
|[Décrément suffixé](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|`––`|  
|[Nom de type](../cpp/typeid-operator.md)|`typeid( )`|  
|[Conversion de type constant](../cpp/const-cast-operator.md)|`const_cast`|  
|[Conversion de type dynamique](../cpp/dynamic-cast-operator.md)|`dynamic_cast`|  
|[Conversion de type réinterprété](../cpp/reinterpret-cast-operator.md)|`reinterpret_cast`|  
|[Conversion de type statique](../cpp/static-cast-operator.md)|`static_cast`|  
|`Group 3 precedence, right to left associativity`|  
|[Taille d'objet ou de type](../cpp/sizeof-operator.md)|`sizeof`|  
|[Incrément préfixé](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|`++`|  
|[Décrément préfixé](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|`––`|  
|[Complément à 1](../cpp/one-s-complement-operator-tilde.md)|`~`|  
|[Opérateur NOT logique](../cpp/logical-negation-operator-exclpt.md)|`!`|  
|[Négation unaire](../misc/unary-negation-operator.md)|`-`|  
|[Plus unaire](../cpp/unary-plus-and-negation-operators-plus-and.md)|`+`|  
|[Adresse\-de](../cpp/lvalue-reference-declarator-amp.md)|`&`|  
|[Adressage indirect](../cpp/indirection-operator-star.md)|`*`|  
|[Créer un objet](../cpp/new-operator-cpp.md)|`new`|  
|[Supprimer un objet](../cpp/delete-operator-cpp.md)|`delete`|  
|[Cast](../cpp/cast-operator-parens.md)|`Cast: ()`|  
|`Group 4 precedence, left to right associativity`|  
|[Pointeur vers membre \(objets ou pointeurs\)](../cpp/pointer-to-member-operators-dot-star-and-star.md)|`.* or –>*`|  
|`Group 5 precedence, left to right associativity`|  
|[Multiplication](../cpp/multiplicative-operators-and-the-modulus-operator.md)|`*`|  
|[Division](../cpp/multiplicative-operators-and-the-modulus-operator.md)|`/`|  
|[Modulo](../cpp/multiplicative-operators-and-the-modulus-operator.md)|`%`|  
|`Group 6 precedence, left to right associativity`|  
|[Addition](../cpp/additive-operators-plus-and.md)|`+`|  
|[Soustraction](../cpp/additive-operators-plus-and.md)|`–`|  
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
|[Opération de bits OR exclusive](../cpp/bitwise-exclusive-or-operator-hat.md)|`^`|  
|`Group 12 precedence, left to right associativity`|  
|[Opération de bits OR inclusive](../cpp/bitwise-inclusive-or-operator-pipe.md)|`&#124;`|  
|`Group 13 precedence, left to right associativity`|  
|[AND logique](../cpp/logical-and-operator-amp-amp.md)|`&&`|  
|`Group 14 precedence, left to right associativity`|  
|[OR logique](../cpp/logical-or-operator-pipe-pipe.md)|`&#124;&#124;`|  
|`Group 15 precedence, right to left associativity`|  
|[Conditionnel](../cpp/conditional-operator-q.md)|`? :`|  
|`Group 16 precedence, right to left associativity`|  
|[Assignation](../cpp/assignment-operators.md)|`=`|  
|[Assignation de multiplication](../cpp/assignment-operators.md)|`*=`|  
|[Assignation de division](../cpp/assignment-operators.md)|`/=`|  
|[Assignation de modulo](../cpp/assignment-operators.md)|`%=`|  
|[Assignation d'addition](../cpp/assignment-operators.md)|`+=`|  
|[Assignation de soustraction](../cpp/assignment-operators.md)|`–=`|  
|[Assignation de décalage vers la gauche](../cpp/assignment-operators.md)|`<<=`|  
|[Assignation de décalage vers la droite](../cpp/assignment-operators.md)|`>>=`|  
|[Assignation d'opération AND au niveau du bit](../cpp/assignment-operators.md)|`&=`|  
|[Assignation d'opération OR inclusive au niveau du bit](../cpp/assignment-operators.md)|`&#124;=`|  
|[Assignation d'opération OR exclusive au niveau du bit](../cpp/assignment-operators.md)|`^=`|  
|`Group 17 precedence, right to left associativity`|  
|[expression throw](../cpp/try-throw-and-catch-statements-cpp.md)|`throw`|  
|`Group 18 precedence, left to right associativity`|  
|[Virgule](../cpp/comma-operator.md)|`,`|  
  
## Voir aussi  
 [Opérateurs C\+\+](../misc/cpp-operators.md)   
 [Surcharge d'opérateur](../cpp/operator-overloading.md)