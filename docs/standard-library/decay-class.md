---
title: decay, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::decay
dev_langs:
- C++
helpviewer_keywords:
- decay class
ms.assetid: 96baa2fd-c8e0-49af-be91-ba375ba7f9dc
caps.latest.revision: 20
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: c24872ee58c740776285c715f1d03b16e811d9c6
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="decay-class"></a>decay, classe
Produit le type passé par la valeur. Transforme un type en non-référence, non-const ou non-volatile, ou crée un pointeur vers le type à partir d’une fonction ou d’un type de tableau.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T>
struct decay;

template <class T>  
using decay_t = typename decay<T>::type;
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Type à modifier.  
  
## <a name="remarks"></a>Notes  
 Utilisez le modèle de décomposition pour produire le type résultant comme si le type avait été passé comme argument par la valeur. Un typedef de membre de la classe de modèle `type` contient un type modifié qui est défini au cours des étapes suivantes :  
  
-   Le type `U` est défini en tant que `remove_reference<T>::type`.  
  
-   Si `is_array<U>::value` a la valeur true, le type modifié `type` est `remove_extent<U>::type *`.  
  
-   Sinon, si `is_function<U>::value` a la valeur true, le type modifié `type` est `add_pointer<U>::type`.  
  
-   Sinon, le type modifié `type` est `remove_cv<U>::type`.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)




