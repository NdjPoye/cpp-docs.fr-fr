---
title: Classe de CComSingleThreadModel | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComSingleThreadModel
- CComSingleThreadModel
- ATL::CComSingleThreadModel
dev_langs:
- C++
helpviewer_keywords:
- single-threaded applications
- CComSingleThreadModel class
- single-threaded applications, ATL
ms.assetid: e5dc30c7-405a-4ba4-8ae9-51937243fce8
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: ff5d8d2ced1d6fe0196888d8c746844ace8307f8
ms.lasthandoff: 02/24/2017

---
# <a name="ccomsinglethreadmodel-class"></a>CComSingleThreadModel (classe)
Cette classe fournit des méthodes pour incrémenter et décrémenter la valeur d’une variable.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CComSingleThreadModel
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComSingleThreadModel::AutoCriticalSection](#autocriticalsection)|Fait référence à la classe [la classe CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).|  
|[CComSingleThreadModel::CriticalSection](#criticalsection)|Fait référence à la classe `CComFakeCriticalSection`.|  
|[CComSingleThreadModel::ThreadModelNoCS](#threadmodelnocs)|Références `CComSingleThreadModel`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CComSingleThreadModel::Decrement](#decrement)|Décrémente la valeur de la variable spécifiée. Cette implémentation n’est pas thread-safe.|  
|[CComSingleThreadModel::Increment](#increment)|Incrémente la valeur de la variable spécifiée. Cette implémentation n’est pas thread-safe.|  
  
## <a name="remarks"></a>Remarques  
 `CComSingleThreadModel`Fournit des méthodes pour incrémenter et décrémenter la valeur d’une variable. Contrairement aux [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) et [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), ces méthodes ne sont pas thread-safe.  

 En général, vous utilisez `CComSingleThreadModel` via un des deux `typedef` les noms, soit [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) ou [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel). La classe référencée par chaque `typedef` varie selon le modèle de thread utilisé, comme indiqué dans le tableau suivant :  

  
|typedef|Modèle de thread unique|Modèle de thread cloisonné|Modèle de thread libre|  
|-------------|----------------------------|-------------------------------|--------------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S= `CComSingleThreadModel`; M =`CComMultiThreadModel`  
  
 `CComSingleThreadModel`lui-même définit trois `typedef` noms. `ThreadModelNoCS`références `CComSingleThreadModel`. `AutoCriticalSection`et `CriticalSection` reference, classe [la classe CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), qui fournit des méthodes vides associés d’obtenir et de libérer la possession d’une section critique.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
##  <a name="a-nameautocriticalsectiona--ccomsinglethreadmodelautocriticalsection"></a><a name="autocriticalsection"></a>CComSingleThreadModel::AutoCriticalSection  
 Lorsque vous utilisez `CComSingleThreadModel`, le `typedef` nom `AutoCriticalSection` fait référence à la classe [la classe CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>Remarques  
 Étant donné que `CComFakeCriticalSection` ne fournit pas une section critique, ses méthodes ne rien font.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) et [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) contiennent des définitions pour `AutoCriticalSection`. Le tableau suivant montre la relation entre la classe de modèle de thread et la classe de section critique référencée par `AutoCriticalSection`:  
  
|Classe définie dans|Classe référencée|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComAutoCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 En plus de `AutoCriticalSection`, vous pouvez utiliser la `typedef` nom [CriticalSection](#criticalsection). Vous ne devez pas spécifier `AutoCriticalSection` dans des objets globaux ou des membres de classe statique si vous souhaitez supprimer le code de démarrage CRT.  
  
### <a name="example"></a>Exemple  
 Consultez la page [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="a-namecriticalsectiona--ccomsinglethreadmodelcriticalsection"></a><a name="criticalsection"></a>CComSingleThreadModel::CriticalSection  
 Lorsque vous utilisez `CComSingleThreadModel`, le `typedef` nom `CriticalSection` fait référence à la classe [la classe CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>Remarques  
 Étant donné que `CComFakeCriticalSection` ne fournit pas une section critique, ses méthodes ne rien font.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) et [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) contiennent des définitions pour `CriticalSection`. Le tableau suivant montre la relation entre la classe de modèle de thread et la classe de section critique référencée par `CriticalSection`:  
  
|Classe définie dans|Classe référencée|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 En plus de `CriticalSection`, vous pouvez utiliser la `typedef` nom [AutoCriticalSection](#autocriticalsection). Vous ne devez pas spécifier `AutoCriticalSection` dans des objets globaux ou des membres de classe statique si vous souhaitez supprimer le code de démarrage CRT.  
  
### <a name="example"></a>Exemple  
 Consultez la page [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="a-namedecrementa--ccomsinglethreadmodeldecrement"></a><a name="decrement"></a>CComSingleThreadModel::Decrement  
 Décrémente de cette fonction statique la valeur de la variable vers laquelle pointe `p`.  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `p`  
 [in] Pointeur vers la variable à décrémenter.  
  
### <a name="return-value"></a>Valeur de retour  
 Le résultat de la décrémentation.  
  
##  <a name="a-nameincrementa--ccomsinglethreadmodelincrement"></a><a name="increment"></a>CComSingleThreadModel::Increment  
 Décrémente de cette fonction statique la valeur de la variable vers laquelle pointe `p`.  
  
```
static ULONG WINAPI Increment(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `p`  
 [in] Pointeur vers la variable à incrémenter.  
  
### <a name="return-value"></a>Valeur de retour  
 Le résultat de l’incrément.  
  
##  <a name="a-namethreadmodelnocsa--ccomsinglethreadmodelthreadmodelnocs"></a><a name="threadmodelnocs"></a>CComSingleThreadModel::ThreadModelNoCS  
 Lorsque vous utilisez `CComSingleThreadModel`, le `typedef` nom `ThreadModelNoCS` fait simplement référence à `CComSingleThreadModel`.  
  
```
typedef CComSingleThreadModel ThreadModelNoCS;
```  
  
### <a name="remarks"></a>Remarques  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) et [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) contiennent des définitions pour `ThreadModelNoCS`. Le tableau suivant montre la relation entre la classe de modèle de thread et la classe référencée par `ThreadModelNoCS`:  
  
|Classe définie dans|Classe référencée|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
  
### <a name="example"></a>Exemple  
 Consultez la page [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

