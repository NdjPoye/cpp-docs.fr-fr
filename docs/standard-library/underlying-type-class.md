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
ms.openlocfilehash: b539f62e1e9c6b9bf11b176bd50f7dca63508ddd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)



