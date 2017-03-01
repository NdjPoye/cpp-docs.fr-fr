---
title: "cache_suballoc, classe │ Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdext.cache_suballoc
- allocators/stdext::cache_suballoc
- stdext::cache_suballoc
- cache_suballoc
dev_langs:
- C++
helpviewer_keywords:
- cache_suballoc class
ms.assetid: 9ea9c5e9-1dcc-45d0-b3a7-a56a93d88898
caps.latest.revision: 17
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 537930868e47fd1e947a99ff808d870532c38c58
ms.lasthandoff: 02/24/2017

---
# <a name="cachesuballoc-class"></a>cache_suballoc, classe
Définit un [allocateur de blocs](../standard-library/allocators-header.md) qui alloue et désalloue des blocs de mémoire de taille unique.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <std::size_t Sz, size_t Nelts = 20>  
class cache_suballoc
```  
  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Sz`|Nombre d’éléments du tableau à allouer.|  
  
## <a name="remarks"></a>Notes  
 La classe de modèle cache_suballoc stocke les blocs de mémoire désalloués dans une liste de libération avec une longueur illimitée, à l’aide de `freelist<sizeof(Type), max_unbounded>`, et sous-alloue des blocs de mémoire d’un segment plus grand alloué avec `operator new` quand la liste de libération est vide.  
  
 Chaque segment contient `Sz * Nelts` octets de mémoire utilisable et les données dont `operator new` et `operator delete` ont besoin. Les segments alloués ne sont jamais libérés.  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[cache_suballoc](#cache_suballoc__cache_suballoc)|Construit un objet de type `cache_suballoc`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[allocate](#cache_suballoc__allocate)|Alloue un bloc de mémoire.|  
|[deallocate](#cache_suballoc__deallocate)|Libère du stockage un nombre d'objets spécifié à partir d'une position spécifiée.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<allocators>  
  
 **Espace de noms :** stdext  
  
##  <a name="a-namecachesuballocallocatea--cachesuballocallocate"></a><a name="cache_suballoc__allocate"></a>  cache_suballoc::allocate  
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
  
##  <a name="a-namecachesuballoccachesuballoca--cachesuballoccachesuballoc"></a><a name="cache_suballoc__cache_suballoc"></a>  cache_suballoc::cache_suballoc  
 Construit un objet de type `cache_suballoc`.  
  
```
cache_suballoc();
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namecachesuballocdeallocatea--cachesuballocdeallocate"></a><a name="cache_suballoc__deallocate"></a>  cache_suballoc::deallocate  
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
  
## <a name="see-also"></a>Voir aussi  
 [\<allocators>](../standard-library/allocators-header.md)




