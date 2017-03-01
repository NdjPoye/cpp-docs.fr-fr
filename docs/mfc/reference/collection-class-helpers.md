---
title: Classe de collection Helpers | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- DestructElements function
- ConstructElements function
- SerializeElements function
- collection classes, helper functions
- helper functions collection class
ms.assetid: bc3a2368-9edd-4748-9e6a-13cba79517ca
caps.latest.revision: 14
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
ms.openlocfilehash: d2649ef9c8b0320a94ec28a2341baa0f768b07d0
ms.lasthandoff: 02/24/2017

---
# <a name="collection-class-helpers"></a>Programmes d’assistance pour les classes de collection
Les classes de collection `CMap`, `CList`, et `CArray` utilisent les fonctions d’assistance globales basé sur un modèle fins telles que la comparaison, la copie et la sérialisation des éléments. Dans le cadre de votre implémentation de classes basées sur `CMap`, `CList`, et `CArray`, vous devez substituer ces fonctions en fonction des besoins avec des versions adaptées au type de données stockées dans votre carte, une liste ou un tableau. Pour plus d’informations sur la substitution des fonctions d’assistance telles que `SerializeElements`, consultez l’article [Collections : comment créer une Collection de Type sécurisé](../../mfc/how-to-make-a-type-safe-collection.md). Notez que **ConstructElements** et **DestructElements** ont été déconseillées.  
  
 La bibliothèque Microsoft Foundation Class fournit les fonctions globales suivantes pour vous aider à personnaliser vos classes de collection afxtempl.h :  
  
### <a name="collection-class-helpers"></a>Programmes d’assistance pour les classes de collection  
  
|||  
|-|-|  
|[CompareElements](#compareelements)|Indique si les éléments sont les mêmes.|  
|[CopyElements](#copyelements)|Copie les éléments d’un tableau à un autre.|  
|[DumpElements](#dumpelements)|Fournit une sortie de diagnostic orienté flux de données.|  
|[HashKey](#hashkey)|Calcule une clé de hachage.|  
|[SerializeElements](#serializeelements)|Stocke ou extrait des éléments vers ou à partir d’une archive.|  
  
##  <a name="a-namecompareelementsa--compareelements"></a><a name="compareelements"></a>CompareElements  
 Appelé directement par [CList::Find] (clist-class.md #not_found.md #clist__find et indirectement par [cmap__lookup](cmap-class.md#lookup) et [[] cmap__operator](cmap-class.md#operator_at).  
  
```   
template<class TYPE, class ARG_TYPE>  
BOOL AFXAPI  
CompareElements(
    const TYPE* pElement1,  
    const ARG_TYPE* pElement2);  
```  
  
### <a name="parameters"></a>Paramètres  
 *TYPE*  
 Le type du premier élément à comparer.  
  
 `pElement1`  
 Pointeur vers le premier élément à comparer.  
  
 `ARG_TYPE`  
 Le type du deuxième élément à comparer.  
  
 `pElement2`  
 Pointeur vers le deuxième élément à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’objet pointé par `pElement1` est égal à l’objet pointé par `pElement2`; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Le `CMap` appelle utiliser le `CMap` les paramètres de modèle *clé* et `ARG_KEY`.  
  
 L’implémentation par défaut retourne le résultat de la comparaison de * \*pElement1* et * \*pElement2*. Remplacez cette fonction pour qu’elle compare les éléments d’une manière qui convient à votre application.  
  
 Le langage C++ définit l’opérateur de comparaison ( `==`) pour les types simples ( `char`, `int`, **float**, et ainsi de suite) mais ne définit ne pas un opérateur de comparaison pour les classes et structures. Si vous souhaitez utiliser `CompareElements` ou pour instancier l’une des classes de collection qui l’utilise, vous devez définir l’opérateur de comparaison ou surcharge `CompareElements` avec une version qui renvoie les valeurs appropriées.  
  
### <a name="requirements"></a>Spécifications  
   **En-tête :** afxtempl.h   
  
##  <a name="a-namecopyelementsa--copyelements"></a><a name="copyelements"></a>CopyElements  
 Cette fonction est appelée directement par [CArray::Append](carray-class.md#append) et [CArray::Copy](carray-class.md#copy).  
  
```   
template<class TYPE>  
void AFXAPI CopyElements(
    TYPE* pDest,  
    const TYPE* pSrc,  
    INT_PTR nCount);  
```  
  
### <a name="parameters"></a>Paramètres  
 *TYPE*  
 Paramètre de modèle spécifiant le type d’éléments à copier.  
  
 `pDest`  
 Pointeur vers la destination où les éléments sont copiés.  
  
 `pSrc`  
 Pointeur vers la source des éléments à copier.  
  
 `nCount`  
 Nombre d’éléments à copier.  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut utilise l’opérateur d’assignation simple ( ** = ** ) pour effectuer l’opération de copie. Si le type en cours de copie ne dispose pas d’un opérateur surchargé =, l’implémentation par défaut effectue une copie au niveau du bit.  
  
 Pour plus d’informations sur l’implémentation de cela et autres fonctions d’assistance, consultez l’article [Collections : comment créer une Collection de Type sécurisé](../how-to-make-a-type-safe-collection.md).  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxtempl.h  
  
##  <a name="a-namedumpelementsa--dumpelements"></a><a name="dumpelements"></a>DumpElements  
 Fournit une sortie de diagnostic orienté flux de données sous forme de texte pour les éléments de votre collection en cas de substitution.  
  
```   
template<class TYPE>  
void  AFXAPI DumpElements(
    CDumpContext& dc,  
    const TYPE* pElements,  
    INT_PTR nCount);  
```  
  
### <a name="parameters"></a>Paramètres  
 `dc`  
 Vider le contexte pour faire un dump des éléments.  
  
 *TYPE*  
 Paramètre de modèle qui spécifie le type des éléments.  
  
 `pElements`  
 Pointeur vers les éléments à être vidées.  
  
 `nCount`  
 Nombre d’éléments à être vidées.  
  
### <a name="remarks"></a>Remarques  
 Le **CArray::Dump**, **CList::Dump**, et **CMap::Dump** fonctions appellent cela si la profondeur de l’image est supérieure à 0.  
  
 L'implémentation par défaut n'exécute aucune opération. Si les éléments de votre collection sont dérivés de `CObject`, votre remplacement sera généralement une itération au sein des éléments de la collection, appelant `Dump` pour chaque élément à son tour.  
  

### <a name="requirements"></a>Spécifications  
  **En-tête** afxtempl.h  
  
##  <a name="a-namehashkeya--hashkey"></a><a name="hashkey"></a>HashKey  
 Calcule une valeur de hachage pour la clé donnée.  
  
```  
template<class ARG_KEY>  
AFX_INLINE UINT AFXAPI HashKey(ARG_KEY  key); 
```  
  
### <a name="parameters"></a>Paramètres  
 `ARG_KEY`  
 Paramètre de modèle qui spécifie le type de données permettant d’accéder aux clés de carte.  
  
 `key`  
 Clé dont la valeur hachage doit être calculé.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur de hachage de la clé.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est appelée directement par [CMap::RemoveKey](cmap-class.md#removekey) et indirectement par [CMap::Lookup](cmap-class.md#lookup) et [[] CMap::Operator](cmap-class.md#operator_at).
  
 L’implémentation par défaut crée une valeur de hachage en utilisant `key` droite par quatre positions. Remplacez cette fonction afin qu’il retourne des valeurs de hachage appropriée pour votre application.  
  
### <a name="example"></a>Exemple
 ```cpp  
template <> UINT AFXAPI HashKey(unsigned __int64 key)
{
   // Generate the hash value by XORing the lower 32 bits of the number 
   // with the upper 32 bits
   return(UINT(key) ^ UINT(key >> 32));
}
 ```
 
### <a name="requirements"></a>Spécifications  
  **En-tête** afxtempl.h 
  
##  <a name="a-nameserializeelementsa--serializeelements"></a><a name="serializeelements"></a>SerializeElements  
 [CArray](carray-class.md), [CList](clist-class.md), et [CMap](cmap-class.md) appelez cette fonction pour sérialiser des éléments.  
  
```   
template<class TYPE>  
void AFXAPI SerializeElements(CArchive& ar, TYPE* pElements, INT_PTR nCount);  
```  
  
### <a name="parameters"></a>Paramètres  
 *TYPE*  
 Paramètre de modèle qui spécifie le type des éléments.  
  
 `ar`  
 Un objet archive archiver vers ou à partir de.  
  
 `pElements`  
 Pointeur vers les éléments archivés.  
  
 `nCount`  
 Nombre d’éléments archivés  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut est une opération de bits lecture ou d’écriture.  
  
 Pour plus d’informations sur l’implémentation de cela et autres fonctions d’assistance, consultez l’article [Collections : comment créer une Collection de Type sécurisé](../how-to-make-a-type-safe-collection.md).  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple dans l’article [Collections : comment créer une Collection de Type sécurisé](../how-to-make-a-type-safe-collection.md).  
 
### <a name="requirements"></a>Spécifications  
  **En-tête** afxtempl.h 
    
## <a name="see-also"></a>Voir aussi  
 [Macros and Globals](mfc-macros-and-globals.md)   
 [CMap (classe)](cmap-class.md)   
 [CList (classe)](clist-class.md)   
 [CArray (classe)](carray-class.md)
