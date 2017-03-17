---
title: Classe de CElementTraitsBase | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase::INARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::OUTARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::CopyElements
- ATLCOLL/ATL::CElementTraitsBase::RelocateElements
dev_langs:
- C++
helpviewer_keywords:
- CElementTraitsBase class
ms.assetid: 75284caf-347e-4355-a7d8-efc708dd514a
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: a06af7698afb24c1c2391b762673c7e3633018d4
ms.lasthandoff: 02/24/2017

---
# <a name="celementtraitsbase-class"></a>CElementTraitsBase (classe)
Cette classe fournit la copie par défaut et les méthodes d’une classe de collection de déplacement.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<typename T>  
class CElementTraitsBase
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Le type de données à stocker dans la collection.  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CElementTraitsBase::INARGTYPE](#inargtype)|Le type de données à utiliser pour l’ajout d’éléments à l’objet de classe de collection.|  
|[CElementTraitsBase::OUTARGTYPE](#outargtype)|Le type de données à utiliser pour récupérer des éléments de l’objet de classe de collection.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CElementTraitsBase::CopyElements](#copyelements)|Appelez cette méthode pour copier les éléments stockés dans un objet de classe de collection.|  
|[CElementTraitsBase::RelocateElements](#relocateelements)|Appelez cette méthode pour déplacer des éléments stockés dans un objet de classe de collection.|  
  
## <a name="remarks"></a>Notes  
 Cette classe de base définit des méthodes pour la copie et déplacement d’éléments dans une classe de collection. Elle est utilisée par les classes [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md), [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md), et [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md).  
  
 Pour plus d’informations, consultez [Classes de Collection ATL](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcoll.h  
  
##  <a name="copyelements"></a>CElementTraitsBase::CopyElements  
 Appelez cette méthode pour copier les éléments stockés dans un objet de classe de collection.  
  
```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDest`  
 Pointeur vers le premier élément qui reçoit les données copiées.  
  
 `pSrc`  
 Pointeur vers le premier élément à copier.  
  
 `nElements`  
 Nombre d'éléments à copier.  
  
### <a name="remarks"></a>Remarques  
 Les éléments source et de destination ne doivent pas se chevaucher.  
  
##  <a name="inargtype"></a>CElementTraitsBase::INARGTYPE  
 Le type de données à utiliser pour ajouter des éléments à la collection.  
  
```
typedef const T& INARGTYPE;
```  
  
##  <a name="outargtype"></a>CElementTraitsBase::OUTARGTYPE  
 Le type de données à utiliser pour récupérer des éléments de la collection.  
  
```
typedef T& OUTARGTYPE;
```  
  
##  <a name="relocateelements"></a>CElementTraitsBase::RelocateElements  
 Appelez cette méthode pour déplacer des éléments stockés dans un objet de classe de collection.  
  
```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDest`  
 Pointeur vers le premier élément qui reçoit les données déplacées.  
  
 `pSrc`  
 Pointeur vers le premier élément à déplacer.  
  
 `nElements`  
 Le nombre d’éléments à déplacer.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode appelle [memmove](../../c-runtime-library/reference/memmove-wmemmove.md), ce qui est suffisant pour la plupart des types de données. Si les objets déplacés contiennent des pointeurs vers des membres de leurs propre, cette méthode devez être remplacée.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

