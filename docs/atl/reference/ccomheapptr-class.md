---
title: Classe de CComHeapPtr | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComHeapPtr
- ATLBASE/ATL::CComHeapPtr
- ATLBASE/ATL::CComHeapPtr::CComHeapPtr
dev_langs:
- C++
helpviewer_keywords:
- CComHeapPtr class
ms.assetid: bd08b53d-da2b-43ab-a79c-e7c8dbbc5994
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 0e5196a98b8fd76b2e7e791fd2cd9549099a1cc9
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="ccomheapptr-class"></a>CComHeapPtr (classe)
Une classe de pointeur intelligent pour la gestion des pointeurs de tas.  
  
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
  
## <a name="remarks"></a>Remarques  
 `CComHeapPtr`dérive de `CHeapPtr`, mais utilise [CComAllocator](../../atl/reference/ccomallocator-class.md) d’allocation de mémoire à l’aide des routines de COM. Consultez la page [CHeapPtr](../../atl/reference/cheapptr-class.md) et [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) pour les méthodes disponibles.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)  
  
 [CHeapPtr](../../atl/reference/cheapptr-class.md)  
  
 `CComHeapPtr`  
  
## <a name="requirements"></a>Spécifications  
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
  
### <a name="remarks"></a>Remarques  
 Le pointeur du tas peut être éventuellement créé à l’aide d’un fichier `CComHeapPtr` objet. Dans ce cas, la nouvelle `CComHeapPtr` objet assume la responsabilité de gérer le nouveau pointeur et les ressources.  
  
## <a name="see-also"></a>Voir aussi  
 [CHeapPtr (classe)](../../atl/reference/cheapptr-class.md)   
 [CHeapPtrBase (classe)](../../atl/reference/cheapptrbase-class.md)   
 [CComAllocator (classe)](../../atl/reference/ccomallocator-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

