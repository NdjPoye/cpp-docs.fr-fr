---
title: conditional, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::conditional
dev_langs: C++
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0a106f2361dccbeb33c662c88edd40223a604639
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="conditional-class"></a>conditional, classe
Sélectionne un des deux types, selon la condition spécifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <bool B, class T1, class T2>  
struct conditional;

template <bool _Test, class _T1, class _T2>  
using conditional_t = typename conditional<_Test, _T1, _T2>::type;
```  
  
#### <a name="parameters"></a>Paramètres  
 `B`  
 Valeur qui détermine le type sélectionné.  
  
 `T1`  
 Résultat de type quand B a la valeur true.  
  
 `T2`  
 Résultat de type quand B a la valeur false.  
  
## <a name="remarks"></a>Notes  
 Le typedef de membre de modèle `conditional<B, T1, T2>::type` équivaut à `T1` quand `B` équivaut à `true`, et équivaut à `T2` quand `B` équivaut à `false`.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)



