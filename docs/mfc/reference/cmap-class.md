---
title: Classe de CMap | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMap
dev_langs:
- C++
helpviewer_keywords:
- dictionary mapping class
- collection classes, dictionary mapping
- CMap class
ms.assetid: 640a45ab-0993-4def-97ec-42cc78eb10b9
caps.latest.revision: 24
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
ms.openlocfilehash: 680d44fe6154861d2c638697cfc9d3fbeab36cc4
ms.lasthandoff: 02/24/2017

---
# <a name="cmap-class"></a>CMap (classe)
Classe de collection de dictionnaires qui mappe des clés uniques à des valeurs.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<class KEY, class ARG_KEY, class VALUE, class ARG_VALUE>class CMap : public CObject  
```  
  
#### <a name="parameters"></a>Paramètres  
 `KEY`  
 Classe de l’objet utilisé comme clé pour la carte.  
  
 `ARG` *_* `KEY`  
 Type de données utilisé pour `KEY` arguments ; généralement une référence à `KEY`.  
  
 `VALUE`  
 Classe de l’objet stocké dans la table.  
  
 `ARG` *_* `VALUE`  
 Type de données utilisé pour `VALUE` arguments ; généralement une référence à `VALUE`.  
  
## <a name="members"></a>Membres  
  
### <a name="public-structures"></a>Structures publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMap::CPair](#cpair)|Une structure imbriquée contenant une valeur de clé et la valeur de l’objet associé.|  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMap::CMap](#cmap)|Construit une collection qui mappe les valeurs des clés.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMap::GetCount](#getcount)|Retourne le nombre d’éléments dans ce mappage.|  
|[CMap::GetHashTableSize](#gethashtablesize)|Retourne le nombre d’éléments dans la table de hachage.|  
|[CMap::GetNextAssoc](#getnextassoc)|Obtient l’élément suivant pour l’itération.|  
|[CMap::GetSize](#getsize)|Retourne le nombre d’éléments dans ce mappage.|  
|[CMap::GetStartPosition](#getstartposition)|Retourne la position du premier élément.|  
|[CMap::InitHashTable](#inithashtable)|Initialise la table de hachage et spécifie sa taille.|  
|[CMap::IsEmpty](#isempty)|Vérifie si la condition de mappage vide (aucun élément).|  
|[CMap::Lookup](#lookup)|Recherche la valeur mappée à une clé donnée.|  
|[CMap::PGetFirstAssoc](#pgetfirstassoc)|Retourne un pointeur vers le premier élément.|  
|[CMap::PGetNextAssoc](#pgetnextassoc)|Obtient un pointeur vers l’élément suivant pour l’itération.|  
|[CMap::PLookup](#plookup)|Retourne un pointeur vers une clé dont la valeur correspond à la valeur spécifiée.|  
|[CMap::RemoveAll](#removeall)|Supprime tous les éléments de cette carte.|  
|[CMap::RemoveKey](#removekey)|Supprime un élément spécifié par une clé.|  
|[CMap::SetAt](#setat)|Insère un élément dans la carte ; remplace un élément existant si une clé est trouvée.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[[] CMap::operator](#operator_at)|Insère un élément dans le mappage â €« substitution de l’opérateur pour `SetAt`.|  
  
## <a name="remarks"></a>Remarques  
 Une fois que vous avez inséré une paire clé-valeur (élément) dans le mappage, vous pouvez efficacement récupérer ou supprimer la paire à l’aide de la clé pour y accéder. Vous pouvez également itérer sur tous les éléments dans la carte.  
  
 Une variable de type **POSITION** est utilisé pour un autre accès aux entrées. Vous pouvez utiliser un **POSITION** pour « mémoriser » une entrée et une itération au sein de la carte. Vous pouvez penser que cette itération est séquentielle par valeur de clé ; Il n’est pas le cas. La séquence des éléments récupérés est indéterminée.  
  
 Certaines fonctions membres de cet appel de classe des fonctions d’assistance globales qui doivent être personnalisées pour la plupart des utilisations de la `CMap` classe. Consultez la page [Assistants de classe de Collection](../../mfc/reference/collection-class-helpers.md) dans la section Macros and Globals de le `MFC``Reference`.  
  
 `CMap`substitue [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) pour prendre en charge la sérialisation et le vidage de ses éléments. Si un mappage est stocké dans une archive à l’aide de `Serialize`, chaque élément de mappage est sérialisé à son tour. L’implémentation par défaut de le `SerializeElements` fonction d’assistance effectue une écriture au niveau du bit. Pour plus d’informations sur la sérialisation des éléments de collection pointeur dérivé `CObject` ou autres types définis par l’utilisateur, consultez la page [Comment : créer une Collection de Type sécurisé](../../mfc/how-to-make-a-type-safe-collection.md).  
  
 Si vous avez besoin de diagnostic vider des éléments individuels dans le mappage (les clés et valeurs), vous devez définir la profondeur du contexte de vidage à 1 ou supérieur.  
  
 Lorsqu’un `CMap` objet est supprimé, ou lorsque ses éléments sont supprimés, les clés et valeurs sont supprimés.  
  
 Dérivation de classe de carte est similaire à la dérivation de la liste. Consultez l’article [Collections](../../mfc/collections.md) pour une illustration de la dérivation d’une classe de liste de spécial.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMap`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxtempl.h  
  
##  <a name="a-namecmapa--cmapcmap"></a><a name="cmap"></a>CMap::CMap  
 Construit un mappage vide.  
  
```  
CMap(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>Paramètres  
 `nBlockSize`  
 Spécifie la granularité d’allocation de mémoire pour l’extension de la carte.  
  
### <a name="remarks"></a>Remarques  
 À mesure que la carte augmente, la mémoire est allouée en unités de `nBlockSize` entrées.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCCollections&#56;](../../mfc/codesnippet/cpp/cmap-class_1.cpp)]  
  
##  <a name="a-namecpaira--cmapcpair"></a><a name="cpair"></a>CMap::CPair  
 Contient une valeur de clé et la valeur de l’objet associé.  
  
### <a name="remarks"></a>Notes  
 Il s’agit d’une structure imbriquée dans la classe [CMap](../../mfc/reference/cmap-class.md).  
  
 La structure est composée de deux champs :  
  
- **Key Â Â** la valeur réelle du type de clé.  
  
- **valueÂ Â Â** la valeur de l’objet associé.  
  
 Il est utilisé pour stocker les valeurs de retour à partir de [CMap::PLookup](#plookup), [CMap::PGetFirstAssoc](#pgetfirstassoc), et [CMap::PGetNextAssoc](#pgetnextassoc).  
  
### <a name="example"></a>Exemple  
 Pour obtenir un exemple d’utilisation, consultez l’exemple de [CMap::PLookup](#plookup).  
  
##  <a name="a-namegetcounta--cmapgetcount"></a><a name="getcount"></a>CMap::GetCount  
 Récupère le nombre d’éléments de la carte.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Nombre d'éléments.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CMap::Lookup](#lookup).  
  
##  <a name="a-namegethashtablesizea--cmapgethashtablesize"></a><a name="gethashtablesize"></a>CMap::GetHashTableSize  
 Détermine le nombre d’éléments dans la table de hachage pour la carte.  
  
```  
UINT GetHashTableSize() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre d’éléments dans la table de hachage.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCCollections&#57;](../../mfc/codesnippet/cpp/cmap-class_2.cpp)]  
  
##  <a name="a-namegetnextassoca--cmapgetnextassoc"></a><a name="getnextassoc"></a>CMap::GetNextAssoc  
 Récupère l’élément de la carte à `rNextPosition`, puis met à jour `rNextPosition` pour faire référence à l’élément suivant dans la carte.  
  
```  
void GetNextAssoc(
    POSITION& rNextPosition,
    KEY& rKey,
    VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `rNextPosition`  
 Spécifie une référence à un **POSITION** valeur retournée par une précédente `GetNextAssoc` ou `GetStartPosition` appeler.  
  
 *CLÉ*  
 Paramètre de modèle qui spécifie le type de clé de la carte.  
  
 `rKey`  
 Spécifie la clé de l’élément récupéré retournée.  
  
 *VALEUR*  
 Paramètre de modèle spécifiant le type de valeur de la carte.  
  
 `rValue`  
 Spécifie la valeur retournée de l’élément récupéré.  
  
### <a name="remarks"></a>Notes  
 Cette fonction est particulièrement utile pour itérer tous les éléments dans la carte. Notez que la séquence de position n’est pas nécessairement identique à la séquence de la valeur de clé.  
  
 Si l’élément récupéré est le dernier dans le mappage, puis la nouvelle valeur de `rNextPosition` a **NULL**.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CMap::SetAt](#setat).  
  
##  <a name="a-namegetsizea--cmapgetsize"></a><a name="getsize"></a>CMap::GetSize  
 Retourne le nombre d’éléments de mappage.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre d’éléments dans la carte.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode pour récupérer le nombre d’éléments de la carte.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCCollections&#58;](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]  
  
##  <a name="a-namegetstartpositiona--cmapgetstartposition"></a><a name="getstartposition"></a>CMap::GetStartPosition  
 Démarre une itération de la carte en retournant un **POSITION** valeur qui peut être passé à un `GetNextAssoc` appeler.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A **POSITION** valeur qui indique la position de départ pour l’itération de la carte ; ou **NULL** si le mappage est vide.  
  
### <a name="remarks"></a>Remarques  
 La séquence d’itération n’est pas prévisible ; Par conséquent, le « premier élément de la carte » n’a aucune signification spéciale.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CMap::SetAt](#setat).  
  
##  <a name="a-nameinithashtablea--cmapinithashtable"></a><a name="inithashtable"></a>CMap::InitHashTable  
 Initialise la table de hachage.  
  
```  
void InitHashTable(UINT hashSize, BOOL  bAllocNow = TRUEÂ);  
```  
  
### <a name="parameters"></a>Paramètres  
 `hashSize`  
 Nombre d’entrées dans la table de hachage.  
  
 `bAllocNow`  
 Si **TRUE**, alloue de la table de hachage lors de l’initialisation ; sinon, le tableau est alloué lorsque nécessaire.  
  
### <a name="remarks"></a>Notes  
 Pour de meilleures performances, la taille de table de hachage doit être un nombre premier. Pour réduire les conflits, la taille doit être environ 20 pour cent supérieur le plus grand jeu de données prévu.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CMap::Lookup](#lookup).  
  
##  <a name="a-nameisemptya--cmapisempty"></a><a name="isempty"></a>CMap::IsEmpty  
 Détermine si le mappage est vide.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si ce mappage ne contient aucun élément ; sinon 0.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CMap::RemoveAll](#removeall).  
  
##  <a name="a-namelookupa--cmaplookup"></a><a name="lookup"></a>CMap::Lookup  
 Recherche la valeur mappée à une clé donnée.  
  
```  
BOOL Lookup(ARG_KEY key, VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `ARG_KEY`  
 Paramètre de modèle spécifiant le type de la `key` valeur.  
  
 `key`  
 Spécifie la clé qui identifie l’élément à rechercher.  
  
 *VALEUR*  
 Spécifie le type de la valeur à rechercher.  
  
 `rValue`  
 Reçoit la valeur recherchée.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’élément a été trouvé ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 `Lookup`utilise un algorithme de hachage pour trouver rapidement l’élément de carte avec une clé correspondant exactement à la clé donnée.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCCollections&#58;](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]  
  
##  <a name="a-nameoperatorata--cmapoperator--"></a><a name="operator_at"></a>[] CMap::operator  
 Un substitut pratique pour le `SetAt` fonction membre.  
  
```  
VALUE& operator[](arg_key key);
```  
  
### <a name="parameters"></a>Paramètres  
 *VALEUR*  
 Paramètre de modèle qui spécifie le type de la valeur de la carte.  
  
 `ARG_KEY`  
 Paramètre de modèle spécifiant le type de la valeur de clé.  
  
 `key`  
 La clé utilisée pour récupérer la valeur de la carte.  
  
### <a name="remarks"></a>Remarques  
 Par conséquent, il peut être utilisé uniquement sur le côté gauche d’une instruction d’assignation (une l-value). S’il n’existe aucun élément de carte avec la clé spécifiée, un nouvel élément est créé.  
  
 Aucune (valeur r) « droite » n’est équivalent à cet opérateur, car il est possible qu’une clé peut être introuvable dans la carte. Utilisez le `Lookup` fonction membre pour l’extraction de l’élément.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CMap::Lookup](#lookup).  
  
##  <a name="a-namepgetfirstassoca--cmappgetfirstassoc"></a><a name="pgetfirstassoc"></a>CMap::PGetFirstAssoc  
 Retourne la première entrée de l’objet de mappage.  
  
```  
const CPair* PGetFirstAssoc() const;Â CPair* PGetFirstAssoc();  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers la première entrée de la carte ; consultez la page [CMap::CPair](#cpair). Si la carte ne contient aucune entrée, la valeur est **NULL**.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette fonction pour retourner un pointeur du premier élément dans l’objet map.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCCollections&#59;](../../mfc/codesnippet/cpp/cmap-class_4.cpp)]  
  
##  <a name="a-namepgetnextassoca--cmappgetnextassoc"></a><a name="pgetnextassoc"></a>CMap::PGetNextAssoc  
 Récupère l’élément de carte indiqué par `pAssocRec`.  
  
```  
const CPair *PGetNextAssoc(const CPair* pAssocRet) const;  
  
CPair *PGetNextAssoc(const CPair* pAssocRet);
```  
  
### <a name="parameters"></a>Paramètres  
 *pAssocRet*  
 Pointe vers une entrée de mappage retournée par une [PGetNextAssoc](#pgetnextassoc) ou [CMap::PGetFirstAssoc](#pgetfirstassoc) appeler.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’entrée suivante dans la carte ; consultez la page [CMap::CPair](#cpair). Si l’élément est le dernier de la carte, la valeur est **NULL**.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode pour effectuer une itération dans tous les éléments dans la carte. Récupérer le premier élément avec un appel à `PGetFirstAssoc` , puis itérer la carte avec les appels successifs à `PGetNextAssoc`.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CMap::PGetFirstAssoc](#pgetfirstassoc).  
  
##  <a name="a-nameplookupa--cmapplookup"></a><a name="plookup"></a>CMap::PLookup  
 Recherche la valeur mappée à une clé donnée.  
  
```  
const CPair* PLookup(ARG_KEY  key) const;
CPair* PLookup(Â    ARG_KEY  keyÂ);  ```  
  
### Parameters  
 `key`  
 Key for the element to be searched for.  
  
### Return Value  
 A pointer to a key structure; see [CMap::CPair](#cpair). If no match is found, `CMap::PLookup` returns `NULL`.  
  
### Remarks  
 Call this method to search for a map element with a key that exactly matches the given key.  
  
### Example  
 [!code-cpp[NVC_MFCCollections#60](../../mfc/codesnippet/cpp/cmap-class_5.cpp)]  
  
##  <a name="removeall"></a>  CMap::RemoveAll  
 Removes all the values from this map by calling the global helper function **DestructElements**.  
  
```  
void RemoveAll() ;
```  
  
### Remarks  
 The function works correctly if the map is already empty.  
  
### Example  
 [!code-cpp[NVC_MFCCollections#61](../../mfc/codesnippet/cpp/cmap-class_6.cpp)]  
  
##  <a name="removekey"></a>  CMap::RemoveKey  
 Looks up the map entry corresponding to the supplied key; then, if the key is found, removes the entry.  
  
```  
BOOL RemoveKey(ARG_KEY key) ;
```  
  
### Parameters  
 `ARG_KEY`  
 Template parameter specifying the type of the key.  
  
 `key`  
 Key for the element to be removed.  
  
### Return Value  
 Nonzero if the entry was found and successfully removed; otherwise 0.  
  
### Remarks  
 The **DestructElements** helper function is used to remove the entry.  
  
### Example  
 See the example for [CMap::SetAt](#setat).  
  
##  <a name="setat"></a>  CMap::SetAt  
 The primary means to insert an element in a map.  
  
```  
void SetAt (ARG_KEY clé, ARG_VALUE newValue) ;
```  
  
### Parameters  
 `ARG_KEY`  
 Template parameter specifying the type of the `key` parameter.  
  
 `key`  
 Specifies the key of the new element.  
  
 `ARG_VALUE`  
 Template parameter specifying the type of the `newValue` parameter.  
  
 `newValue`  
 Specifies the value of the new element.  
  
### Remarks  
 First, the key is looked up. If the key is found, then the corresponding value is changed; otherwise a new key-value pair is created.  
  
### Example  
 [!code-cpp[NVC_MFCCollections#62](../../mfc/codesnippet/cpp/cmap-class_7.cpp)]  
  
## See Also  
 [MFC Sample COLLECT](../../visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)  

