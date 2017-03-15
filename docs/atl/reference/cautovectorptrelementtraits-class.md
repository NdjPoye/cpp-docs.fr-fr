---
title: Classe de CAutoVectorPtrElementTraits | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAutoVectorPtrElementTraits<T>
- ATL.CAutoVectorPtrElementTraits
- ATL.CAutoVectorPtrElementTraits<T>
- ATL::CAutoVectorPtrElementTraits
- CAutoVectorPtrElementTraits
dev_langs:
- C++
helpviewer_keywords:
- CAutoVectorPtrElementTraits class
ms.assetid: 16b81a56-55fb-46ca-b376-66a1884231a6
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
ms.openlocfilehash: d7b7418b713993f539f56e70715296d5af265d28
ms.lasthandoff: 02/24/2017

---
# <a name="cautovectorptrelementtraits-class"></a>CAutoVectorPtrElementTraits (classe)
Cette classe fournit des méthodes et fonctions statiques typedefs utiles pour la création de collections de pointeurs intelligents à l’aide de nouveau vecteur et supprimer des opérateurs.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <typename T>  
class CAutoVectorPtrElementTraits : 
   public CDefaultElementTraits<ATL::CAutoVectorPtr<T>>
```    
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Le type de pointeur.  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAutoVectorPtrElementTraits::INARGTYPE](#inargtype)|Le type de données à utiliser pour l’ajout d’éléments à l’objet de classe de collection.|  
|[CAutoVectorPtrElementTraits::OUTARGTYPE](#outargtype)|Le type de données à utiliser pour récupérer des éléments de l’objet de classe de collection.|  
  
## <a name="remarks"></a>Remarques  
 Cette classe fournit des méthodes, des fonctions statiques et typedefs pour contribuer à la création d’objets de classe de collection qui contient des pointeurs intelligents. Contrairement aux [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md), cette classe vector nouveaux et supprimer des opérateurs.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CAutoVectorPtrElementTraits`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcoll.h  
  
##  <a name="a-nameinargtypea--cautovectorptrelementtraitsinargtype"></a><a name="inargtype"></a>CAutoVectorPtrElementTraits::INARGTYPE  
 Le type de données à utiliser pour l’ajout d’éléments à l’objet de classe de collection.  
  
```
typedef CAutoVectorPtr<T>& INARGTYPE;
```  
  
##  <a name="a-nameoutargtypea--cautovectorptrelementtraitsoutargtype"></a><a name="outargtype"></a>CAutoVectorPtrElementTraits::OUTARGTYPE  
 Le type de données à utiliser pour récupérer des éléments de l’objet de classe de collection.  
  
```
typedef T*& OUTARGTYPE;
```  
  
## <a name="see-also"></a>Voir aussi  
 [CDefaultElementTraits (classe)](../../atl/reference/cdefaultelementtraits-class.md)   
 [CAutoVectorPtr (classe)](../../atl/reference/cautovectorptr-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

