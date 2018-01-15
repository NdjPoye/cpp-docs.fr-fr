---
title: make_signed, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::make_signed
dev_langs: C++
helpviewer_keywords:
- make_signed class
- make_signed
ms.assetid: 686247c0-247c-496b-9b1b-ba9dcd633621
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f9b811f585370a19be47b0140adf74495b6d9019
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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
  
## <a name="remarks"></a>Notes  
 Une instance du modificateur de type contient un type modifié qui est `T` si `is_signed<T>` contient la valeur true. Dans le cas contraire, il s'agit du plus petit type non signé `UT` pour lequel `sizeof (T) <= sizeof (UT)`.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)



