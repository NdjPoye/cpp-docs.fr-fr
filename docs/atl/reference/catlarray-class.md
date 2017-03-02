---
title: Classe CAtlArray | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAtlArray
- ATL.CAtlArray
- CAtlArray
dev_langs:
- C++
helpviewer_keywords:
- CAtlArray class
ms.assetid: 0b503aa8-2357-40af-a326-6654bf1da098
caps.latest.revision: 21
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
ms.openlocfilehash: 5fe987e428fc0dcf3e40bfb16aa26bcb90339aff
ms.lasthandoff: 02/24/2017

---
# <a name="catlarray-class"></a>Classe CAtlArray
Cette classe implémente un objet tableau.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<typename E, class ETraits = CElementTraits<E>>
class CAtlArray
```  
  
#### <a name="parameters"></a>Paramètres  
 *E*  
 Type de données à stocker dans le tableau.  
  
 *ETraits*  
 Le code utilisé pour copier ou déplacer des éléments.  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[Ajouter](#add)|Appelez cette méthode pour ajouter un élément à l’objet tableau.|  
|[Ajouter](#append)|Appelez cette méthode pour ajouter le contenu d’un tableau à la fin d’une autre.|  
|[AssertValid](#assertvalid)|Appelez cette méthode pour vérifier que l’objet tableau est valide.|  
|[CAtlArray](#catlarray)|Constructeur.|  
|[~ CAtlArray](#dtor)|Destructeur.|  
|[Copie](#copy)|Appelez cette méthode pour copier les éléments d’un tableau à un autre.|  
|[FreeExtra](#freeextra)|Appelez cette méthode pour supprimer tous les éléments vides du tableau.|  
|[GetAt](#getat)|Appelez cette méthode pour récupérer un élément unique de l’objet de tableau.|  
|[GetCount](#getcount)|Appelez cette méthode pour retourner le nombre d’éléments stockés dans le tableau.|  
|[GetData](#getdata)|Appelez cette méthode pour retourner un pointeur vers le premier élément du tableau.|  
|[InsertArrayAt](#insertarrayat)|Appelez cette méthode pour insérer un tableau dans un autre.|  
|[InsertAt](#insertat)|Appelez cette méthode pour insérer un nouvel élément (ou plusieurs copies d’un élément) dans l’objet de tableau.|  
|[IsEmpty](#isempty)|Appelez cette méthode pour tester si le tableau est vide.|  
|[RemoveAll](#removeall)|Appelez cette méthode pour supprimer tous les éléments de l’objet array.|  
|[RemoveAt](#removeat)|Appelez cette méthode pour supprimer un ou plusieurs éléments du tableau.|  
|[SetAt](#setat)|Appelez cette méthode pour définir la valeur d’un élément dans l’objet tableau.|  
|[SetAtGrow](#setatgrow)|Appelez cette méthode pour définir la valeur d’un élément dans l’objet de tableau, en développant le tableau en fonction des besoins.|  
|[SetCount](#setcount)|Appelez cette méthode pour définir la taille de l’objet array.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator&#91;&#93;](#operator_at)|Appelez cet opérateur pour renvoyer une référence à un élément dans le tableau.|  

  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[INARGTYPE](#inargtype)|Le type de données à utiliser pour l’ajout d’éléments dans le tableau.|  
|[OUTARGTYPE](#outargtype)|Le type de données à utiliser pour récupérer des éléments du tableau.|  
  
## <a name="remarks"></a>Notes  
 **CAtlArray** fournit des méthodes pour créer et gérer un tableau d’éléments d’un type défini par l’utilisateur. Bien que semblable aux tableaux C standard, le **CAtlArray** objet peut dynamiquement réduire et s’agrandir autant que nécessaire. L’index de tableau commence toujours à la position 0 et la limite supérieure peut être fixe ou autorisée à étendre à mesure que de nouveaux éléments sont ajoutés.  
  
 Pour les tableaux avec un petit nombre d’éléments, la classe ATL [CSimpleArray](../../atl/reference/csimplearray-class.md) peut être utilisé.  
  
 **CAtlArray** est étroitement liée à MFC **CArray** classe et fonctionnera dans un projet MFC, mais sans prise en charge de la sérialisation.  
  
 Pour plus d’informations, consultez [Classes de Collection ATL](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcoll.h  
  
##  <a name="a-nameadda--catlarrayadd"></a><a name="add"></a>CAtlArray::Add  
 Appelez cette méthode pour ajouter un élément à l’objet tableau.  
  
```
size_t Add(INARGTYPE element);
size_t Add();
```  
  
### <a name="parameters"></a>Paramètres  
 `element`  
 L’élément à ajouter au tableau.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’index de l’élément ajouté.  
  
### <a name="remarks"></a>Remarques  
 Le nouvel élément est ajouté à la fin du tableau. Si aucun élément n’est fourni, un élément vide est ajouté ; Autrement dit, le tableau est augmenté la taille comme si un élément réel a été ajouté. Si l’opération échoue, [AtlThrow](http://msdn.microsoft.com/library/2bd111da-8170-488d-914a-c9bf6b6765f7) est appelée avec l’argument E_OUTOFMEMORY.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Utilities n °&1;](../../atl/codesnippet/cpp/catlarray-class_1.cpp)]  
  
##  <a name="a-nameappenda--catlarrayappend"></a><a name="append"></a>CAtlArray::Append  
 Appelez cette méthode pour ajouter le contenu d’un tableau à la fin d’une autre.  
  
```
size_t Append(const CAtlArray<E, ETraits>& aSrc);
```  
  
### <a name="parameters"></a>Paramètres  
 `aSrc`  
 Tableau à ajouter.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’index du premier élément ajouté.  
  
### <a name="remarks"></a>Remarques  
 Les éléments du tableau fourni sont ajoutés à la fin du tableau existant. Si nécessaire, mémoire sera allouée pour intégrer les nouveaux éléments.  
  
 Les tableaux doivent être du même type, et il n’est pas possible d’ajouter un tableau à lui-même.  
  
 Dans les versions debug, un ATLASSERT ; sera déclenchée si les `CAtlArray` argument n’est pas un tableau valide ou si `aSrc` fait référence au même objet. Arguments non valides dans les versions release, peuvent entraîner un comportement imprévisible.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Utilities n °&2;](../../atl/codesnippet/cpp/catlarray-class_2.cpp)]  
  
##  <a name="a-nameassertvalida--catlarrayassertvalid"></a><a name="assertvalid"></a>CAtlArray::AssertValid  
 Appelez cette méthode pour vérifier que l’objet tableau est valide.  
  
```
void AssertValid() const;
```  
  
### <a name="remarks"></a>Remarques  
 Si l’objet array n’est pas valide, `ATLASSERT` génère une assertion. Cette méthode est disponible uniquement si _DEBUG n’est défini.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Utilities n °&3;](../../atl/codesnippet/cpp/catlarray-class_3.cpp)]  
  
##  <a name="a-namecatlarraya--catlarraycatlarray"></a><a name="catlarray"></a>CAtlArray::CAtlArray  
 Constructeur.  
  
```
CAtlArray() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Initialise l’objet array.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Utilities n °&4;](../../atl/codesnippet/cpp/catlarray-class_4.cpp)]  
  
##  <a name="a-namedtora--catlarraycatlarray"></a><a name="dtor"></a>CAtlArray :: ~ CAtlArray  
 Destructeur.  
  
```
~CAtlArray() throw();
```  
  
### <a name="remarks"></a>Notes  
 Libère toutes les ressources utilisées par l’objet de tableau.  
  
##  <a name="a-namecopya--catlarraycopy"></a><a name="copy"></a>CAtlArray::Copy  
 Appelez cette méthode pour copier les éléments d’un tableau à un autre.  
  
```
void Copy(const CAtlArray<E, ETraits>& aSrc);
```  
  
### <a name="parameters"></a>Paramètres  
 `aSrc`  
 La source des éléments à copier dans un tableau.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode pour remplacer les éléments d’un tableau avec les éléments d’un autre tableau. Si nécessaire, mémoire sera allouée pour intégrer les nouveaux éléments. Il n’est pas possible de copier des éléments d’un tableau à lui-même.  
  
 Si le contenu existant du tableau doivent être conservées, utilisez [CAtlArray::Append](#append) à la place.  
  
 Dans les versions debug, un ATLASSERT ; sera déclenchée si existant `CAtlArray` objet n’est pas valide, ou si `aSrc` fait référence au même objet. Arguments non valides dans les versions release, peuvent entraîner un comportement imprévisible.  
  
> [!NOTE]
> `CAtlArray::Copy`ne prend pas en charge les tableaux constitué des éléments créés avec la [CAutoPtr](../../atl/reference/cautoptr-class.md) (classe).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Utilities n °&5;](../../atl/codesnippet/cpp/catlarray-class_5.cpp)]  
  
##  <a name="a-namefreeextraa--catlarrayfreeextra"></a><a name="freeextra"></a>CAtlArray::FreeExtra  
 Appelez cette méthode pour supprimer tous les éléments vides du tableau.  
  
```
void FreeExtra() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Les éléments vides sont supprimés, mais la taille et la limite supérieure du tableau restent inchangées.  
  
 Dans les versions debug, un ATLASSERT ; sera déclenchée si l’objet CAtlArray n’est pas valide ou si le tableau dépasse sa taille maximale.  
  
##  <a name="a-namegetata--catlarraygetat"></a><a name="getat"></a>CAtlArray::GetAt  
 Appel de que cette méthode récupère un élément unique à partir de l’objet array.  
  
```
const E& GetAt(size_t iElement) const throw();
E& GetAt(size_t iElement) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `iElement`  
 La valeur d’index de l’élément de tableau à retourner.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une référence à l’élément de tableau obligatoire.  
  
### <a name="remarks"></a>Remarques  
 Dans les versions debug, un ATLASSERT ; sera déclenchée si `iElement` dépasse le nombre d’éléments dans le tableau. Un argument non valide dans les versions release, peut entraîner un comportement imprévisible.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Utilities n °&6;](../../atl/codesnippet/cpp/catlarray-class_6.cpp)]  
  
##  <a name="a-namegetcounta--catlarraygetcount"></a><a name="getcount"></a>CAtlArray::GetCount  
 Appelez cette méthode pour retourner le nombre d’éléments stockés dans le tableau.  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre d’éléments stockés dans le tableau.  
  
### <a name="remarks"></a>Remarques  
 Comme le premier élément du tableau est à la position 0, la valeur retournée par `GetCount` est toujours 1 supérieur le plus grand index.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CAtlArray::GetAt](#getat).  
  
##  <a name="a-namegetdataa--catlarraygetdata"></a><a name="getdata"></a>CAtlArray::GetData  
 Appelez cette méthode pour retourner un pointeur vers le premier élément du tableau.  
  
```
E* GetData() throw();
const E* GetData() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur vers l’emplacement de mémoire stockant le premier élément du tableau. Si aucun élément n’est disponible, la valeur NULL est retournée.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Utilities&#7;](../../atl/codesnippet/cpp/catlarray-class_7.cpp)]  
  
##  <a name="a-nameinargtypea--catlarrayinargtype"></a><a name="inargtype"></a>CAtlArray::INARGTYPE  
 Le type de données à utiliser pour l’ajout d’éléments dans le tableau.  
  
```
typedef ETraits::INARGTYPE INARGTYPE;
```  
  
##  <a name="a-nameinsertarrayata--catlarrayinsertarrayat"></a><a name="insertarrayat"></a>CAtlArray::InsertArrayAt  
 Appelez cette méthode pour insérer un tableau dans un autre.  
  
```
void InsertArrayAt(size_t iStart, const CAtlArray<E, ETraits>* paNew);
```  
  
### <a name="parameters"></a>Paramètres  
 `iStart`  
 Index auquel le tableau doit être inséré.  
  
 `paNew`  
 Le tableau doit être inséré.  
  
### <a name="remarks"></a>Remarques  
 Éléments du tableau `paNew` sont copiés dans l’objet de tableau, en commençant à l’élément `iStart`. Les éléments du tableau sont déplacés pour éviter l’écrasement.  
  
 Dans les versions debug, un ATLASSERT ; sera déclenchée si les `CAtlArray` objet n’est pas valide, ou si le `paNew` pointeur est NULL ou non valide.  
  
> [!NOTE]
> `CAtlArray::InsertArrayAt`ne prend pas en charge les tableaux constitué des éléments créés avec la [CAutoPtr](../../atl/reference/cautoptr-class.md) (classe).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Utilities n °&8;](../../atl/codesnippet/cpp/catlarray-class_8.cpp)]  
  
##  <a name="a-nameinsertata--catlarrayinsertat"></a><a name="insertat"></a>CAtlArray::InsertAt  
 Appelez cette méthode pour insérer un nouvel élément (ou plusieurs copies d’un élément) dans l’objet de tableau.  
  
```
void InsertAt(size_t iElement, INARGTYPE element, size_t nCount = 1);
```  
  
### <a name="parameters"></a>Paramètres  
 `iElement`  
 Index où l’élément ou les éléments doivent être insérés.  
  
 `element`  
 La valeur de l’élément ou les éléments à insérer.  
  
 `nCount`  
 Le nombre d’éléments à ajouter.  
  
### <a name="remarks"></a>Notes  
 Insère un ou plusieurs éléments dans le tableau, en commençant à l’index `iElement`. Les éléments existants sont déplacés pour éviter l’écrasement.  
  
 Dans les versions debug, un ATLASSERT ; sera déclenchée si le `CAtlArray` objet n’est pas valide, le nombre d’éléments à ajouter est égal à zéro ou le nombre d’éléments est trop volumineux pour le tableau destiné à contenir. Dans les versions commerciales, le passage de paramètres non valides peut provoquer des résultats imprévisibles.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Utilities&#9;](../../atl/codesnippet/cpp/catlarray-class_9.cpp)]  
  
##  <a name="a-nameisemptya--catlarrayisempty"></a><a name="isempty"></a>CAtlArray::IsEmpty  
 Appelez cette méthode pour tester si le tableau est vide.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne true si le tableau est vide, sinon false.  
  
### <a name="remarks"></a>Remarques  
 Le tableau est dite vide s’il ne contienne aucun élément. Par conséquent, même si le tableau contient les éléments vides, il n’est pas vide.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Utilities&#10;](../../atl/codesnippet/cpp/catlarray-class_10.cpp)]  
  
##  <a name="a-nameoperatorata--catlarrayoperator-"></a><a name="operator_at"></a>[] CAtlArray::operator  
 Appelez cet opérateur pour renvoyer une référence à un élément dans le tableau.  
  
```
E& operator[](size_t ielement) throw();
const E& operator[](size_t ielement) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `iElement`  
 La valeur d’index de l’élément de tableau à retourner.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une référence à l’élément de tableau obligatoire.  
  
### <a name="remarks"></a>Notes  
 Exécute une fonction semblable à [CAtlArray::GetAt](#getat). Contrairement à la classe MFC [CArray](../../mfc/reference/carray-class.md), cet opérateur ne peut pas être utilisé pour remplacer [CAtlArray::SetAt](#setat).  
  
 Dans les versions debug, un ATLASSERT ; sera déclenchée si `iElement` dépasse le nombre total d’éléments dans le tableau. Dans les versions commerciales, un paramètre non valide peut provoquer des résultats imprévisibles.  
  
##  <a name="a-nameoutargtypea--catlarrayoutargtype"></a><a name="outargtype"></a>CAtlArray::OUTARGTYPE  
 Le type de données à utiliser pour récupérer des éléments du tableau.  
  
```
typedef ETraits::OUTARGTYPE OUTARGTYPE;
```  
  
##  <a name="a-nameremovealla--catlarrayremoveall"></a><a name="removeall"></a>CAtlArray::RemoveAll  
 Appelez cette méthode pour supprimer tous les éléments de l’objet array.  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>Notes  
 Supprime tous les éléments de l’objet array.  
  
 Cette méthode appelle [CAtlArray::SetCount](#setcount) pour redimensionner le tableau et par la suite libère la mémoire allouée.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CAtlArray::IsEmpty](#isempty).  
  
##  <a name="a-nameremoveata--catlarrayremoveat"></a><a name="removeat"></a>CAtlArray::RemoveAt  
 Appelez cette méthode pour supprimer un ou plusieurs éléments du tableau.  
  
```
void RemoveAt(size_t iElement, size_t nCount = 1);
```  
  
### <a name="parameters"></a>Paramètres  
 `iElement`  
 L’index du premier élément à supprimer.  
  
 `nCount`  
 Nombre d'éléments à supprimer.  
  
### <a name="remarks"></a>Remarques  
 Supprime un ou plusieurs éléments du tableau. Les éléments restants sont décalés vers le bas. La limite supérieure est décrémentée, mais la mémoire n’est pas libérée jusqu'à ce qu’un appel à [CAtlArray::FreeExtra](#freeextra) est effectuée.  
  
 Dans les versions debug, un ATLASSERT ; sera déclenchée si les `CAtlArray` objet n’est pas valide, ou si le total combiné de `iElement` et `nCount` dépasse le nombre total d’éléments dans le tableau. Dans les versions commerciales, paramètres non valides peuvent provoquer des résultats imprévisibles.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Utilities&#11;](../../atl/codesnippet/cpp/catlarray-class_11.cpp)]  
  
##  <a name="a-namesetata--catlarraysetat"></a><a name="setat"></a>CAtlArray::SetAt  
 Appelez cette méthode pour définir la valeur d’un élément dans l’objet tableau.  
  
```
void SetAt(size_t iElement, INARGTYPE element);
```  
  
### <a name="parameters"></a>Paramètres  
 `iElement`  
 L’index qui pointe vers l’élément de tableau à définir.  
  
 `element`  
 La nouvelle valeur de l’élément spécifié.  
  
### <a name="remarks"></a>Remarques  
 Dans les versions debug, un ATLASSERT ; sera déclenchée si `iElement` dépasse le nombre d’éléments dans le tableau. Un paramètre non valide dans les versions commerciales, peut entraîner des résultats imprévisibles.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CAtlArray::GetAt](#getat).  
  
##  <a name="a-namesetcounta--catlarraysetcount"></a><a name="setcount"></a>CAtlArray::SetCount  
 Appelez cette méthode pour définir la taille de l’objet array.  
  
```
bool SetCount(size_t nNewSize, int nGrowBy = - 1);
```  
  
### <a name="parameters"></a>Paramètres  
 `nNewSize`  
 La taille requise du tableau.  
  
 `nGrowBy`  
 Une valeur utilisée pour déterminer la taille de la mémoire tampon. Une valeur de -1 entraîne une valeur calculée en interne à utiliser.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si le tableau est correctement redimensionné, false dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 Le tableau peut être augmenté ou réduit en taille. Si augmenté, éléments vides supplémentaires sont ajoutés au tableau. Si réduit, les éléments avec les plus grand index seront supprimés et la mémoire libérée.  
  
 Utilisez cette méthode pour définir la taille du tableau avant de l’utiliser. Si `SetCount` n’est pas utilisé, le processus d’ajout d’éléments, et l’allocation de mémoire suivantes effectuées, réduira les performances et fragmenter la mémoire.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CAtlArray::GetData](#getdata).  
  
##  <a name="a-namesetatgrowa--catlarraysetatgrow"></a><a name="setatgrow"></a>CAtlArray::SetAtGrow  
 Appelez cette méthode pour définir la valeur d’un élément dans l’objet de tableau, en développant le tableau en fonction des besoins.  
  
```
void SetAtGrow(size_t iElement, INARGTYPE element);
```  
  
### <a name="parameters"></a>Paramètres  
 `iElement`  
 L’index qui pointe vers l’élément de tableau à définir.  
  
 `element`  
 La nouvelle valeur de l’élément spécifié.  
  
### <a name="remarks"></a>Remarques  
 Remplace la valeur de l’élément vers lequel pointé l’index. Si `iElement` est supérieure à la taille actuelle du tableau, le tableau est automatiquement augmenté à l’aide d’un appel à [CAtlArray::SetCount](#setcount). Dans les versions debug, un ATLASSERT ; sera déclenchée si le `CAtlArray` objet n’est pas valide. Dans les versions commerciales, paramètres non valides peuvent provoquer des résultats imprévisibles.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Utilities&#12;](../../atl/codesnippet/cpp/catlarray-class_12.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [MMXSwarm, exemple](../../visual-cpp-samples.md)   
 [DynamicConsumer, exemple](../../visual-cpp-samples.md)   
 [UpdatePV, exemple](../../visual-cpp-samples.md)   
 [Exemple de texte défilant](../../visual-cpp-samples.md)   
 [CArray (classe)](../../mfc/reference/carray-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

