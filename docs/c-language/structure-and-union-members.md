---
title: "Structure et membres d&#39;union | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ". d'opérateur"
  - "-> (opérateur), structure et membres d'union"
  - "opérateur point (.)"
  - "opérateurs de sélection de membres"
  - "opérateurs (C), sélection de membres"
  - "référencer des membres de structures"
  - "sélection de membres de structures"
  - "membres de structures, référencer"
ms.assetid: bb1fe304-af49-4f98-808d-afdc99b3e319
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Structure et membres d&#39;union
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une « expression de sélection de membres » fait référence aux membres de structures et d'unions.  Ce type d'expression a la valeur et le type du membre sélectionné.  
  
```  
  
        postfix-expression . identifier  
postfix-expression –> identifier  
```  
  
 La liste suivante décrit les deux formes d'expression de sélection de membres :  
  
1.  Dans la première forme, *postfix\-expression* représente une valeur de `struct` ou de type **union**, et *identifier* désigne un membre de la structure ou de l'union spécifiée.  La valeur de l'opération est celle d'*identifier* ; il s'agit d'une l\-value si *postfix\-expression* est une l\-value.  Consultez [Expressions L\-value et R\-value](../c-language/l-value-and-r-value-expressions.md) pour plus d'informations.  
  
2.  Dans la seconde forme, *postfix\-expression* représente un pointeur vers une structure ou une union, et *identifier* désigne un membre de la structure ou de l'union spécifiée.  La valeur est celle de *identifier* ; il s'agit d'une l\-value.  
  
 Les deux formes de ces expressions de sélection de membres ont des effets similaires.  
  
 En fait, une expression utilisant l'opérateur de sélection de membres \(**–\>**\) est une version abrégée d'une expression utilisant le point \(**.**\) si l'expression avant le point inclut l'opérateur d'indirection \(**\***\) appliqué à une valeur de pointeur.  Par conséquent,  
  
```  
  
expression –> identifier  
```  
  
 est équivalent à  
  
```  
  
(*  
expression  
) . identifier  
```  
  
 lorsque *expression* est une valeur de pointeur.  
  
## Exemples  
 Les exemples suivants font référence à cette déclaration de structure.  Pour plus d'informations sur l'opérateur d'indirection \(**\***\) utilisé dans ces exemples, consultez [Opérateurs d'indirection et d'adresse](../c-language/indirection-and-address-of-operators.md).  
  
```  
struct pair   
{  
    int a;  
    int b;  
    struct pair *sp;  
} item, list[10];  
```  
  
 Une expression de sélection de membres pour la structure `item` ressemble à ceci :  
  
```  
item.sp = &item;  
```  
  
 Dans l'exemple ci\-dessus, l'adresse de la structure `item` est assignée au membre `sp` de la structure.  Cela signifie qu'`item` contient un pointeur vers lui\-même.  
  
```  
(item.sp)–>a = 24;  
```  
  
 Dans cet exemple, l'expression de pointeur `item.sp` est utilisée avec l'opérateur de sélection de membres \(**–\>**\) pour assigner une valeur au membre `a`.  
  
```  
list[8].b = 12;  
```  
  
 Cette instruction indique comment sélectionner un membre de structure individuel dans un tableau de structures.  
  
## Voir aussi  
 [Opérateurs d'accès aux membres : . et \-\>](../cpp/member-access-operators-dot-and.md)