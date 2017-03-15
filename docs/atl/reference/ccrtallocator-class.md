---
title: Classe de CCRTAllocator | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCRTAllocator
dev_langs:
- C++
helpviewer_keywords:
- CCRTAllocator class
ms.assetid: 3e1b8cb0-859a-41ab-8e93-6f0b5ceca49d
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 5154a095409705e96dee6f52c67d7c23b0e6691f
ms.lasthandoff: 02/24/2017

---
# <a name="ccrtallocator-class"></a>CCRTAllocator (classe)
Cette classe fournit des méthodes pour la gestion de la mémoire à l’aide des routines de mémoire CRT.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class ATL::CCRTAllocator
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CCRTAllocator::Allocate](#allocate)|(Statique) Appelez cette méthode pour allouer de la mémoire.|  
|[CCRTAllocator::Free](#free)|(Statique) Appelez cette méthode pour libérer de la mémoire.|  
|[CCRTAllocator::Reallocate](#reallocate)|(Statique) Appelez cette méthode pour réallouer de la mémoire.|  
  
## <a name="remarks"></a>Notes  
 Cette classe est utilisée par [CHeapPtr](../../atl/reference/cheapptr-class.md) pour fournir des routines d’allocation de la mémoire CRT. La classe homologue, [CComAllocator](../../atl/reference/ccomallocator-class.md), fournit les mêmes méthodes que l’utilisation de COM routines.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcore.h  
  
##  <a name="a-nameallocatea--ccrtallocatorallocate"></a><a name="allocate"></a>CCRTAllocator::Allocate  
 Appelez cette fonction statique pour allouer de la mémoire.  
  
```
static __declspec(allocator) void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nBytes`  
 Nombre d'octets à allouer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur void vers l'espace alloué, ou NULL si la mémoire disponible est insuffisante.  
  
### <a name="remarks"></a>Notes  
 Alloue de la mémoire. Consultez la page [malloc](../../c-runtime-library/reference/malloc.md) pour plus de détails.  
  
##  <a name="a-namefreea--ccrtallocatorfree"></a><a name="free"></a>CCRTAllocator::Free  
 Appelez cette fonction pour libérer de la mémoire statique.  
  
```
static void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `p`  
 Pointeur vers la mémoire allouée.  
  
### <a name="remarks"></a>Remarques  
 Libère la mémoire allouée. Consultez la page [libre](../../c-runtime-library/reference/free.md) pour plus de détails.  
  
##  <a name="a-namereallocatea--ccrtallocatorreallocate"></a><a name="reallocate"></a>CCRTAllocator::Reallocate  
 Appelez cette fonction statique pour réallouer de la mémoire.  
  
```
static __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `p`  
 Pointeur vers la mémoire allouée.  
  
 `nBytes`  
 Nombre d'octets à réallouer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur void vers l'espace alloué, ou NULL si la mémoire est insuffisante.  
  
### <a name="remarks"></a>Remarques  
 Redimensionne la quantité de mémoire allouée. Consultez la page [realloc](../../c-runtime-library/reference/realloc.md) pour plus de détails.  
  
## <a name="see-also"></a>Voir aussi  
 [CHeapPtr (classe)](../../atl/reference/cheapptr-class.md)   
 [CComAllocator (classe)](../../atl/reference/ccomallocator-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

