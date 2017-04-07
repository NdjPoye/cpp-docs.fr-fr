---
title: Classe de CComAllocator | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAllocator
- ATLBASE/ATL::CComAllocator
- ATLBASE/ATL::CComAllocator::Allocate
- ATLBASE/ATL::CComAllocator::Free
- ATLBASE/ATL::CComAllocator::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CComAllocator class
ms.assetid: 0cd706fd-0c7b-42d3-9054-febe2966fc8e
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
ms.openlocfilehash: d395d347e81b24462a41de5ae3b9d8791d7f82fd
ms.lasthandoff: 02/24/2017

---
# <a name="ccomallocator-class"></a>CComAllocator (classe)
Cette classe fournit des méthodes pour la gestion de la mémoire à l’aide des routines de mémoire COM.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CComAllocator
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CComAllocator::Allocate](#allocate)|Appelez cette méthode statique pour allouer de la mémoire.|  
|[CComAllocator::Free](#free)|Appelez cette méthode statique pour libérer de la mémoire allouée.|  
|[CComAllocator::Reallocate](#reallocate)|Appelez cette méthode statique pour réallouer de la mémoire.|  
  
## <a name="remarks"></a>Remarques  
 Cette classe est utilisée par [CComHeapPtr](../../atl/reference/ccomheapptr-class.md) pour fournir des routines d’allocation de la mémoire COM. La classe homologue, [CCRTAllocator](../../atl/reference/ccrtallocator-class.md), fournit les mêmes méthodes que l’utilisation de routines de la bibliothèque CRT.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
##  <a name="allocate"></a>CComAllocator::Allocate  
 Appelez cette fonction statique pour allouer de la mémoire.  
  
```
static void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nBytes`  
 Nombre d'octets à allouer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur void vers l'espace alloué, ou NULL si la mémoire disponible est insuffisante.  
  
### <a name="remarks"></a>Remarques  
 Alloue de la mémoire. Consultez la page [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727) pour plus de détails.  
  
##  <a name="free"></a>CComAllocator::Free  
 Appelez cette fonction statique pour libérer de la mémoire allouée.  
  
```
static void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `p`  
 Pointeur vers la mémoire allouée.  
  
### <a name="remarks"></a>Notes  
 Libère la mémoire allouée. Consultez la page [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722) pour plus de détails.  
  
##  <a name="reallocate"></a>CComAllocator::Reallocate  
 Appelez cette fonction statique pour réallouer de la mémoire.  
  
```
static void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `p`  
 Pointeur vers la mémoire allouée.  
  
 `nBytes`  
 Nombre d'octets à réallouer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur void vers l’espace alloué, ou NULL si la mémoire est insuffisante  
  
### <a name="remarks"></a>Remarques  
 Redimensionne la quantité de mémoire allouée. Consultez la page [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280) pour plus de détails.  
  
## <a name="see-also"></a>Voir aussi  
 [CComHeapPtr (classe)](../../atl/reference/ccomheapptr-class.md)   
 [CCRTAllocator (classe)](../../atl/reference/ccrtallocator-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

