---
title: "Op&#233;rateurs d&#39;assignation C | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "%= (opérateur)"
  - "&= (opérateur)"
  - "*= (opérateur)"
  - "/= (opérateur)"
  - "^= (opérateur), opérateurs d'assignation"
  - "|= (opérateur)"
  - "+= (opérateur)"
  - "<<= (opérateur)"
  - "= (opérateur)"
  - "-= (opérateur)"
  - "= (opérateur), opérateurs d'assignation"
  - ">> (opérateur)"
  - ">>= (opérateur)"
  - "conversions d'assignation"
  - "opérateurs d'assignation"
  - "opérateurs d'assignation, C"
  - "bitwise-AND (opérateur d'assignation)"
  - "division (opérateur d'assignation)"
  - "multiplication (opérateur d'assignation) (*=)"
  - ">>= (opérateur), opérateurs d'assignation C"
  - "opérateurs (C), d'assignation"
  - "opérateurs (C), déplacement"
  - "remainder (opérateur d'assignation) (%=)"
  - "opérateurs de décalage vers la droite"
  - "opérateurs de décalage, droite"
  - "soustraction (opérateur)"
  - "soustraction (opérateur), opérateurs d'assignation C"
ms.assetid: 11688dcb-c941-44e7-a636-3fc98e7dac40
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateurs d&#39;assignation C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une opération d'assignation assigne la valeur de l'opérande droit à l'emplacement de stockage nommé par l'opérande gauche.  Par conséquent, l'opérande gauche d'une opération d'assignation doit être une l\-value modifiable.  Après l'assignation, une expression d'assignation a la valeur de l'opérande gauche mais n'est pas une l\-value.  
  
 **Syntaxe**  
  
 *assignment\-expression* :  
 *conditional\-expression*  
  
 *unary\-expression assignment\-operator assignment\-expression*  
  
 *assignment\-operator* : un des éléments suivants :  
 **\= \*\=** `/=` `%=` `+=` **–\= \<\<\= \>\>\= &\=** `^=` `|=`  
  
 Les opérateurs d'assignation en langage C peuvent transformer et assigner des valeurs dans une même opération.  C propose les opérateurs d'assignation suivants :  
  
|Opérateur|Opération effectuée|  
|---------------|-------------------------|  
|**\=**|Assignation simple|  
|**\*\=**|Assignation de multiplication|  
|`/=`|Assignation de division|  
|`%=`|Assignation de reste|  
|`+=`|Assignation d'addition|  
|**–\=**|Assignation de soustraction|  
|**\<\<\=**|Assignation de décalage vers la gauche|  
|**\>\>\=**|Assignation de décalage vers la droite|  
|**&\=**|Assignation d'opération AND au niveau du bit|  
|`^=`|Assignation d'opération OR exclusive au niveau du bit|  
|`&#124;=`|Assignation d'opération OR inclusive au niveau du bit|  
  
 Dans l'assignation, le type de la valeur droite est converti pour correspondre au type de la valeur gauche, et la valeur est stockée dans l'opérande gauche après l'assignation.  L'opérande gauche ne doit pas être un tableau, une fonction ni une constante.  Le chemin d'accès de conversion spécifique, qui dépend des deux types, est décrit en détail dans [Conversions de type](../c-language/type-conversions-c.md).  
  
## Voir aussi  
 [Opérateurs d'assignation](../cpp/assignment-operators.md)