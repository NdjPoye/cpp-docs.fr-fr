---
title: Opérateurs d’assignation C | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9a13f3b36ae4f5bbd11f170d78d735427882d2ff
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
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