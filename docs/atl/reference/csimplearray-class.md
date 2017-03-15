---
title: Classe de CSimpleArray | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CSimpleArray
- ATL::CSimpleArray
- CSimpleArray
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArray class
ms.assetid: ee0c9f39-b61c-4c18-bc43-4eada21dca3a
caps.latest.revision: 20
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: e261f95a375a2edda1d543a36b605d23fc718b99
ms.lasthandoff: 02/24/2017

---
# <a name="csimplearray-class"></a>CSimpleArray (classe)
Cette classe fournit des méthodes pour la gestion d’un simple tableau.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T, class TEqual = CSimpleArrayEqualHelper<T>>  
class CSimpleArray
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Le type de données à stocker dans le tableau.  
  
 `TEqual`  
 Un objet de caractéristique en définissant le test d’égalité pour les éléments de type `T`.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CSimpleArray::CSimpleArray](#csimplearray)|Le constructeur de tableau simple.|  
|[CSimpleArray :: ~ CSimpleArray](#dtor)|Le destructeur de tableau simple.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CSimpleArray::Add](#add)|Ajoute un nouvel élément dans le tableau.|  
|[CSimpleArray::Find](#find)|Recherche un élément dans le tableau.|  
|[CSimpleArray::GetData](#getdata)|Retourne un pointeur vers les données stockées dans le tableau.|  
|[CSimpleArray::GetSize](#getsize)|Retourne le nombre d’éléments stockés dans le tableau.|  
|[CSimpleArray::Remove](#remove)|Supprime un élément donné du tableau.|  
|[CSimpleArray::RemoveAll](#removeall)|Supprime tous les éléments du tableau.|  
|[CSimpleArray::RemoveAt](#removeat)|Supprime l’élément spécifié à partir du tableau.|  
|[CSimpleArray::SetAtIndex](#setatindex)|Définit l’élément spécifié dans le tableau.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CSimpleArray::operator\[\]](#operator_at)|Récupère un élément du tableau.|  
|[CSimpleArray::operator =](#operator_eq)|Opérateur d'assignation.|  

  
## <a name="remarks"></a>Remarques  
 `CSimpleArray`Fournit des méthodes pour créer et gérer un simple tableau, d’un type donné `T`.  
  
 Le paramètre `TEqual` fournit un moyen de définir une fonction de l’égalité de deux éléments de type `T`. En créant une classe similaire à [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md), il est possible de modifier le comportement du test d’égalité pour n’importe quel tableau donné. Par exemple, lorsque vous travaillez avec un tableau de pointeurs, il peut être utile définir l’égalité comme en fonction des valeurs de référence les pointeurs. L’implémentation par défaut utilise **operator=()**.  
  
 Les deux `CSimpleArray` et [CSimpleMap](../../atl/reference/csimplemap-class.md) sont conçus pour un petit nombre d’éléments. [CAtlArray](../../atl/reference/catlarray-class.md) et [CAtlMap](../../atl/reference/catlmap-class.md) doit être utilisé lorsque le tableau contient un grand nombre d’éléments.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlsimpcoll.h  
  
## <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Utilities&#86;](../../atl/codesnippet/cpp/csimplearray-class_1.cpp)]  
  
##  <a name="a-nameadda--csimplearrayadd"></a><a name="add"></a>CSimpleArray::Add  
 Ajoute un nouvel élément dans le tableau.  
  
```
BOOL Add(const T& t);
```  
  
### <a name="parameters"></a>Paramètres  
 *t*  
 L’élément à ajouter au tableau.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE si l’élément est correctement ajouté au tableau, FALSE dans le cas contraire.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Utilities&#87;](../../atl/codesnippet/cpp/csimplearray-class_2.cpp)]  
  
##  <a name="a-namecsimplearraya--csimplearraycsimplearray"></a><a name="csimplearray"></a>CSimpleArray::CSimpleArray  
 Le constructeur de l’objet array.  
  
```
CSimpleArray(const CSimpleArray<T, TEqual>& src);  
CSimpleArray();
```     
  
### <a name="parameters"></a>Paramètres  
 *src*  
 Objet `CSimpleArray` existant.  
  
### <a name="remarks"></a>Remarques  
 Initialise les membres de données, création d’un nouveau vide `CSimpleArray` objet, ou une copie d’un `CSimpleArray` objet.  
  
##  <a name="a-namedtora--csimplearraycsimplearray"></a><a name="dtor"></a>CSimpleArray :: ~ CSimpleArray  
 Destructeur.  
  
```
~CSimpleArray();
```  
  
### <a name="remarks"></a>Notes  
 Libère toutes les ressources attribuées.  
  
##  <a name="a-namefinda--csimplearrayfind"></a><a name="find"></a>CSimpleArray::Find  
 Recherche un élément dans le tableau.  
  
```
int Find(const T& t) const;
```  
  
### <a name="parameters"></a>Paramètres  
 *t*  
 L’élément à rechercher.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’index de l’élément est trouvé, ou -1 si l’élément est introuvable.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Utilities&#88;](../../atl/codesnippet/cpp/csimplearray-class_3.cpp)]  
  
##  <a name="a-namegetdataa--csimplearraygetdata"></a><a name="getdata"></a>CSimpleArray::GetData  
 Retourne un pointeur vers les données stockées dans le tableau.  
  
```
T* GetData() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur vers les données dans le tableau.  
  
##  <a name="a-namegetsizea--csimplearraygetsize"></a><a name="getsize"></a>CSimpleArray::GetSize  
 Retourne le nombre d’éléments stockés dans le tableau.  
  
```
int GetSize() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre d’éléments stockés dans le tableau.  
  
##  <a name="a-nameoperatorata--csimplearrayoperator-"></a><a name="operator_at"></a>CSimpleArray::operator\[\]  
 Récupère un élément du tableau.  
  
```
T& operator[](int nindex);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 L’index de l’élément.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’élément de tableau référencé par `nIndex`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Utilities&#89;](../../atl/codesnippet/cpp/csimplearray-class_4.cpp)]  
  
##  <a name="a-nameoperatoreqa--csimplearrayoperator-"></a><a name="operator_eq"></a>CSimpleArray::operator =  
 Opérateur d'assignation.  
  
```
CSimpleArray<T, TEqual>
& operator=(
    const CSimpleArray<T, TEqual>& src);
```  
  
### <a name="parameters"></a>Paramètres  
 *src*  
 Tableau à copier.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur vers la mise à jour `CSimpleArray` objet.  
  
### <a name="remarks"></a>Remarques  
 Copie tous les éléments de la `CSimpleArray` objet référencé par *src* dans l’objet de tableau en cours, en remplaçant toutes les données existantes.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Utilities&#90;](../../atl/codesnippet/cpp/csimplearray-class_5.cpp)]  
  
##  <a name="a-nameremovea--csimplearrayremove"></a><a name="remove"></a>CSimpleArray::Remove  
 Supprime un élément donné du tableau.  
  
```
BOOL Remove(const T& t);
```  
  
### <a name="parameters"></a>Paramètres  
 *t*  
 L’élément à supprimer du tableau.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE si l’élément est trouvé et supprimé, FALSE dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 Lorsqu’un élément est supprimé, les éléments restants dans le tableau sont renumérotés pour remplir l’espace vide.  
  
##  <a name="a-nameremovealla--csimplearrayremoveall"></a><a name="removeall"></a>CSimpleArray::RemoveAll  
 Supprime tous les éléments du tableau.  
  
```
void RemoveAll();
```  
  
### <a name="remarks"></a>Notes  
 Supprime tous les éléments actuellement stockés dans le tableau.  
  
##  <a name="a-nameremoveata--csimplearrayremoveat"></a><a name="removeat"></a>CSimpleArray::RemoveAt  
 Supprime l’élément spécifié à partir du tableau.  
  
```
BOOL RemoveAtint nIndex);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index qui pointe vers l’élément à supprimer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE si l’élément a été supprimé, FALSE si l’index n’est pas valide.  
  
### <a name="remarks"></a>Remarques  
 Lorsqu’un élément est supprimé, les éléments restants dans le tableau sont renumérotés pour remplir l’espace vide.  
  
##  <a name="a-namesetatindexa--csimplearraysetatindex"></a><a name="setatindex"></a>CSimpleArray::SetAtIndex  
 Définir l’élément spécifié dans le tableau.  
  
```
BOOL SetAtIndex(
    int nIndex,
    const T& t);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 L’index de l’élément à modifier.  
  
 *t*  
 Valeur à assigner à l’élément spécifié.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne TRUE si réussi et FALSE si l’index n’est pas valide.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

