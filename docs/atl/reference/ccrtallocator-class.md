---
title: Classe de CCRTAllocator | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCRTAllocator
- ATLCORE/ATL::CCRTAllocator
- ATLCORE/ATL::CCRTAllocator::Allocate
- ATLCORE/ATL::CCRTAllocator::Free
- ATLCORE/ATL::CCRTAllocator::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CCRTAllocator class
ms.assetid: 3e1b8cb0-859a-41ab-8e93-6f0b5ceca49d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 84c8f800e0b68e23fe33ca0a7e1c1d977bcc344e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ccrtallocator-class"></a>Classe de CCRTAllocator
Cette classe fournit des méthodes pour la gestion de la mémoire à l’aide des routines de mémoire CRT.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class ATL::CCRTAllocator
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CCRTAllocator::Allocate](#allocate)|(Statique) Appelez cette méthode pour allouer de mémoire.|  
|[CCRTAllocator::Free](#free)|(Statique) Appelez cette méthode pour libérer de la mémoire.|  
|[CCRTAllocator::Reallocate](#reallocate)|(Statique) Appelez cette méthode pour réallouer la mémoire.|  
  
## <a name="remarks"></a>Notes  
 Cette classe est utilisée par [CHeapPtr](../../atl/reference/cheapptr-class.md) pour fournir des routines d’allocation de la mémoire CRT. La classe équivalent, [CComAllocator](../../atl/reference/ccomallocator-class.md), fournit les mêmes méthodes que l’utilisation de COM routines.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atlcore.h  
  
##  <a name="allocate"></a>CCRTAllocator::Allocate  
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
 Alloue de la mémoire. Consultez [malloc](../../c-runtime-library/reference/malloc.md) pour plus d’informations.  
  
##  <a name="free"></a>CCRTAllocator::Free  
 Appelez cette fonction statique pour libérer de la mémoire.  
  
```
static void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `p`  
 Pointeur vers la mémoire allouée.  
  
### <a name="remarks"></a>Notes  
 Libère la mémoire allouée. Consultez [libre](../../c-runtime-library/reference/free.md) pour plus d’informations.  
  
##  <a name="reallocate"></a>CCRTAllocator::Reallocate  
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
  
### <a name="remarks"></a>Notes  
 Redimensionne la quantité de mémoire allouée. Consultez [realloc](../../c-runtime-library/reference/realloc.md) pour plus d’informations.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de CHeapPtr](../../atl/reference/cheapptr-class.md)   
 [Classe de CComAllocator](../../atl/reference/ccomallocator-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
