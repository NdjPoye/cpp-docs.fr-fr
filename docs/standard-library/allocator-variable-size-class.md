---
title: "allocator_variable_size, classe │ Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::allocator_variable_size
- allocators/stdext::allocators::allocator_variable_size
- stdext::allocators::allocator_variable_size
dev_langs: C++
helpviewer_keywords:
- stdext::allocator_variable_size
- stdext::allocators [C++], allocator_variable_size
ms.assetid: c3aa4105-ae45-4385-bbbe-9f23060478cb
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 43825113ac1c067354dd95c675a54a7741806108
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="allocatorvariablesize-class"></a>allocator_variable_size, classe
Décrit un objet qui gère l’allocation et la libération de stockage pour des objets de type `Type` à l’aide d’un cache de type [cache_freelist](../standard-library/cache-freelist-class.md) avec une longueur gérée par [max_variable_size](../standard-library/max-variable-size-class.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Type>  
class allocator_variable_size;
```  
  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Type`|Type des éléments alloués par l'allocateur.|  
  
## <a name="remarks"></a>Notes  
 La macro [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) transmet cette classe comme paramètre `name` dans l’instruction suivante : `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_variable_size), SYNC_DEFAULT, allocator_variable_size);`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<allocators>  
  
 **Espace de noms :** stdext  
  
## <a name="see-also"></a>Voir aussi  
 [\<allocators>](../standard-library/allocators-header.md)



