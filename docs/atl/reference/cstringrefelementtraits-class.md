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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 3709a5d4aac02651e5b6fafd441499fea1f8eabc
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cstringrefelementtraits-class"></a>CStringRefElementTraits (classe)
Cette classe fournit des fonctions statiques relatives aux chaînes stockées dans les objets de classe de collection. Les objets chaîne sont traitées en tant que références.  
  
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
|[CStringRefElementTraits::CompareElements](#compareelements)|Appelez cette fonction pour comparer deux éléments de chaîne d’égalité statique.|  
|[CStringRefElementTraits::CompareElementsOrdered](#compareelementsordered)|Appelez cette fonction pour comparer deux éléments de chaîne statique.|  
|[CStringRefElementTraits::Hash](#hash)|Appelez cette fonction statique pour calculer une valeur de hachage pour l’élément de la chaîne donnée.|  
  
## <a name="remarks"></a>Notes  
 Cette classe fournit des fonctions statiques pour la comparaison de chaînes et de créer une valeur de hachage. Ces fonctions sont utiles lorsque vous utilisez une classe de collection pour stocker des données de type chaîne. Contrairement aux [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md) et [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md), `CStringRefElementTraits` provoque la `CString` arguments à transmettre en tant que **const CString se** références.  
  
 Pour plus d’informations, consultez [Classes de Collection ATL](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringRefElementTraits`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcoll.h  
  
##  <a name="compareelements"></a>CStringRefElementTraits::CompareElements  
 Appelez cette fonction pour comparer deux éléments de chaîne d’égalité statique.  
  
```
static bool CompareElements(INARGTYPE element1, INARGTYPE element2) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `element1`  
 Le premier élément de chaîne.  
  
 `element2`  
 Le deuxième élément de chaîne.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si les éléments sont égaux.  
  
##  <a name="compareelementsordered"></a>CStringRefElementTraits::CompareElementsOrdered  
 Appelez cette fonction pour comparer deux éléments de chaîne statique.  
  
```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `str1`  
 Le premier élément de chaîne.  
  
 `str2`  
 Le deuxième élément de chaîne.  
  
### <a name="return-value"></a>Valeur de retour  
 Zéro si les chaînes sont identiques, < 0="" if=""> `str1` est inférieure à `str2`, ou 0 > si `str1` est supérieur à `str2`. Le [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) méthode est utilisée pour effectuer des comparaisons.  
  
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
 [CElementTraitsBase (classe)](../../atl/reference/celementtraitsbase-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

