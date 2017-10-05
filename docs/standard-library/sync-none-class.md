---
title: sync_none, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::sync_none
- allocators/stdext::sync_none::allocate
- allocators/stdext::sync_none::deallocate
- allocators/stdext::sync_none::equals
dev_langs:
- C++
helpviewer_keywords:
- stdext::sync_none
- stdext::sync_none [C++], allocate
- stdext::sync_none [C++], deallocate
- stdext::sync_none [C++], equals
ms.assetid: f7473cee-14f3-4fe1-88bc-68cd085e59e1
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.openlocfilehash: 6cd96ec71098bed30fdbbb0fa84cfd7e61e33a7b
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="syncnone-class"></a>sync_none, classe
Décrit un [filtre de synchronisation](../standard-library/allocators-header.md) qui ne fournit aucune synchronisation.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Cache>  
class sync_none
```  
  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Cache`|Type de cache associé au filtre de synchronisation. Il peut s’agir de [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) ou [cache_suballoc](../standard-library/cache-suballoc-class.md).|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[allocate](#allocate)|Alloue un bloc de mémoire.|  
|[deallocate](#deallocate)|Libère du stockage un nombre d'objets spécifié à partir d'une position spécifiée.|  
|[equals](#equals)|Compare l'égalité de deux caches.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<allocators>  
  
 **Espace de noms :** stdext  
  
##  <a name="allocate"></a>  sync_none::allocate  
 Alloue un bloc de mémoire.  
  
```
void *allocate(std::size_t count);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`count`|Nombre d’éléments du tableau à allouer.|  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne `cache.allocate(count)`, où `cache` est l’objet cache.  
  
##  <a name="deallocate"></a>  sync_none::deallocate  
 Libère du stockage un nombre d'objets spécifié à partir d'une position spécifiée.  
  
```
void deallocate(void* ptr, std::size_t count);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`ptr`|Pointeur vers le premier objet à désallouer dans le stockage.|  
|`count`|Nombre d’objets à désallouer dans le stockage.|  
  
### <a name="remarks"></a>Notes  
 La fonction membre appelle `cache.deallocate(ptr, count)`, où `cache` représente l’objet cache.  
  
##  <a name="equals"></a>  sync_none::equals  
 Compare l'égalité de deux caches.  
  
```
bool equals(const sync<Cache>& Other) const;
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Cache`|L’objet cache du filtre de synchronisation.|  
|`Other`|Objet cache dont l’égalité est à comparer.|  
  
### <a name="return-value"></a>Valeur de retour  
 La fonction membre retourne toujours `true`.  
  
### <a name="remarks"></a>Notes  
  
## <a name="see-also"></a>Voir aussi  
 [\<allocators>](../standard-library/allocators-header.md)




