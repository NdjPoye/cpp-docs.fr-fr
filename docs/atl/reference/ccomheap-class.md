---
title: Classe de CComHeap | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComHeap
- ATLCOMMEM/ATL::CComHeap
- ATLCOMMEM/ATL::CComHeap::Allocate
- ATLCOMMEM/ATL::CComHeap::Free
- ATLCOMMEM/ATL::CComHeap::GetSize
- ATLCOMMEM/ATL::CComHeap::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CComHeap class
ms.assetid: c74183ce-98ae-46fb-b186-93ea4cf0222b
caps.latest.revision: 22
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 323ad1aed4bae706ecbf66de769e33873f20c149
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="ccomheap-class"></a>CComHeap (classe)
Cette classe implémente [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) en utilisant les fonctions d’allocation de mémoire COM.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CComHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CComHeap::Allocate](#allocate)|Appelez cette méthode pour allouer un bloc de mémoire.|  
|[CComHeap::Free](#free)|Appelez cette méthode pour libérer un bloc de mémoire alloué par ce gestionnaire de mémoire.|  
|[CComHeap::GetSize](#getsize)|Appelez cette méthode pour obtenir la taille d’un bloc de mémoire alloué par ce gestionnaire de mémoire allouée.|  
|[CComHeap::Reallocate](#reallocate)|Appelez cette méthode pour réallouer la mémoire allouée par ce gestionnaire de mémoire.|  
  
## <a name="remarks"></a>Remarques  
 `CComHeap`implémente des fonctions d’allocation de mémoire à l’aide des fonctions d’allocation du COM, y compris [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727), [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722), [IMalloc::GetSize](http://msdn.microsoft.com/library/windows/desktop/ms691226), et [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280). La quantité maximale de mémoire pouvant être allouée est égale à **INT_MAX** (2147483647) octets.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple de [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `IAtlMemMgr`  
  
 `CComHeap`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** ATLComMem.h  
  
##  <a name="allocate"></a>CComHeap::Allocate  
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
 Appelez [CComHeap::Free](#free) ou [CComHeap::Reallocate](#reallocate) pour libérer la mémoire allouée par cette méthode.  
  
 Implémenté à l’aide de [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727).  
  
##  <a name="free"></a>CComHeap::Free  
 Appelez cette méthode pour libérer un bloc de mémoire alloué par ce gestionnaire de mémoire.  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `p`  
 Pointeur vers la mémoire précédemment allouée par ce gestionnaire de mémoire. NULL est une valeur valide et n’a aucun effet.  
  
### <a name="remarks"></a>Remarques  
 Implémenté à l’aide de [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722).  
  
##  <a name="getsize"></a>CComHeap::GetSize  
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
 Implémenté à l’aide de [IMalloc::GetSize](http://msdn.microsoft.com/library/windows/desktop/ms691226).  
  
##  <a name="reallocate"></a>CComHeap::Reallocate  
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
  
### <a name="remarks"></a>Remarques  
 Appelez [CComHeap::Free](#free) pour libérer la mémoire allouée par cette méthode.  
  
 Implémenté à l’aide de [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280).  
  
## <a name="see-also"></a>Voir aussi  
 [DynamicConsumer, exemple](../../visual-cpp-samples.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)   
 [CWin32Heap (classe)](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap (classe)](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap (classe)](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap (classe)](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr (classe)](../../atl/reference/iatlmemmgr-class.md)

