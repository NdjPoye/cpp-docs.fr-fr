---
title: is_constructible, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_constructible
dev_langs: C++
helpviewer_keywords: is_constructible
ms.assetid: 7cdec5ff-73cf-4f78-a9db-ced2e9c0fd7f
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a2d2127ec8f007dbf301fca7e01a59a7ef462cd1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="isconstructible-class"></a>is_constructible, classe
Teste si un type est constructible quand les types d’arguments spécifiés sont utilisés.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T, class... Args>  
struct is_constructible;
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Type à interroger.  
  
 `Args`  
 Types d’arguments à faire correspondre dans un constructeur de `T`.  
  
## <a name="remarks"></a>Notes  
 Une instance du prédicat de type a la valeur true si le type `T` est constructible en utilisant les types d’arguments dans `Args`. Sinon, sa valeur est false. Le type `T` est constructible si la définition de variable `T t(std::declval<Args>()...);` est bien formée. `T` et tous les types dans `Args` doivent être des types complets, `void`, ou des tableaux de limite inconnue.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)



