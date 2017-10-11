---
title: make_signed, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::make_signed
dev_langs:
- C++
helpviewer_keywords:
- make_signed class
- make_signed
ms.assetid: 686247c0-247c-496b-9b1b-ba9dcd633621
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 710f73961b7c31b106d796bfe8935ac6b297072a
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="makesigned-class"></a>make_signed, classe
Rend le type ou le plus petit type signé supérieur ou égal en taille au type.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T>
struct make_signed;

template <class T>
using make_signed_t = typename make_signed<T>::type;
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Type à modifier.  
  
## <a name="remarks"></a>Remarques  
 Une instance du modificateur de type contient un type modifié qui est `T` si `is_signed<T>` contient la valeur true. Dans le cas contraire, il s'agit du plus petit type non signé `UT` pour lequel `sizeof (T) <= sizeof (UT)`.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)




