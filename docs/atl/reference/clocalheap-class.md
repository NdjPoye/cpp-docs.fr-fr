---
title: Classe de CLocalHeap | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CLocalHeap
- ATLMEM/ATL::CLocalHeap
- ATLMEM/ATL::CLocalHeap::Allocate
- ATLMEM/ATL::CLocalHeap::Free
- ATLMEM/ATL::CLocalHeap::GetSize
- ATLMEM/ATL::CLocalHeap::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CLocalHeap class
ms.assetid: 1ffa87a5-5fc8-4f8d-8809-58e87e963bd2
caps.latest.revision: 20
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
ms.openlocfilehash: 6a5caaa360970578aee4432fd40af9aa0e391d90
ms.lasthandoff: 02/24/2017

---
# <a name="clocalheap-class"></a>CLocalHeap (classe)
Cette classe implémente [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) à l’aide de fonctions Win32 du tas local.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CLocalHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CLocalHeap::Allocate](#allocate)|Appelez cette méthode pour allouer un bloc de mémoire.|  
|[CLocalHeap::Free](#free)|Appelez cette méthode pour libérer un bloc de mémoire alloué par ce gestionnaire de mémoire.|  
|[CLocalHeap::GetSize](#getsize)|Appelez cette méthode pour obtenir la taille d’un bloc de mémoire alloué par ce gestionnaire de mémoire allouée.|  
|[CLocalHeap::Reallocate](#reallocate)|Appelez cette méthode pour réallouer la mémoire allouée par ce gestionnaire de mémoire.|  
  
## <a name="remarks"></a>Remarques  
 `CLocalHeap`implémente les fonctions d’allocation de mémoire à l’aide de fonctions Win32 du tas local.  
  
> [!NOTE]
>  Les fonctions du tas local sont plus lentes que d’autres fonctions de gestion de mémoire et ne fournissent pas autant de fonctionnalités. Par conséquent, les nouvelles applications doivent utiliser le [fonctions de tas](http://msdn.microsoft.com/library/windows/desktop/aa366711). Ils sont disponibles dans le [CWin32Heap](../../atl/reference/cwin32heap-class.md) (classe).  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple de [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `IAtlMemMgr`  
  
 `CLocalHeap`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlmem.h  
  
##  <a name="allocate"></a>CLocalHeap::Allocate  
 Appelez cette méthode pour allouer un bloc de mémoire.  
  
```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nBytes`  
 Nombre demandé d'octets dans le nouveau bloc de mémoire.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur vers le début du bloc de mémoire nouvellement alloué.  
  
### <a name="remarks"></a>Notes  
 Appelez [CLocalHeap::Free](#free) ou [CLocalHeap::Reallocate](#reallocate) pour libérer la mémoire allouée par cette méthode.  
  
 Implémenté à l’aide de [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723) avec un paramètre d’indicateur de **LMEM_FIXED**.  
  
##  <a name="free"></a>CLocalHeap::Free  
 Appelez cette méthode pour libérer un bloc de mémoire alloué par ce gestionnaire de mémoire.  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `p`  
 Pointeur vers la mémoire précédemment allouée par ce gestionnaire de mémoire. NULL est une valeur valide et n’a aucun effet.  
  
### <a name="remarks"></a>Remarques  
 Implémenté à l’aide de [LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730).  
  
##  <a name="getsize"></a>CLocalHeap::GetSize  
 Appelez cette méthode pour obtenir la taille d’un bloc de mémoire alloué par ce gestionnaire de mémoire allouée.  
  
```
virtual size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `p`  
 Pointeur vers la mémoire précédemment allouée par ce gestionnaire de mémoire.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la taille du bloc de mémoire allouée en octets.  
  
### <a name="remarks"></a>Notes  
 Implémenté à l’aide de [LocalSize](http://msdn.microsoft.com/library/windows/desktop/aa366745).  
  
##  <a name="reallocate"></a>CLocalHeap::Reallocate  
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
 Appelez [CLocalHeap::Free](#free) pour libérer la mémoire allouée par cette méthode.  
  
 Implémenté à l’aide de [LocalReAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366742).  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)   
 [CComHeap (classe)](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap (classe)](../../atl/reference/cwin32heap-class.md)   
 [CGlobalHeap (classe)](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap (classe)](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr (classe)](../../atl/reference/iatlmemmgr-class.md)

