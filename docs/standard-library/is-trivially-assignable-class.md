---
title: is_trivially_assignable, classe | Microsoft Docs
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
- type_traits/std::is_trivially_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_assignable
ms.assetid: 1284a8f7-4093-426d-9c9a-dabb46f90d6d
caps.latest.revision: 13
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
ms.openlocfilehash: d37d4c827a082f7db179d4fb7014cba371103e71
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="istriviallyassignable-class"></a>is_trivially_assignable, classe
Teste si une valeur de type `From` peut être affectée de façon triviale au type `To`.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class To, class From>  
struct is_trivially_assignable;
```  
  
#### <a name="parameters"></a>Paramètres  
 Pour  
 Type de l'objet qui reçoit l'assignation.  
  
 From  
 Type de l'objet qui fournit la valeur.  
  
## <a name="remarks"></a>Notes  
 L’expression `declval<To>() = declval<From>()` doit être bien formée et le compilateur doit savoir qu’elle ne nécessite aucune opération non triviale. `From` et `To` doivent tous deux être des types complets, `void`, ou des tableaux de limite inconnue.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)




