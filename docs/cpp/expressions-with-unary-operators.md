---
title: "Expressions avec op&#233;rateurs unaires | Microsoft Docs"
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
  - "expressions (C++), opérateurs"
  - "expressions (C++), opérateurs unaires"
  - "opérateurs unaires, expressions avec"
ms.assetid: 1217685b-b85d-4b48-9ff4-d90f56a26c1b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Expressions avec op&#233;rateurs unaires
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les opérateurs unaires agissent sur un seul opérande dans une expression.  Opérateurs unaires :  
  
-   [Opérateur d'indirection \(\*\)](../cpp/indirection-operator-star.md)  
  
-   [Opérateur d'adresse \(&\)](../cpp/address-of-operator-amp.md)  
  
-   [Opérateur plus unaire \(\+\)](../cpp/unary-plus-and-negation-operators-plus-and.md)  
  
-   [Opérateur moins unaire \(–\)](../misc/unary-negation-operator.md)  
  
-   [Opérateur de négation logique \(\!\)](../cpp/logical-negation-operator-exclpt.md)  
  
-   [Opérateur de complément à un \(~\)](../cpp/one-s-complement-operator-tilde.md)  
  
-   [Opérateur d'incrémentation de préfixe \(\+\+\)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)  
  
-   [Opérateur de décrémentation de préfixe \(––\)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)  
  
-   [Opérateur de cast \(\)](../cpp/cast-operator-parens.md)  
  
-   [Opérateur sizeof](../cpp/sizeof-operator.md)  
  
-   [Opérateur \_\_uuidof](../cpp/uuidof-operator.md)  
  
-   [Opérateur \_\_alignof](../cpp/alignof-operator.md)  
  
-   [Opérateur new](../cpp/new-operator-cpp.md)  
  
-   [Opérateur delete](../cpp/delete-operator-cpp.md)  
  
 Ces opérateurs ont une associativité de droite à gauche.  Les expressions unaires impliquent en général une syntaxe qui précède une expression primaire ou suffixée.  
  
 Voici les formes possibles des expressions unaires :  
  
-   *postfix\-expression*  
  
-   `++` *unary\-expression*  
  
-   `––` *unary\-expression*  
  
-   *unary\-operator* *cast\-expression*  
  
-   `sizeof` *unary\-expression*  
  
-   `sizeof(` *type\-name* `)`  
  
-   `decltype(` *expression* `)`  
  
-   *allocation\-expression*  
  
-   *deallocation\-expression*  
  
 Toute *postfix\-expression* est considérée comme étant une *unary\-expression*, et comme toute expression primaire est considérée comme étant une *postfix\-expression*, toute expression primaire est considérée comme étant une *unary\-expression*.  Pour plus d'informations, consultez [Expressions suffixées](../cpp/postfix-expressions.md) et [Expressions primaires](../cpp/primary-expressions.md).  
  
 Un *unary\-operator* est constitué d'un ou de plusieurs des symboles suivants : `* &` `+` `–` `!` `~`  
  
 Une *cast\-expression* est une expression unaire avec un transtypage facultatif pour modifier le type.  Pour plus d'informations, consultez [Opérateur de cast : \(\)](../cpp/cast-operator-parens.md).  
  
 Une *expression* peut être une expression quelconque.  Pour plus d'informations, consultez [Expressions](../cpp/expressions-cpp.md).  
  
 L'*allocation\-expression* fait référence à l'opérateur `new`.  L'*deallocation\-expression* fait référence à l'opérateur `delete`.  Pour plus d'informations, reportez\-vous aux liens fournis plus haut dans cette rubrique.  
  
## Voir aussi  
 [Types d'expressions](../cpp/types-of-expressions.md)