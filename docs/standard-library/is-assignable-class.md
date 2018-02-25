---
title: is_assignable, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_assignable
ms.assetid: 53444287-c8be-4ad2-9487-a85c066a4f84
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d616145aa0810a370d2a9c8f602fc578b28a661b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="isassignable-class"></a>is_assignable, classe
Teste si une valeur de type `From` peut être affectée à un type `To`.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class To, class From>  
struct is_assignable;
```  
  
#### <a name="parameters"></a>Paramètres  
 Pour  
 Type de l'objet qui reçoit l'assignation.  
  
 From  
 Type de l'objet qui fournit la valeur.  
  
## <a name="remarks"></a>Notes  
 L’expression non évaluée `declval<To>() = declval<From>()` doit être bien formée. `From` et `To` doivent tous deux être des types complets, `void` ou des tableaux de limite inconnue.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)



