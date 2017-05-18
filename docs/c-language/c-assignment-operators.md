---
title: "Opérateurs d’assignation C | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- remainder assignment operator (%=)
- '&= operator'
- bitwise-AND assignment operator
- operators [C], assignment
- operators [C], shift
- ^= operator, assignment operators
- += operator
- '>>= operator'
- '|= operator'
- division assignment operator
- subtraction operator
- right shift operators
- subtraction operator, C assignment operators
- = operator, assignment operators
- '*= operator'
- '>> operator'
- '%= operator'
- assignment operators, C
- = operator
- assignment operators
- assignment conversions
- -= operator
- multiplication assignment operator (*=)
- shift operators, right
- /= operator
- operator >>=, C assignment operators
- <<= operator
ms.assetid: 11688dcb-c941-44e7-a636-3fc98e7dac40
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 0e65a64dffc4a9c03f2075bcd9eee87b18ad2e77
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="c-assignment-operators"></a>Opérateurs d'assignation C
Une opération d’assignation assigne la valeur de l’opérande droit à l’emplacement de stockage nommé par l’opérande gauche. Par conséquent, l'opérande gauche d'une opération d'assignation doit être une l-value modifiable. Après l’assignation, une expression d’assignation a la valeur de l’opérande gauche mais n’est pas une l-value.  
  
 **Syntaxe**  
  
 *assignment-expression* :  
 *conditional-expression*  
  
 *unary-expression assignment-operator assignment-expression*  
  
 *assignment-operator* : un des éléments suivants :  
 **= \*=** `/=` `%=` `+=` **-= <\<= >>= &=** `^=` `|=`  
  
 Les opérateurs d'assignation en langage C peuvent transformer et assigner des valeurs dans une même opération. C propose les opérateurs d'assignation suivants :  
  
|Opérateur|Opération effectuée|  
|--------------|-------------------------|  
|**=**|Assignation simple|  
|**\*=**|Assignation de multiplication|  
|`/=`|Assignation de division|  
|`%=`|Assignation de reste|  
|`+=`|Assignation d'addition|  
|**-=**|Assignation de soustraction|  
|**<\<=**|Assignation de décalage vers la gauche|  
|**>>=**|Assignation de décalage vers la droite|  
|**&=**|Assignation d'opération AND au niveau du bit|  
|`^=`|Assignation d'opération OR exclusive au niveau du bit|  
|`&#124;=`|Assignation d'opération OR inclusive au niveau du bit|  
  
 Dans l'assignation, le type de la valeur droite est converti pour correspondre au type de la valeur gauche, et la valeur est stockée dans l'opérande gauche après l'assignation. L’opérande gauche ne doit pas être un tableau, une fonction ni une constante. Le chemin d’accès de conversion spécifique, qui dépend des deux types, est décrit en détail dans [Conversions de type](../c-language/type-conversions-c.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Opérateurs d’assignation](../cpp/assignment-operators.md)
