---
title: Classe de CStringRefElementTraits | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits::CompareElements
- ATLCOLL/ATL::CStringRefElementTraits::CompareElementsOrdered
- ATLCOLL/ATL::CStringRefElementTraits::Hash
dev_langs:
- C++
helpviewer_keywords:
- CStringRefElementTraits class
ms.assetid: cc15062d-5627-46cc-ac2b-1744afdc2dbd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c89a1e0d87550614fb8991ac3efe6bf369d147e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cstringrefelementtraits-class"></a>Classe de CStringRefElementTraits
Cette classe fournit des fonctions statiques relatives aux chaînes stockées dans les objets de classe de collection. Les objets de chaîne sont traitées en tant que références.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <typename T>  
class CStringRefElementTraits : public CElementTraitsBase<T>
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Le type de données à stocker dans la collection.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CStringRefElementTraits::CompareElements](#compareelements)|Appelez cette fonction statique pour comparer deux éléments de chaîne pour l’égalité.|  
|[CStringRefElementTraits::CompareElementsOrdered](#compareelementsordered)|Appelez cette fonction statique pour comparer deux éléments de chaîne.|  
|[CStringRefElementTraits::Hash](#hash)|Appelez cette fonction statique pour calculer une valeur de hachage pour l’élément de la chaîne donnée.|  
  
## <a name="remarks"></a>Notes  
 Cette classe fournit des fonctions statiques pour la comparaison de chaînes et pour la création d’une valeur de hachage. Ces fonctions sont utiles lors de l’utilisation d’une classe de collection pour stocker les données de type chaîne. Contrairement aux [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md) et [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md), `CStringRefElementTraits` provoque la `CString` arguments à passer en tant que **const CString &** références.  
  
 Pour plus d’informations, consultez [Classes de Collection ATL](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringRefElementTraits`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atlcoll.h  
  
##  <a name="compareelements"></a>CStringRefElementTraits::CompareElements  
 Appelez cette fonction statique pour comparer deux éléments de chaîne pour l’égalité.  
  
```
static bool CompareElements(INARGTYPE element1, INARGTYPE element2) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `element1`  
 Le premier élément de chaîne.  
  
 `element2`  
 Le deuxième élément de chaîne.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si les éléments sont égaux, false dans le cas contraire.  
  
##  <a name="compareelementsordered"></a>CStringRefElementTraits::CompareElementsOrdered  
 Appelez cette fonction statique pour comparer deux éléments de chaîne.  
  
```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `str1`  
 Le premier élément de chaîne.  
  
 `str2`  
 Le deuxième élément de chaîne.  
  
### <a name="return-value"></a>Valeur de retour  
 Zéro si les chaînes sont identiques, < 0 si `str1` est inférieure à `str2`, ou 0 > Si `str1` est supérieur à `str2`. Le [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) méthode est utilisée pour effectuer des comparaisons.  
  
##  <a name="hash"></a>CStringRefElementTraits::Hash  
 Appelez cette fonction statique pour calculer une valeur de hachage pour l’élément de la chaîne donnée.  
  
```
static ULONG Hash(INARGTYPE str) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `str`  
 L’élément de la chaîne.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une valeur de hachage calculée à l’aide du contenu de la chaîne.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
