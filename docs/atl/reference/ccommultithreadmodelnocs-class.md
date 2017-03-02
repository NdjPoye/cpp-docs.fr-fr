---
title: Classe de CComMultiThreadModelNoCS | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CComMultiThreadModelNoCS
- CComMultiThreadModelNoCS
- ATL.CComMultiThreadModelNoCS
dev_langs:
- C++
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModelNoCS class
- threading [ATL]
ms.assetid: 2b3f7a45-fd72-452c-aaf3-ccdaa621c821
caps.latest.revision: 18
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
ms.openlocfilehash: 718aac826916b977eec4fb8400da81b5e32d4afa
ms.lasthandoff: 02/24/2017

---
# <a name="ccommultithreadmodelnocs-class"></a>CComMultiThreadModelNoCS (classe)
`CComMultiThreadModelNoCS`Fournit des méthodes thread-safe pour incrémenter et décrémenter la valeur d’une variable, sans la section critique verrouillage ou déverrouillage de fonctionnalités.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CComMultiThreadModelNoCS
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComMultiThreadModelNoCS::AutoCriticalSection](#autocriticalsection)|Fait référence à la classe [la classe CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).|  
|[CComMultiThreadModelNoCS::CriticalSection](#criticalsection)|Fait référence à la classe `CComFakeCriticalSection`.|  
|[CComMultiThreadModelNoCS::ThreadModelNoCS](#threadmodelnocs)|Fait référence à la classe `CComMultiThreadModelNoCS`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CComMultiThreadModelNoCS::Decrement](#decrement)|(Statique) Décrémente la valeur de la variable spécifiée de manière thread-safe.|  
|[CComMultiThreadModelNoCS::Increment](#increment)|(Statique) Incrémente la valeur de la variable spécifiée de manière thread-safe.|  
  
## <a name="remarks"></a>Remarques  
 `CComMultiThreadModelNoCS`est semblable à [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) car elle fournit des méthodes thread-safe pour l’incrémentation et décrémentation de variable. Toutefois, lorsque vous référencez une classe de la section critique via `CComMultiThreadModelNoCS`, des méthodes telles que `Lock` et `Unlock` ne fera rien.  
  
 En général, vous utilisez `CComMultiThreadModelNoCS` via la `ThreadModelNoCS``typedef` nom. Cela `typedef` est défini dans `CComMultiThreadModelNoCS`, `CComMultiThreadModel`, et [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md).  
  
> [!NOTE]
>  Global `typedef` noms [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) et [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel) ne font pas référence à `CComMultiThreadModelNoCS`.  
  
 En plus de `ThreadModelNoCS`, `CComMultiThreadModelNoCS` définit `AutoCriticalSection` et `CriticalSection`. Ces deux derniers `typedef` noms font référence à [la classe CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), qui fournit des méthodes vides associés à obtenir et à libérer une section critique.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
##  <a name="a-nameautocriticalsectiona--ccommultithreadmodelnocsautocriticalsection"></a><a name="autocriticalsection"></a>CComMultiThreadModelNoCS::AutoCriticalSection  
 Lorsque vous utilisez `CComMultiThreadModelNoCS`, le `typedef` nom `AutoCriticalSection` fait référence à la classe [la classe CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>Remarques  
 Étant donné que `CComFakeCriticalSection` ne fournit pas une section critique, ses méthodes ne rien font.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) et [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) contiennent également des définitions pour `AutoCriticalSection`. Le tableau suivant montre la relation entre la classe de modèle de thread et la classe de section critique référencée par `AutoCriticalSection`:  
  
|Classe définie dans|Classe référencée|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComAutoCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
  
 En plus de `AutoCriticalSection`, vous pouvez utiliser la `typedef` nom [CriticalSection](#criticalsection). Vous ne devez pas spécifier `AutoCriticalSection` dans des objets globaux ou des membres de classe statique si vous souhaitez supprimer le code de démarrage CRT.  
  
### <a name="example"></a>Exemple  
 Consultez la page [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="a-namecriticalsectiona--ccommultithreadmodelnocscriticalsection"></a><a name="criticalsection"></a>CComMultiThreadModelNoCS::CriticalSection  
 Lorsque vous utilisez `CComMultiThreadModelNoCS`, le `typedef` nom `CriticalSection` fait référence à la classe [la classe CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>Remarques  
 Étant donné que `CComFakeCriticalSection` ne fournit pas une section critique, ses méthodes ne rien font.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) et [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) contiennent également des définitions pour `CriticalSection`. Le tableau suivant montre la relation entre la classe de modèle de thread et la classe de section critique référencée par `CriticalSection`:  
  
|Classe définie dans|Classe référencée|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
  
 En plus de `CriticalSection`, vous pouvez utiliser la `typedef` nom `AutoCriticalSection`. Vous ne devez pas spécifier `AutoCriticalSection` dans des objets globaux ou des membres de classe statique si vous souhaitez supprimer le code de démarrage CRT.  
  
### <a name="example"></a>Exemple  
 Consultez la page [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="a-namedecrementa--ccommultithreadmodelnocsdecrement"></a><a name="decrement"></a>CComMultiThreadModelNoCS::Decrement  
 Cette fonction statique appelle la fonction Win32 [InterlockedDecrement](http://msdn.microsoft.com/library/windows/desktop/ms683580), qui décrémente la valeur de la variable vers laquelle pointe `p`.  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `p`  
 [in] Pointeur vers la variable à décrémenter.  
  
### <a name="return-value"></a>Valeur de retour  
 Si le résultat de la décrémentation est 0, puis `Decrement` retourne 0. Si le résultat de la décrémentation est différente de zéro, la valeur de retour est également différente de zéro, mais ne peut-être pas égaler le résultat de la décrémentation.  
  
### <a name="remarks"></a>Notes  
 **InterlockedDecrement** empêche que plusieurs threads simultanément à l’aide de cette variable.  
  
##  <a name="a-nameincrementa--ccommultithreadmodelnocsincrement"></a><a name="increment"></a>CComMultiThreadModelNoCS::Increment  
 Cette fonction statique appelle la fonction Win32 [InterlockedIncrement](http://msdn.microsoft.com/library/windows/desktop/ms683614), qui incrémente la valeur de la variable vers laquelle pointée `p`.  
  
```
static ULONG WINAPI Increment(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `p`  
 [in] Pointeur vers la variable à incrémenter.  
  
### <a name="return-value"></a>Valeur de retour  
 Si le résultat de l’incrément est 0, puis **incrément** retourne 0. Si le résultat de l’incrément est différente de zéro, la valeur de retour est également différente de zéro, mais le résultat de l’incrément ne peut pas égaler.  
  
### <a name="remarks"></a>Remarques  
 **InterlockedIncrement** empêche que plusieurs threads simultanément à l’aide de cette variable.  
  
##  <a name="a-namethreadmodelnocsa--ccommultithreadmodelnocsthreadmodelnocs"></a><a name="threadmodelnocs"></a>CComMultiThreadModelNoCS::ThreadModelNoCS  
 Lorsque vous utilisez `CComMultiThreadModelNoCS`, le `typedef` nom `ThreadModelNoCS` fait simplement référence à `CComMultiThreadModelNoCS`.  
  
```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```  
  
### <a name="remarks"></a>Notes  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) et [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) contiennent également des définitions pour `ThreadModelNoCS`. Le tableau suivant montre la relation entre la classe de modèle de thread et la classe référencée par `ThreadModelNoCS`:  
  
|Classe définie dans|Classe référencée|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
  
 Notez que la définition de `ThreadModelNoCS` dans `CComMultiThreadModelNoCS` fournit une symétrie avec `CComMultiThreadModel` et `CComSingleThreadModel`. Par exemple, supposons que l’exemple de code `CComMultiThreadModel::AutoCriticalSection` déclaré suit `typedef`:  
  
 [!code-cpp[NVC_ATL_COM&#37;](../../atl/codesnippet/cpp/ccommultithreadmodelnocs-class_1.h)]  
  
 Quelle que soit la classe spécifiée pour `ThreadModel` (tel que `CComMultiThreadModelNoCS`), `_ThreadModel` résout en conséquence.  
  
### <a name="example"></a>Exemple  
 Consultez la page [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
