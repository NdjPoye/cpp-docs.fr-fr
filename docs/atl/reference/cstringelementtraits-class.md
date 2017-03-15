---
title: Classe de CStringElementTraits | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CStringElementTraits<T>
- ATL::CStringElementTraits<T>
- CStringElementTraits
- ATL.CStringElementTraits
- ATL::CStringElementTraits
dev_langs:
- C++
helpviewer_keywords:
- CStringElementTraits class
ms.assetid: 74d7134b-099d-4455-bf91-3e68ccbf95bc
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
ms.openlocfilehash: f46ff072bcd0f772dac1bba52b114d82ee433112
ms.lasthandoff: 02/24/2017

---
# <a name="cstringelementtraits-class"></a>CStringElementTraits (classe)
Cette classe fournit des fonctions statiques utilisées par le stockage des classes de collection `CString` objets.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <typename T>  
class CStringElementTraits
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Le type de données à stocker dans la collection.  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CStringElementTraits::INARGTYPE](#inargtype)|Le type de données à utiliser pour l’ajout d’éléments à l’objet de classe de collection.|  
|[CStringElementTraits::OUTARGTYPE](#outargtype)|Le type de données à utiliser pour récupérer des éléments de l’objet de classe de collection.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CStringElementTraits::CompareElements](#compareelements)|(Statique) Appelez cette fonction pour comparer deux éléments de chaîne pour l’égalité.|  
|[CStringElementTraits::CompareElementsOrdered](#compareelementsordered)|(Statique) Appelez cette fonction pour comparer deux éléments de chaîne.|  
|[CStringElementTraits::CopyElements](#copyelements)|(Statique) Appelez cette fonction pour copier `CString` éléments stockés dans un objet de classe de collection.|  
|[CStringElementTraits::Hash](#hash)|(Statique) Appelez cette fonction pour calculer une valeur de hachage pour l’élément de la chaîne donnée.|  
|[CStringElementTraits::RelocateElements](#relocateelements)|(Statique) Appelez cette fonction pour déplacer `CString` éléments stockés dans un objet de classe de collection.|  
  
## <a name="remarks"></a>Remarques  
 Cette classe fournit des fonctions statiques pour la copie, le déplacement et la comparaison de chaînes et de créer une valeur de hachage. Ces fonctions sont utiles lorsque vous utilisez une classe de collection pour stocker des données de type chaîne. Utilisez [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md) lorsque des comparaisons sans respecter la casse sont requises. Utilisez [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) lorsque les objets de chaîne sont traitées en tant que références.  
  
 Pour plus d’informations, consultez [Classes de Collection ATL](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** cstringt.h  
  
##  <a name="a-namecompareelementsa--cstringelementtraitscompareelements"></a><a name="compareelements"></a>CStringElementTraits::CompareElements  
 Appelez cette fonction pour comparer deux éléments de chaîne d’égalité statique.  
  
```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2);
```  
  
### <a name="parameters"></a>Paramètres  
 `str1`  
 Le premier élément de chaîne.  
  
 `str2`  
 Le deuxième élément de chaîne.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si les éléments sont égaux.  
  
##  <a name="a-namecompareelementsordereda--cstringelementtraitscompareelementsordered"></a><a name="compareelementsordered"></a>CStringElementTraits::CompareElementsOrdered  
 Appelez cette fonction pour comparer deux éléments de chaîne statique.  
  
```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2);
```  
  
### <a name="parameters"></a>Paramètres  
 `str1`  
 Le premier élément de chaîne.  
  
 `str2`  
 Le deuxième élément de chaîne.  
  
### <a name="return-value"></a>Valeur de retour  
 Zéro si les chaînes sont identiques, < 0="" if=""> `str1` est inférieure à `str2`, ou 0 > si `str1` est supérieur à `str2`. Le [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) méthode est utilisée pour effectuer des comparaisons.  

  
##  <a name="a-namecopyelementsa--cstringelementtraitscopyelements"></a><a name="copyelements"></a>CStringElementTraits::CopyElements  
 Appelez cette fonction statique pour copier `CString` éléments stockés dans un objet de classe de collection.  
  
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
  
### <a name="remarks"></a>Notes  
 Les éléments source et de destination ne doivent pas se chevaucher.  
  
##  <a name="a-namehasha--cstringelementtraitshash"></a><a name="hash"></a>CStringElementTraits::Hash  
 Appelez cette fonction statique pour calculer une valeur de hachage pour l’élément de la chaîne donnée.  
  
```
static ULONG Hash(INARGTYPE str);
```  
  
### <a name="parameters"></a>Paramètres  
 `str`  
 L’élément de la chaîne.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une valeur de hachage calculée à l’aide du contenu de la chaîne.  
  
##  <a name="a-nameinargtypea--cstringelementtraitsinargtype"></a><a name="inargtype"></a>CStringElementTraits::INARGTYPE  
 Le type de données à utiliser pour l’ajout d’éléments à l’objet de classe de collection.  
  
```
typedef T::PCXSTR INARGTYPE;
```  
  
##  <a name="a-nameoutargtypea--cstringelementtraitsoutargtype"></a><a name="outargtype"></a>CStringElementTraits::OUTARGTYPE  
 Le type de données à utiliser pour récupérer des éléments de l’objet de classe de collection.  
  
```
typedef T& OUTARGTYPE;
```  
  
##  <a name="a-namerelocateelementsa--cstringelementtraitsrelocateelements"></a><a name="relocateelements"></a>CStringElementTraits::RelocateElements  
 Appelez cette fonction pour déplacer statique `CString` éléments stockés dans un objet de classe de collection.  
  
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
 Appelle cette fonction statique [memmove](../../c-runtime-library/reference/memmove-wmemmove.md), ce qui est suffisant pour la plupart des types de données. Si les objets déplacés contiennent des pointeurs vers des membres de leurs propre, cette fonction statique devez être remplacée.  
  
## <a name="see-also"></a>Voir aussi  
 [CElementTraitsBase (classe)](../../atl/reference/celementtraitsbase-class.md)   
 [CStringElementTraitsI (classe)](../../atl/reference/cstringelementtraitsi-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

