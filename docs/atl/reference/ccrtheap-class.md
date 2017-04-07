---
title: Classe de CCRTHeap | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCRTHeap
- ATLMEM/ATL::CCRTHeap
- ATLMEM/ATL::CCRTHeap::Allocate
- ATLMEM/ATL::CCRTHeap::Free
- ATLMEM/ATL::CCRTHeap::GetSize
- ATLMEM/ATL::CCRTHeap::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CCRTHeap class
ms.assetid: 321bd6c5-1856-4ff7-8590-95044a1209f7
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
ms.openlocfilehash: 1b4df6949794981867051437835d043196613afa
ms.lasthandoff: 02/24/2017

---
# <a name="ccrtheap-class"></a>CCRTHeap (classe)
Cette classe implémente [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) à l’aide des fonctions de tas CRT.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CCRTHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CCRTHeap::Allocate](#allocate)|Appelez cette méthode pour allouer un bloc de mémoire.|  
|[CCRTHeap::Free](#free)|Appelez cette méthode pour libérer un bloc de mémoire alloué par ce gestionnaire de mémoire.|  
|[CCRTHeap::GetSize](#getsize)|Appelez cette méthode pour obtenir la taille d’un bloc de mémoire alloué par ce gestionnaire de mémoire allouée.|  
|[CCRTHeap::Reallocate](#reallocate)|Appelez cette méthode pour réallouer la mémoire allouée par ce gestionnaire de mémoire.|  
  
## <a name="remarks"></a>Remarques  
 `CCRTHeap`implémente les fonctions, y compris de segment de mémoire à l’aide de la bibliothèque CRT fonctions d’allocation de mémoire [malloc](../../c-runtime-library/reference/malloc.md), [libre](../../c-runtime-library/reference/free.md), [realloc](../../c-runtime-library/reference/realloc.md), et [_msize](../../c-runtime-library/reference/msize.md).  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple de [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `IAtlMemMgr`  
  
 `CCRTHeap`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlmem.h  
  
##  <a name="allocate"></a>CCRTHeap::Allocate  
 Appelez cette méthode pour allouer un bloc de mémoire.  
  
```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nBytes`  
 Nombre demandé d'octets dans le nouveau bloc de mémoire.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur vers le début du bloc de mémoire nouvellement alloué.  
  
### <a name="remarks"></a>Remarques  
 Appelez [CCRTHeap::Free](#free) ou [CCRTHeap::Reallocate](#reallocate) pour libérer la mémoire allouée par cette méthode.  
  
 Implémenté à l’aide de [malloc](../../c-runtime-library/reference/malloc.md).  
  
##  <a name="free"></a>CCRTHeap::Free  
 Appelez cette méthode pour libérer un bloc de mémoire alloué par ce gestionnaire de mémoire.  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `p`  
 Pointeur vers la mémoire précédemment allouée par ce gestionnaire de mémoire. NULL est une valeur valide et n’a aucun effet.  
  
### <a name="remarks"></a>Remarques  
 Implémenté à l’aide de [libre](../../c-runtime-library/reference/free.md).  
  
##  <a name="getsize"></a>CCRTHeap::GetSize  
 Appelez cette méthode pour obtenir la taille d’un bloc de mémoire alloué par ce gestionnaire de mémoire allouée.  
  
```
virtual size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `p`  
 Pointeur vers la mémoire précédemment allouée par ce gestionnaire de mémoire.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la taille du bloc de mémoire allouée en octets.  
  
### <a name="remarks"></a>Remarques  
 Implémenté à l’aide de [_msize](../../c-runtime-library/reference/msize.md).  
  
##  <a name="reallocate"></a>CCRTHeap::Reallocate  
 Appelez cette méthode pour réallouer la mémoire allouée par ce gestionnaire de mémoire.  
  
```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `p`  
 Pointeur vers la mémoire précédemment allouée par ce gestionnaire de mémoire.  
  
 `nBytes`  
 Nombre demandé d'octets dans le nouveau bloc de mémoire.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur vers le début du bloc de mémoire nouvellement alloué.  
  
### <a name="remarks"></a>Notes  
 Appelez [CCRTHeap::Free](#free) pour libérer la mémoire allouée par cette méthode. Implémenté à l’aide de [realloc](../../c-runtime-library/reference/realloc.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)   
 [CComHeap (classe)](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap (classe)](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap (classe)](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap (classe)](../../atl/reference/cglobalheap-class.md)   
 [IAtlMemMgr (classe)](../../atl/reference/iatlmemmgr-class.md)

