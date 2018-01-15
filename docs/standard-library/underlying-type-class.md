---
title: underlying_type, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: type_traits/std::underlying_type
dev_langs: C++
helpviewer_keywords: underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8c345c6751ac962602a863d52addce2a7d4f0fcb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="underlyingtype-class"></a>underlying_type, classe
Génère le type intégral sous-jacent pour un type d’énumération.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T>  
struct underlying_type;
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Type à modifier.  
  
## <a name="remarks"></a>Notes  
 Le typedef de membre `type` de la classe de modèle désigne le type intégral sous-jacent de `T`, lorsque `T` est un type d’énumération ; sinon il n’existe aucun typedef de membre `type`.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)



