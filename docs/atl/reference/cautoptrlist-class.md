---
title: Classe de CAutoPtrList | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList::CAutoPtrList
dev_langs:
- C++
helpviewer_keywords:
- CAutoPtrList class
ms.assetid: 11de4aca-28b0-4ff2-a74a-cb602312ffbd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0887b0fdaeeaf498bacdc5eec66981656f34fed8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cautoptrlist-class"></a>Classe de CAutoPtrList
Cette classe fournit des méthodes utiles lors de la construction d’une liste de pointeurs intelligents.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<typename E>  
class CAutoPtrList : 
   public CAtlList<ATL::CAutoPtr<E>, CAutoPtrElementTraits<E>>
```  
  
#### <a name="parameters"></a>Paramètres  
 `E`  
 Le type de pointeur.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAutoPtrList::CAutoPtrList](#cautoptrlist)|Constructeur.|  
  
## <a name="remarks"></a>Notes  
 Cette classe fournit un constructeur et dérive des méthodes à partir de [CAtlList](../../atl/reference/catllist-class.md) et [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) à l’aide de la création d’un objet liste de stocker les pointeurs intelligents. La classe [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) fournit une fonction similaire pour un objet tableau.  
  
 Pour plus d’informations, consultez [Classes de Collection ATL](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CAutoPtrList`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atlcoll.h  
  
##  <a name="cautoptrlist"></a>CAutoPtrList::CAutoPtrList  
 Constructeur.  
  
```
CAutoPtrList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nBlockSize`  
 La taille du bloc, avec la valeur par défaut est 10.  
  
### <a name="remarks"></a>Notes  
 La taille de bloc est une mesure de la quantité de mémoire allouée lorsqu’un nouvel élément est requis. Tailles de bloc supérieures réduisent les appels aux routines d’allocation de mémoire, mais utilisent davantage de ressources.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de CAtlList](../../atl/reference/catllist-class.md)   
 [Classe de CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
