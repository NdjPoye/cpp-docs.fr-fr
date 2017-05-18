---
title: sync_per_thread, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdext::sync_per_thread
- sync_per_thread
- allocators/stdext::sync_per_thread
- allocators/stdext::sync_per_thread::allocate
- allocators/stdext::sync_per_thread::deallocate
- allocators/stdext::sync_per_thread::equals
dev_langs:
- C++
helpviewer_keywords:
- sync_per_thread class
ms.assetid: 47bf75f8-5b02-4760-b1d3-3099d08fe14c
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
ms.openlocfilehash: 71d2dd481c2c14303c71ec461ddcb5c041859531
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="syncperthread-class"></a>sync_per_thread, classe
Décrit un [filtre de synchronisation](../standard-library/allocators-header.md) qui fournit un objet cache distinct pour chaque thread.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Cache>  
class sync_per_thread
```  
  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Cache`|Type de cache associé au filtre de synchronisation. Il peut s’agir de [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) ou [cache_suballoc](../standard-library/cache-suballoc-class.md).|  
  
## <a name="remarks"></a>Notes  
 Les allocateurs qui utilisent `sync_per_thread` peuvent être considérés comme égaux même si des blocs alloués dans un thread ne peuvent pas être désalloués à partir d’un autre thread. Quand un de ces allocateurs est utilisé, les blocs de mémoire alloués dans un thread ne doivent pas être visibles pour d’autres threads. Dans la pratique, cela signifie qu’un conteneur qui utilise un de ces allocateurs doit uniquement être accessible par un seul thread.  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[allocate](#allocate)|Alloue un bloc de mémoire.|  
|[deallocate](#deallocate)|Libère du stockage un nombre d'objets spécifié à partir d'une position spécifiée.|  
|[equals](#equals)|Compare l'égalité de deux caches.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<allocators>  
  
 **Espace de noms :** stdext  
  
##  <a name="allocate"></a>  sync_per_thread::allocate  
 Alloue un bloc de mémoire.  
  
```
void *allocate(std::size_t count);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`count`|Nombre d’éléments du tableau à allouer.|  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne le résultat d’un appel à `cache::allocate(count)` sur l’objet cache appartenant au thread actuel. Si aucun objet cache n’a été alloué pour le thread actuel, elle commence par en allouer un.  
  
##  <a name="deallocate"></a>  sync_per_thread::deallocate  
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
 La fonction membre appelle `deallocate` sur l’objet cache appartenant au thread actuel. Si aucun objet cache n’a été alloué pour le thread actuel, elle commence par en allouer un.  
  
##  <a name="equals"></a>  sync_per_thread::equals  
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
 `false` si aucun objet cache n’a été alloué pour cet objet ou pour `Other` dans le thread actuel. Sinon, elle retourne le résultat de l’application de `operator==` aux deux objets caches.  
  
### <a name="remarks"></a>Notes  
  
## <a name="see-also"></a>Voir aussi  
 [\<allocators>](../standard-library/allocators-header.md)




