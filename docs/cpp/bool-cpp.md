---
title: bool (C++) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- bool_cpp
- __BOOL_DEFINED
dev_langs:
- C++
helpviewer_keywords:
- bool keyword [C++]
- __BOOL_DEFINED macro
ms.assetid: 9abed3f2-d21c-4eb4-97c5-716342e613d8
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2d5a8a86cfcc64b70e4910079461513c34fc7d0d
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2018
---
# <a name="bool-c"></a>bool (C++)

Ce mot clé est un type intégré. Une variable de ce type peut avoir des valeurs [true](../cpp/true-cpp.md) et [false](../cpp/false-cpp.md). Les expressions conditionnelles sont de type `bool` et ont ainsi des valeurs de type `bool`. Par exemple, `i!=0` a maintenant **true** ou **false** selon la valeur de `i`.  

**Visual Studio 2017 15,3 et versions ultérieures** (disponible avec [/std : c ++ 17](../build/reference/std-specify-language-standard-version.md)) : l’opérande d’un préfixe ou suffixe incrémentation ou de décrémentation opérateur ne peut pas être de type **bool**. En d’autres termes, étant donnée une variable **b** de type **bool**, ces expressions ne sont plus autorisées :

```cpp
    b++;
    ++b;
    b--;
    --b;
```
  
Les valeurs **true** et **false** ont la relation suivante :  
  
```cpp  
!false == true  
!true == false  
```  
  
Dans l'instruction suivante :  
  
```cpp  
if (condexpr1) statement1;   
```  
  
Si `condexpr1` est **true**, `statement1` est toujours exécuté ; si `condexpr1` est **false**, `statement1` n’est jamais exécutée.  
  
Lorsqu’un préfixe ou suffixe **++** opérateur est appliqué à une variable de type **bool**, la variable est définie sur **true**. 
**Visual Studio 2017 15,3 et versions ultérieures**: opérateur ++ pour **bool** a été supprimé de la langue et n’est plus pris en charge.

Le préfixe ou suffixe **--** opérateur ne peut pas être appliqué à une variable de ce type.  
  
 Le **bool** type participe aux promotions intégrales. R-value de type **bool** peut être converti en une r-value de type **int**, avec **false** devenant zéro et **true** devenant un. Comme un type distinct, **bool** participe à la résolution de surcharge.  
  
## <a name="see-also"></a>Voir aussi

[Mots clés](../cpp/keywords-cpp.md)<br/>
[Types fondamentaux](../cpp/fundamental-types-cpp.md)<br/>
