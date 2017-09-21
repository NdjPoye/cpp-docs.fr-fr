---
title: "Déclarateurs abstraits C | Microsoft Docs"
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
- declarators, abstract
- abstract declarations
ms.assetid: 6a556ad7-0555-421a-aa02-294d77cda8b5
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
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: cc4c700142f8dd533d98eca6ffb01fa18006a111
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="c-abstract-declarators"></a>Déclarateurs abstraits C
Un déclarateur abstrait est un déclarateur sans identificateur, qui se compose d'un ou de plusieurs pointeurs, tableaux ou modificateurs de fonction. Le modificateur de pointeur (**\***) précède toujours l'identificateur dans un déclarateur ; les modificateurs de tableau (**[ ]**) et de fonction (**( )**) suivent l'identificateur. Sachant cela, vous pouvez déterminer l'emplacement où l'identificateur apparaîtrait dans un déclarateur abstrait et interpréter le déclarateur en conséquence. Consultez [Interprétation de déclarateurs plus complexes](../c-language/interpreting-more-complex-declarators.md) pour obtenir des informations supplémentaires et des exemples de déclarateurs complexes. En général, `typedef` peut être utilisé pour simplifier les déclarateurs. Consultez [Déclarations typedef](../c-language/typedef-declarations.md).  
  
 Les déclarateurs abstraits peuvent être complexes. Les parenthèses dans un déclarateur abstrait complexe spécifient une interprétation particulière, comme c'est le cas pour les déclarateurs complexes dans les déclarations.  
  
 Ces exemples illustrent les déclarateurs abstraits :  
  
```  
int *         // The type name for a pointer to type int:  
  
int *[3]      // An array of three pointers to int  
  
int (*) [5]   // A pointer to an array of five int  
  
int *()       // A function with no parameter specification  
              // returning a pointer to int  
  
// A pointer to a function taking no arguments and   
// returning an int  
  
int (*) ( void )    
  
// An array of an unspecified number of constant pointers to   
// functions each with one parameter that has type unsigned int   
// and an unspecified number of other parameters returning an int   
  
int (*const []) ( unsigned int, ... )  
```  
  
> [!NOTE]
>  Le déclarateur abstrait comprenant un jeu de parenthèses vides, **( )**, n'est pas autorisé car il est ambigu. Il est impossible de déterminer si l'identificateur implicite se trouve à l'intérieur des parenthèses (auquel cas il s'agit d'un type non modifié) ou avant les parenthèses (auquel cas il s'agit d'un type de fonction).  
  
## <a name="see-also"></a>Voir aussi  
 [Déclarateurs et déclarations de variable](../c-language/declarators-and-variable-declarations.md)