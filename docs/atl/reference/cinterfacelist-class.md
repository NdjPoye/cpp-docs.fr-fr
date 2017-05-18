---
title: Classe de CInterfaceList | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInterfaceList
- ATLCOLL/ATL::CInterfaceList
- ATLCOLL/ATL::CInterfaceList::CInterfaceList
dev_langs:
- C++
helpviewer_keywords:
- CInterfaceList class
ms.assetid: 2077764d-25e5-4b3d-96c8-08a287bbcd25
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
ms.openlocfilehash: 50d86163080c5a0d0a7bb9ed6d77a40ac73722e7
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cinterfacelist-class"></a>CInterfaceList (classe)
Cette classe fournit des méthodes utiles lors de la construction d’une liste de pointeurs d’interface COM.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class I, const IID* piid =& __uuidof(I)>  
class CInterfaceList 
   : public CAtlList<ATL::CComQIPtr<I, piid>,
                     CComQIPtrElementTraits<I, piid>>
```  
  
#### <a name="parameters"></a>Paramètres  
 `I`  
 Une interface COM qui spécifie le type de pointeur à stocker.  
  
 `piid`  
 Un pointeur vers l’IID de `I`.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CInterfaceList::CInterfaceList](#cinterfacelist)|Le constructeur de la liste d’interface.|  
  
## <a name="remarks"></a>Notes  
 Cette classe fournit un constructeur et méthodes dérivées pour la création d’une liste de pointeurs d’interface COM. Utilisez [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) lorsqu’un tableau est requis.  
  
 Pour plus d’informations, consultez [Classes de Collection ATL](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CInterfaceList`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcoll.h  
  
##  <a name="cinterfacelist"></a>CInterfaceList::CInterfaceList  
 Le constructeur de la liste d’interface.  
  
```
CInterfaceList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nBlockSize`  
 Taille de bloc par défaut est 10.  
  
### <a name="remarks"></a>Remarques  
 La taille de bloc est une mesure de la quantité de mémoire allouée lorsqu’un nouvel élément est requis. Tailles de bloc supérieures réduisent les appels aux routines d’allocation de mémoire, mais utilisent davantage de ressources.  
  
## <a name="see-also"></a>Voir aussi  
 [CAtlList (classe)](../../atl/reference/catllist-class.md)   
 [CComQIPtr (classe)](../../atl/reference/ccomqiptr-class.md)   
 [CComQIPtrElementTraits (classe)](../../atl/reference/ccomqiptrelementtraits-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

