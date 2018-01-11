---
title: "cache_suballoc, classe │ Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::cache_suballoc
- allocators/stdext::cache_suballoc::allocate
- allocators/stdext::cache_suballoc::deallocate
dev_langs: C++
helpviewer_keywords:
- stdext::cache_suballoc
- stdext::cache_suballoc [C++], allocate
- stdext::cache_suballoc [C++], deallocate
ms.assetid: 9ea9c5e9-1dcc-45d0-b3a7-a56a93d88898
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d53e0438d73aa73a32f26d417ea60c4540162125
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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
|[cache_suballoc](#cache_suballoc)|Construit un objet de type `cache_suballoc`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[allocate](#allocate)|Alloue un bloc de mémoire.|  
|[deallocate](#deallocate)|Libère du stockage un nombre d'objets spécifié à partir d'une position spécifiée.|  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<allocators>  
  
 **Espace de noms :** stdext  
  
##  <a name="allocate"></a>  cache_suballoc::allocate  
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
  
##  <a name="cache_suballoc"></a>  cache_suballoc::cache_suballoc  
 Construit un objet de type `cache_suballoc`.  
  
```
cache_suballoc();
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="deallocate"></a>  cache_suballoc::deallocate  
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



