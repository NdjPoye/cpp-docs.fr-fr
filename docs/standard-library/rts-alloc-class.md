---
title: rts_alloc, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdext::rts_alloc
- allocators/stdext::rts_alloc
- rts_alloc
- allocators/stdext::rts_alloc::allocate
- allocators/stdext::rts_alloc::deallocate
- allocators/stdext::rts_alloc::equals
dev_langs:
- C++
helpviewer_keywords:
- rts_alloc class
ms.assetid: ab41bffa-83d1-4a1c-87b9-5707d516931f
caps.latest.revision: 19
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: fe127f896fa902f4a8cdb44454cf6e4c5f449e79
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="rtsalloc-class"></a>rts_alloc, classe
La classe de modèle rts_alloc décrit un [filtre](../standard-library/allocators-header.md) qui contient un tableau d’instances de cache et détermine l’instance à utiliser pour l’allocation et la libération au moment de l’exécution plutôt qu’au moment de la compilation.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Cache>  
class rts_alloc
```  
  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Cache`|Type d'instances de cache contenu dans le tableau. Il peut s’agir de [cache_chunklist Class](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) ou [cache_suballoc](../standard-library/cache-suballoc-class.md).|  
  
## <a name="remarks"></a>Notes  
 Cette classe de modèle contient plusieurs instances d'allocateur de bloc et détermine quelle instance utiliser pour l'allocation ou la désallocation au moment de l'exécution plutôt qu'au moment de la compilation. Elle est utilisée avec les compilateurs qui ne peuvent pas compiler la reliaison.  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[allocate](#allocate)|Alloue un bloc de mémoire.|  
|[deallocate](#deallocate)|Libère du stockage un nombre d'objets spécifié à partir d'une position spécifiée.|  
|[equals](#equals)|Compare l'égalité de deux caches.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<allocators>  
  
 **Espace de noms :** stdext  
  
##  <a name="allocate"></a>  rts_alloc::allocate  
 Alloue un bloc de mémoire.  
  
```
void *allocate(std::size_t count);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`count`|Nombre d’éléments du tableau à allouer.|  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’objet alloué.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne `caches[_IDX].allocate(count)`, où l’index `_IDX` est déterminé par la taille de bloc demandé `count`, ou, si `count` est trop volumineux, il retourne `operator new(count)`. `cache`, qui représente l’objet cache.  
  
##  <a name="deallocate"></a>  rts_alloc::deallocate  
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
 La fonction membre appelle `caches[_IDX].deallocate(ptr, count)`, où l’index `_IDX` est déterminé par la taille de bloc demandé `count`, ou, si `count` est trop volumineux, il retourne `operator delete(ptr)`.  
  
##  <a name="equals"></a>  rts_alloc::equals  
 Compare l'égalité de deux caches.  
  
```
bool equals(const sync<_Cache>& _Other) const;
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`_Cache`|Objet cache associé au filtre.|  
|`_Other`|Objet cache pour comparer l’égalité.|  
  
### <a name="remarks"></a>Notes  
 `true` si le résultat est `caches[0].equals(other.caches[0])`. Sinon, `false`. `caches` représente le tableau d’objets cache.  
  
## <a name="see-also"></a>Voir aussi  
 [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)   
 [\<allocators>](../standard-library/allocators-header.md)




