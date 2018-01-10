---
title: "Opérateurs C| Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ternary operators
- operators [C]
- symbols, operators
- binary operators
- associativity of operators
- binary data, binary expressions
ms.assetid: 13bc4c8e-2dc9-4b23-9f3a-25064e8777ed
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3d4acb0acec44d695bd4c03ffa102a0ac42971b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="c-operators"></a>Opérateurs C
Les opérateurs C sont un sous-ensemble des [opérateurs C++ intégrés](../cpp/cpp-built-in-operators-precedence-and-associativity.md).  
  
 Il existe trois types d'opérateurs. Une expression unaire se compose d'un opérateur unaire ajouté au début d'un opérande, ou du mot clé `sizeof` suivi d'une expression. L'expression peut être le nom d'une variable ou une expression de cast. Si l'expression est une expression de cast, elle doit être placée entre parenthèses. Une expression binaire se compose de deux opérandes joints par un opérateur binaire. Une expression ternaire se compose de trois opérandes joints par l'opérateur d'expression conditionnelle.  
  
 C inclut des opérateurs unaires suivants :  
  
|Symbole|Name|  
|------------|----------|  
|**- ~ !**|Opérateurs de négation et de complément|  
|**\* &**|Opérateurs d'indirection et d'adresse|  
|`sizeof`|Opérateur de taille|  
|**+**|Opérateur plus unaire|  
|**++ --**|Opérateurs d'incrémentation et de décrémentation unaires|  
  
 Les opérateurs binaires s'associent de gauche à droite. C propose les opérateurs binaires suivants :  
  
|Symbole|Name|  
|------------|----------|  
|**\* / %**|Opérateurs multiplicatifs|  
|**+ -**|Opérateurs additifs|  
|**<\< >>**|Opérateurs de décalage|  
|**\<   >   \<=   >=   ==   !=**|Opérateurs relationnels|  
|**&   &#124; ^**|Opérateurs de bits|  
|**&&   &#124;&#124;**|Opérateurs logiques|  
|**,**|Opérateur d'évaluation séquentielle|  
  
 L’opérateur de base (**:>**), pris en charge par les versions antérieures du compilateur C 16 bits de Microsoft, est décrit dans [Résumé de syntaxe du langage C](../c-language/c-language-syntax-summary.md).  
  
 L'opérateur d'expression conditionnelle a une priorité inférieure à celle des expressions binaires et diffère de ces dernières en étant associatif à droite.  
  
 Les expressions avec des opérateurs incluent également des expressions d'assignation, qui utilisent des opérateurs d'assignation unaires ou binaires. Les opérateurs d’assignation unaires sont les opérateurs d’incrémentation (`++`) et de décrémentation (**--**) ; les opérateurs d’assignation binaires sont l’opérateur d’assignation simple (**=**) et les opérateurs d’assignation composés. Chaque opérateur d'assignation composé est une combinaison d'un autre opérateur binaire avec l'opérateur d'assignation simple.  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions et assignations](../c-language/expressions-and-assignments.md)