---
title: "Interprétation de l’opérateur d’indice | Documents Microsoft"
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
- subscript operator, interpretation of
- arrays [C++], subscripting
- interpreting subscript operators
- operators [C++], interpretation of subscript
ms.assetid: 8852ca18-9d5b-43f7-b8bd-abc89364fbf2
caps.latest.revision: 7
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 1a83ff6aea4380688d3b6298b93e04caab1dbb7f
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="interpretation-of-subscript-operator"></a>Interprétation de l'opérateur Indice
Comme d’autres opérateurs, l’opérateur d’indice (**[]**) peut être redéfini par l’utilisateur. Le comportement par défaut de l'opérateur d'indice, s'il n'est pas surchargé, est de combiner le nom d'un tableau et l'indice à l'aide de la méthode suivante :  
  
 \*((*-nom de la matrice*) + (*indice*))  
  
 Comme dans toute addition qui implique des types pointeur, la mise à l'échelle est exécutée automatiquement pour ajuster la taille du type. Par conséquent, la valeur résultante n’est pas *indice* octets à partir de l’origine de *-nom de la matrice*; au lieu de cela, il est le *indice*ième élément du tableau. (Pour plus d’informations sur cette conversion, consultez [opérateurs additifs](../cpp/additive-operators-plus-and.md).)  
  
 De même, pour des tableaux multidimensionnels, l'adresse est dérivée à l'aide de la méthode suivante :  
  
 **((**   
 ***nom de tableau* ) + ()**   
 ***indice* 1***max*2 * \* max*3*...max*n) ** + ** *indice*2 * \* max*3*...max*n).   . . *+**indice*n))  
  
## <a name="see-also"></a>Voir aussi  
 [Tableaux](../cpp/arrays-cpp.md)
