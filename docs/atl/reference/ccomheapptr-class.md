---
title: Classe de CComHeapPtr | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComHeapPtr
- ATLBASE/ATL::CComHeapPtr
- ATLBASE/ATL::CComHeapPtr::CComHeapPtr
dev_langs: C++
helpviewer_keywords: CComHeapPtr class
ms.assetid: bd08b53d-da2b-43ab-a79c-e7c8dbbc5994
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8619c050ecc356e1445991b625da00c04f462848
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomheapptr-class"></a>Classe de CComHeapPtr
Une classe de pointeur intelligent pour la gestion des pointeurs de segment de mémoire.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<typename T>  
class CComHeapPtr : public CHeapPtr<T, CComAllocator>
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Le type d’objet à stocker sur le tas.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComHeapPtr::CComHeapPtr](#ccomheapptr)|Constructeur.|  
  
## <a name="remarks"></a>Notes  
 `CComHeapPtr`dérive de `CHeapPtr`, mais utilise [CComAllocator](../../atl/reference/ccomallocator-class.md) pour allouer de la mémoire à l’aide des routines de COM. Consultez [CHeapPtr](../../atl/reference/cheapptr-class.md) et [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) pour les méthodes disponibles.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)  
  
 [CHeapPtr](../../atl/reference/cheapptr-class.md)  
  
 `CComHeapPtr`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atlbase.h  
  
##  <a name="ccomheapptr"></a>CComHeapPtr::CComHeapPtr  
 Constructeur.  
  
```
CComHeapPtr() throw();
explicit CComHeapPtr(T* pData) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `pData`  
 Objet `CComHeapPtr` existant.  
  
### <a name="remarks"></a>Notes  
 Le pointeur du tas peut être éventuellement créé à l’aide d’un existant `CComHeapPtr` objet. Dans ce cas, la nouvelle `CComHeapPtr` objet assume la responsabilité de gérer les ressources et le nouveau pointeur.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de CHeapPtr](../../atl/reference/cheapptr-class.md)   
 [Classe de CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)   
 [Classe de CComAllocator](../../atl/reference/ccomallocator-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
