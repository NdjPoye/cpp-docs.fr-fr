---
title: is_trivially_constructible, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- is_trivially_constructible
- std.is_trivially_constructible
- std::is_trivially_constructible
- type_traits/std::is_trivially_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_constructible
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 4acc8f686d918391966949134a5c2b3c1a0a41a5
ms.lasthandoff: 02/24/2017

---
# <a name="istriviallyconstructible-class"></a>is_trivially_constructible, classe
Teste si un type est constructible de façon triviale quand les types d’arguments spécifiés sont utilisés.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T, class... Args>  
struct is_trivially_constructible;
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Type à interroger.  
  
 `Args`  
 Types d’arguments à faire correspondre dans un constructeur de `T`.  
  
## <a name="remarks"></a>Notes  
 Une instance du prédicat de type a la valeur true si le type `T` est constructible de façon triviale en utilisant les types d’arguments dans `Args`. Sinon, sa valeur est false. Le type `T` est constructible de façon triviale si la définition de variable `T t(std::declval<Args>()...);` est bien formée et est connue pour n’appeler aucune opération non triviale. `T` et tous les types dans `Args` doivent être des types complets, `void`, ou des tableaux de limite inconnue.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)




