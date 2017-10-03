---
title: is_assignable, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::is_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_assignable
ms.assetid: 53444287-c8be-4ad2-9487-a85c066a4f84
caps.latest.revision: 14
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
ms.openlocfilehash: 3801ef0c7a4642dd3c07b714441e49d7d5ac6bc0
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

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
 L’expression non évaluée `declval<To>() = declval<From>()` doit être bien formée. `From` et `To` doivent tous deux être des types complets, `void`, ou des tableaux de limite inconnue.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)




