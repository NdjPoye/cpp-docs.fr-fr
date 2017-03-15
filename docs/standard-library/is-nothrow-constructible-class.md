---
title: is_nothrow_constructible, classe | Microsoft Docs
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
- is_nothrow_constructible
- std.is_nothrow_constructible
- std::is_nothrow_constructible
- type_traits/std::is_nothrow_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_constructible
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
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
ms.openlocfilehash: bf39b973c39fd024de6b4b75b3cc47aeb5bec9d8
ms.lasthandoff: 02/24/2017

---
# <a name="isnothrowconstructible-class"></a>is_nothrow_constructible, classe
Teste si un type est constructible et est connu comme ne levant pas d’exception quand les types d’arguments spécifiés sont utilisés.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T, class... Args>  
struct is_nothrow_constructible;
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Type à interroger.  
  
 `Args`  
 Types d’arguments à faire correspondre dans un constructeur de `T`.  
  
## <a name="remarks"></a>Notes  
 Une instance du prédicat de type a la valeur true si le type `T` est constructible à l’aide des types d’arguments dans `Args`, et que le constructeur est connu par le compilateur comme ne levant pas d’exception. Sinon, sa valeur est false. Le type `T` est constructible si la définition de variable `T t(std::declval<Args>()...);` est bien formée. `T` et tous les types dans `Args` doivent être des types complets, `void`, ou des tableaux de limite inconnue.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)




