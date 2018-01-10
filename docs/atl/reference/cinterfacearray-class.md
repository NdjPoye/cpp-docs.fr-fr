---
title: Classe de CInterfaceArray | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray::CInterfaceArray
dev_langs: C++
helpviewer_keywords: CInterfaceArray class
ms.assetid: 1f29cf66-a086-4a7b-b6a8-64f73da39f79
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ece9858d0be171febaeb52e820e922665ac2a351
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cinterfacearray-class"></a>Classe de CInterfaceArray
Cette classe fournit des méthodes utiles lors de la construction d’un tableau de pointeurs d’interface COM.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class I, const IID* piid=& __uuidof(I)>  
class CInterfaceArray : 
   public CAtlArray<ATL::CComQIPtr<I, piid>,
                    CComQIPtrElementTraits<I, piid>>
```  
  
#### <a name="parameters"></a>Paramètres  
 `I`  
 Une interface COM en spécifiant le type de pointeur à stocker.  
  
 `piid`  
 Un pointeur vers l’IID de `I`.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CInterfaceArray::CInterfaceArray](#cinterfacearray)|Le constructeur pour le tableau de l’interface.|  
  
## <a name="remarks"></a>Notes  
 Cette classe fournit un constructeur et les méthodes dérivées pour la création d’un tableau de pointeurs d’interface COM. Utilisez [CInterfaceList](../../atl/reference/cinterfacelist-class.md) lorsqu’une liste est requise.  
  
 Pour plus d’informations, consultez [Classes de Collection ATL](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `CAtlArray`  
  
 `CInterfaceArray`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atlcoll.h  
  
##  <a name="cinterfacearray"></a>CInterfaceArray::CInterfaceArray  
 Constructeur.  
  
```
CInterfaceArray() throw();
```  
  
### <a name="remarks"></a>Notes  
 Initialise le tableau de pointeurs intelligents.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe CAtlArray](../../atl/reference/catlarray-class.md)   
 [Classe de CComQIPtr](../../atl/reference/ccomqiptr-class.md)   
 [Classe de CComQIPtrElementTraits](../../atl/reference/ccomqiptrelementtraits-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
