---
title: Classe de CComCachedTearOffObject | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::AddRef
- ATLCOM/ATL::CComCachedTearOffObject::FinalConstruct
- ATLCOM/ATL::CComCachedTearOffObject::FinalRelease
- ATLCOM/ATL::CComCachedTearOffObject::QueryInterface
- ATLCOM/ATL::CComCachedTearOffObject::Release
- ATLCOM/ATL::CComCachedTearOffObject::m_contained
dev_langs:
- C++
helpviewer_keywords:
- cache, ATL cached tear-off objects
- CComCachedTearOffObject class
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
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
ms.openlocfilehash: 96f040c732c5545a9b8febb32fcb1636f0fe4a40
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcachedtearoffobject-class"></a>CComCachedTearOffObject (classe)
Cette classe implémente [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) pour une interface détachables.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template
 <class contained>
class CComCachedTearOffObject : public
    IUnknown,
public CComObjectRootEx<contained
 ::_ThreadModel::ThreadModelNoCS>
```  
  
#### <a name="parameters"></a>Paramètres  
 `contained`  
 Votre classe détachables, dérivée de `CComTearOffObjectBase` et les interfaces que votre objet détachable pour prendre en charge.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComCachedTearOffObject::CComCachedTearOffObject](#ccomcachedtearoffobject)|Constructeur.|  
|[CComCachedTearOffObject :: ~ CComCachedTearOffObject](#dtor)|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CComCachedTearOffObject::AddRef](#addref)|Incrémente le décompte de références pour un `CComCachedTearOffObject` objet.|  
|[CComCachedTearOffObject::FinalConstruct](#finalconstruct)|Appelle le `m_contained::FinalConstruct` (la détachable méthode classe).|  
|[CComCachedTearOffObject::FinalRelease](#finalrelease)|Appelle le `m_contained::FinalRelease` (la détachable méthode classe).|  
|[CComCachedTearOffObject::QueryInterface](#queryinterface)|Retourne un pointeur vers le `IUnknown` de la `CComCachedTearOffObject` objet, ou à l’interface demandée sur votre classe détachable (la classe `contained`).|  
|[CComCachedTearOffObject::Release](#release)|Décrémente le décompte de références pour un `CComCachedTearOffObject` de l’objet et il détruit si le décompte de références est 0.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComCachedTearOffObject::m_contained](#m_contained)|A `CComContainedObject` objet dérivé votre classe détachable (la classe `contained`).|  
  
## <a name="remarks"></a>Remarques  
 `CComCachedTearOffObject`implémente [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) pour une interface détachables. Diffère de cette classe `CComTearOffObject` dans `CComCachedTearOffObject` a son propre **IUnknown**, indépendamment de l’objet propriétaire **IUnknown** (le propriétaire est l’objet pour lequel le détachable est créé). `CComCachedTearOffObject`conserve son propre le décompte de références sur son **IUnknown** et supprimé une fois que son décompte de références est égal à zéro. Toutefois, si vous interrogez des ses détachables interfaces, le décompte de références de l’objet propriétaire **IUnknown** est incrémentée.  
  
 Si le `CComCachedTearOffObject` objet implémentant le détachable est déjà instanciée, et l’interface détachable est interrogé pour là encore, la même `CComCachedTearOffObject` objet est réutilisé. En revanche, si une interface détachable implémentée par un `CComTearOffObject` est à nouveau interrogé pour via l’objet propriétaire, un autre `CComTearOffObject` est instancié.  
  
 Le propriétaire de la classe doit implémenter `FinalRelease` et appelez **version** sur la mise en cache **IUnknown** pour le `CComCachedTearOffObject`, qui décrémente son décompte de références. Cela entraîne `CComCachedTearOffObject`de `FinalRelease` pour être appelée et supprimer le détachables.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComCachedTearOffObject`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
##  <a name="addref"></a>CComCachedTearOffObject::AddRef  
 Incrémente le décompte de références du `CComCachedTearOffObject` objet par 1.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur qui peut être utile pour les tests de diagnostic et de test.  
  
##  <a name="ccomcachedtearoffobject"></a>CComCachedTearOffObject::CComCachedTearOffObject  
 Constructeur.  
  
```
CComCachedTearOffObject(void* pv);
```  
  
### <a name="parameters"></a>Paramètres  
 `pv`  
 [in] Pointeur vers le **IUnknown** de la `CComCachedTearOffObject`.  
  
### <a name="remarks"></a>Notes  
 Initialise le `CComContainedObject` membre, [m_contained](#m_contained).  
  
##  <a name="dtor"></a>CComCachedTearOffObject :: ~ CComCachedTearOffObject  
 Destructeur.  
  
```
~CComCachedTearOffObject();
```  
  
### <a name="remarks"></a>Remarques  
 Libère toutes les ressources attribuées et les appels [FinalRelease](#finalrelease).  
  
##  <a name="finalconstruct"></a>CComCachedTearOffObject::FinalConstruct  
 Appels **m_contained::FinalConstruct** création `m_contained`, le `CComContainedObject` <  `contained`> objet utilisé pour accéder à l’interface implémenté par votre classe détachables.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
##  <a name="finalrelease"></a>CComCachedTearOffObject::FinalRelease  
 Appels **m_contained::FinalRelease** de `m_contained`, le `CComContainedObject` <  `contained`> objet.  
  
```
void FinalRelease();
```  
  
##  <a name="m_contained"></a>CComCachedTearOffObject::m_contained  
 A [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) objet dérivé votre classe détachables.  
  
```
CcomContainedObject <contained> m_contained;
```     
  
### <a name="parameters"></a>Paramètres  
 `contained`  
 [in] Votre classe détachables, dérivée de `CComTearOffObjectBase` et les interfaces que votre objet détachable pour prendre en charge.  
  
### <a name="remarks"></a>Remarques  
 Les méthodes `m_contained` hérite sont utilisés pour accéder à l’interface détachable dans votre classe détachable via l’objet mis en cache détachable `QueryInterface`, `FinalConstruct`, et `FinalRelease`.  
  
##  <a name="queryinterface"></a>CComCachedTearOffObject::QueryInterface  
 Récupère un pointeur vers l'interface demandée.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Paramètres  
 `iid`  
 [in] Le GUID de l’interface demandée.  
  
 `ppvObject`  
 [out] Un pointeur vers le pointeur d’interface identifié par `iid`, ou **NULL** si l’interface est introuvable.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Notes  
 Si l’interface demandée est **IUnknown**, retourne un pointeur vers le `CComCachedTearOffObject`de propre **IUnknown** et incrémente le décompte de références. Sinon, les requêtes pour l’interface sur votre classe détachable à l’aide de la [InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) héritée de la méthode `CComObjectRootEx`.  

  
##  <a name="release"></a>CComCachedTearOffObject::Release  
 Décrémente le décompte de références de 1 et, si le décompte de références est 0, supprime la `CComCachedTearOffObject` objet.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Dans les versions non debug retourne toujours 0. Dans les versions debug, retourne une valeur qui peut être utile pour les tests de diagnostic ou de test.  
  
## <a name="see-also"></a>Voir aussi  
 [CComTearOffObject (classe)](../../atl/reference/ccomtearoffobject-class.md)   
 [CComObjectRootEx (classe)](../../atl/reference/ccomobjectrootex-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

