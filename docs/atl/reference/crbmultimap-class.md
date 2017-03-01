---
title: Classe de CRBMultiMap | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRBMultiMap
- ATL.CRBMultiMap
- ATL::CRBMultiMap
dev_langs:
- C++
helpviewer_keywords:
- CRBMultiMap class
ms.assetid: 94d3ec0c-3e30-4ab7-a101-d8da4fb8add3
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
ms.openlocfilehash: a72ddfbf4944f0de5e979f7046872d594017b9cf
ms.lasthandoff: 02/24/2017

---
# <a name="crbmultimap-class"></a>CRBMultiMap (classe)
Cette classe représente une structure de mappage qui permet à que chaque clé peut être associé à plusieurs valeurs, à l’aide d’une arborescence binaire rouge-noire.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<typename K,
         typename V, 
         class KTraits = CElementTraits<K>, 
         class VTraits = CElementTraits<V>>  
class CRBMultiMap : public CRBTree<K, V, KTraits, VTraits>
```    
  
#### <a name="parameters"></a>Paramètres  
 `K`  
 Le type d’élément clé.  
  
 *V*  
 Le type d’élément de valeur.  
  
 `KTraits`  
 Le code utilisé pour copier ou déplacer des éléments clés. Consultez la page [CElementTraits classe](../../atl/reference/celementtraits-class.md) pour plus de détails.  
  
 `VTraits`  
 Le code utilisé pour copier ou déplacer des éléments de valeur.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CRBMultiMap::CRBMultiMap](#crbmultimap)|Constructeur.|  
|[CRBMultiMap :: ~ CRBMultiMap](#dtor)|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CRBMultiMap::FindFirstWithKey](#findfirstwithkey)|Appelez cette méthode pour trouver la position du premier élément avec une clé donnée.|  
|[CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)|Appelez cette méthode pour obtenir la valeur associée à une clé donnée et mettre à jour la valeur de position.|  
|[CRBMultiMap::GetNextWithKey](#getnextwithkey)|Appelez cette méthode pour obtenir l’élément associé à une clé donnée et mettre à jour la valeur de position.|  
|[CRBMultiMap::Insert](#insert)|Appelez cette méthode pour insérer une paire de l’élément dans le mappage.|  
|[CRBMultiMap::RemoveKey](#removekey)|Appelez cette méthode pour supprimer tous les éléments clé/valeur d’une clé spécifique.|  
  
## <a name="remarks"></a>Remarques  
 `CRBMultiMap`prend en charge un tableau de mappage d’un type donné, la gestion d’un tableau ordonné d’éléments clés et valeurs. Contrairement à la [CRBMap](../../atl/reference/crbmap-class.md) (classe), chaque clé peut être associé à plusieurs valeurs.  
  
 Éléments (composé d’une clé et une valeur) sont stockés dans une arborescence binaire à l’aide de la structure du [CRBMultiMap::Insert](#insert) (méthode). Les éléments peuvent être supprimés à l’aide de la [CRBMultiMap::RemoveKey](#removekey) (méthode), ce qui supprime tous les éléments qui correspondent à la clé donnée.  
  
 Parcours de l’arborescence est possible avec des méthodes telles que [CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext), et [CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue). L’accès à la potentiellement plusieurs valeurs par clé est possible grâce au [CRBMultiMap::FindFirstWithKey](#findfirstwithkey), [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey), et [CRBMultiMap::GetNextWithKey](#getnextwithkey) méthodes. Consultez l’exemple de [CRBMultiMap::CRBMultiMap](#crbmultimap) pour une illustration dans la pratique.  
  
 Le `KTraits` et `VTraits` paramètres sont des classes de traits qui contiennent tout code supplémentaire nécessaire pour copier ou déplacer des éléments.  
  
 `CRBMultiMap`est dérivé [CRBTree](../../atl/reference/crbtree-class.md), qui implémente un arbre binaire à l’aide de l’algorithme rouge-noire. Une alternative à `CRBMultiMap` et `CRBMap` est proposé par le [CAtlMap](../../atl/reference/catlmap-class.md) classe. Lorsque seulement un petit nombre d’éléments doit être stockée, envisagez d’utiliser le [CSimpleMap](../../atl/reference/csimplemap-class.md) classe à la place.  
  
 Pour une description plus complète des diverses classes de collection et leurs fonctionnalités et les caractéristiques de performance, consultez [Classes de Collection ATL](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CRBTree](../../atl/reference/crbtree-class.md)  
  
 `CRBMultiMap`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcoll.h  
  
##  <a name="a-namecrbmultimapa--crbmultimapcrbmultimap"></a><a name="crbmultimap"></a>CRBMultiMap::CRBMultiMap  
 Constructeur.  
  
```
explicit CRBMultiMap(size_t nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nBlockSize`  
 La taille du bloc.  
  
### <a name="remarks"></a>Remarques  
 Le `nBlockSize` paramètre est une mesure de la quantité de mémoire allouée lorsqu’un nouvel élément est requis. Tailles de bloc supérieures réduisent les appels aux routines d’allocation de mémoire, mais utilisent davantage de ressources. La valeur par défaut alloue de l’espace de 10 éléments à la fois.  
  
 Consultez la documentation de la classe de base [CRBTree](../../atl/reference/crbtree-class.md) pour plus d’informations sur les autres méthodes disponibles.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Utilities&#85;](../../atl/codesnippet/cpp/crbmultimap-class_1.cpp)]  
  
##  <a name="a-namedtora--crbmultimapcrbmultimap"></a><a name="dtor"></a>CRBMultiMap :: ~ CRBMultiMap  
 Destructeur.  
  
```
~CRBMultiMap() throw();
```  
  
### <a name="remarks"></a>Notes  
 Libère toutes les ressources allouées.  
  
 Consultez la documentation de la classe de base [CRBTree](../../atl/reference/crbtree-class.md) pour plus d’informations sur les autres méthodes disponibles.  
  
##  <a name="a-namefindfirstwithkeya--crbmultimapfindfirstwithkey"></a><a name="findfirstwithkey"></a>CRBMultiMap::FindFirstWithKey  
 Appelez cette méthode pour trouver la position du premier élément avec une clé donnée.  
  
```
POSITION FindFirstWithKey(KINARGTYPE key) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `key`  
 Spécifie la clé qui identifie l’élément à rechercher.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la POSITION du premier élément de clé/valeur si la clé est trouvée, NULL sinon.  
  
### <a name="remarks"></a>Notes  
 Une clé dans le `CRBMultiMap` peut avoir une ou plusieurs valeurs associées. Cette méthode fournit la valeur de position de la première valeur (qui peut être en fait, la seule valeur) associée à cette clé particulière. La valeur de position renvoyée puis peut être utilisée avec [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey) ou [CRBMultiMap::GetNextWithKey](#getnextwithkey) pour obtenir la valeur et de mettre à jour la position.  
  
 Consultez la documentation de la classe de base [CRBTree](../../atl/reference/crbtree-class.md) pour plus d’informations sur les autres méthodes disponibles.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CRBMultiMap::CRBMultiMap](#crbmultimap).  
  
##  <a name="a-namegetnextvaluewithkeya--crbmultimapgetnextvaluewithkey"></a><a name="getnextvaluewithkey"></a>CRBMultiMap::GetNextValueWithKey  
 Appelez cette méthode pour obtenir la valeur associée à une clé donnée et mettre à jour la valeur de position.  
  
```
const V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `pos`  
 La valeur de position, obtenue par un appel à [CRBMultiMap::FindFirstWithKey](#findfirstwithkey) ou [CRBMultiMap::GetNextWithKey](#getnextwithkey), ou un appel précédent à `GetNextValueWithKey`.  
  
 `key`  
 Spécifie la clé qui identifie l’élément à rechercher.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la paire de l’élément associée à la clé donnée.  
  
### <a name="remarks"></a>Notes  
 La valeur de position est mise à jour pour pointer vers la valeur suivante est associée à la clé. Si aucune valeur n’existe, la valeur de position est définie sur NULL.  
  
 Consultez la documentation de la classe de base [CRBTree](../../atl/reference/crbtree-class.md) pour plus d’informations sur les autres méthodes disponibles.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CRBMultiMap::CRBMultiMap](#crbmultimap).  
  
##  <a name="a-namegetnextwithkeya--crbmultimapgetnextwithkey"></a><a name="getnextwithkey"></a>CRBMultiMap::GetNextWithKey  
 Appelez cette méthode pour obtenir l’élément associé à une clé donnée et mettre à jour la valeur de position.  
  
```
const CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `pos`  
 La valeur de position, obtenue par un appel à [CRBMultiMap::FindFirstWithKey](#findfirstwithkey) ou [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey), ou un appel précédent à `GetNextWithKey`.  
  
 `key`  
 Spécifie la clé qui identifie l’élément à rechercher.  
  
### <a name="return-value"></a>Valeur de retour  
 Renvoie la prochaine [CRBTree::CPair classe](crbtree-class.md#cpair_class) élément associé à la clé donnée.  
  
### <a name="remarks"></a>Notes  
 La valeur de position est mise à jour pour pointer vers la valeur suivante est associée à la clé. Si aucune valeur n’existe, la valeur de position est définie sur NULL.  
  
 Consultez la documentation de la classe de base [CRBTree](../../atl/reference/crbtree-class.md) pour plus d’informations sur les autres méthodes disponibles.  
  
##  <a name="a-nameinserta--crbmultimapinsert"></a><a name="insert"></a>CRBMultiMap::Insert  
 Appelez cette méthode pour insérer une paire de l’élément dans le mappage.  
  
```
POSITION Insert(KINARGTYPE key, VINARGTYPE value) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `key`  
 La valeur de clé à ajouter à la `CRBMultiMap` objet.  
  
 *value*  
 La valeur à ajouter à la `CRBMultiMap` est associé, `key`.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la position de la paire d’élément clé/valeur dans la `CRBMultiMap` objet.  
  
### <a name="remarks"></a>Remarques  
 Consultez la documentation de la classe de base [CRBTree](../../atl/reference/crbtree-class.md) pour plus d’informations sur les autres méthodes disponibles.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CRBMultiMap::CRBMultiMap](#crbmultimap).  
  
##  <a name="a-nameremovekeya--crbmultimapremovekey"></a><a name="removekey"></a>CRBMultiMap::RemoveKey  
 Appelez cette méthode pour supprimer tous les éléments clé/valeur d’une clé spécifique.  
  
```
size_t RemoveKey(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `key`  
 Spécifie la clé qui identifie l’ou les éléments à supprimer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre de valeurs associées à la clé donnée.  
  
### <a name="remarks"></a>Notes  
 `RemoveKey`Supprime tous les éléments clé/valeur qui a une clé qui correspond à `key`.  
  
 Consultez la documentation de la classe de base [CRBTree](../../atl/reference/crbtree-class.md) pour plus d’informations sur les autres méthodes disponibles.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CRBMultiMap::CRBMultiMap](#crbmultimap).  
  
## <a name="see-also"></a>Voir aussi  
 [CRBTree (classe)](../../atl/reference/crbtree-class.md)   
 [CAtlMap (classe)](../../atl/reference/catlmap-class.md)   
 [CRBMap (classe)](../../atl/reference/crbmap-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

