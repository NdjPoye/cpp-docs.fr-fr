---
title: is_destructible, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: type_traits/std::is_destructible
dev_langs: C++
helpviewer_keywords: is_destructible
ms.assetid: 3bb9b718-1ad5-49ae-93cc-92b93b546b4d
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 25574f44995bc118388c3100ee262d9ad13f4f8c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="isdestructible-class"></a>is_destructible, classe
Teste si le type est destructible.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T>  
struct is_destructible;
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Type à interroger.  
  
## <a name="remarks"></a>Notes  
 Une instance du prédicat de type a la valeur true si le type `T` est un type destructible. Sinon, sa valeur est false. Les types destructibles sont des types référence, des types d’objets et des types pour lesquels, pour un type `U` égal à `remove_all_extents_t<T>` , l’opérande non évalué `std::declval<U&>.~U()` est bien formé. D’autres types, notamment les types incomplets, `void`, et les types de fonction, ne sont pas des types destructibles.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)



