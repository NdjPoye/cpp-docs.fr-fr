---
title: Classe de CComAggObject | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAggObject
- ATLCOM/ATL::CComAggObject
- ATLCOM/ATL::CComAggObject::CComAggObject
- ATLCOM/ATL::CComAggObject::AddRef
- ATLCOM/ATL::CComAggObject::CreateInstance
- ATLCOM/ATL::CComAggObject::FinalConstruct
- ATLCOM/ATL::CComAggObject::FinalRelease
- ATLCOM/ATL::CComAggObject::QueryInterface
- ATLCOM/ATL::CComAggObject::Release
- ATLCOM/ATL::CComAggObject::m_contained
dev_langs:
- C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComAggObject class
ms.assetid: 7aa90d69-d399-477b-880d-e2cdf0ef7881
caps.latest.revision: 29
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 2f580a33b5b92f44e40a3da2e1f7111cbb8ede88
ms.contentlocale: fr-fr
ms.lasthandoff: 03/31/2017

---
# <a name="ccomaggobject-class"></a>Classe de CComAggObject
Cette classe implémente la [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) interface pour un objet. Par définition, un objet est contenu dans un objet externe. Le `CComAggObject` classe est semblable à la [CComObject classe](../../atl/reference/ccomobject-class.md), à ceci près qu’il expose une interface qui est directement accessible aux clients externes.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class contained>  
class CComAggObject : public IUnknown, 
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```  
  
#### <a name="parameters"></a>Paramètres  
 `contained`  
 Votre classe, dérivée de [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) ou [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), ainsi que d’autres interfaces souhaitées prendre en charge sur l’objet.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComAggObject::CComAggObject](#ccomaggobject)|Constructeur.|  
|[CComAggObject :: ~ CComAggObject](#dtor)|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CComAggObject::AddRef](#addref)|Incrémente le décompte de références sur l’objet agrégée.|  
|[CComAggObject::CreateInstance](#createinstance)|Cette fonction statique vous permet de créer un nouveau **CComAggObject** `contained` **>** objet sans la surcharge de [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).|  
|[CComAggObject::FinalConstruct](#finalconstruct)|Effectue l’initialisation finale de `m_contained`.|  
|[CComAggObject::FinalRelease](#finalrelease)|Effectue une destruction finale de `m_contained`.|  
|[CComAggObject::QueryInterface](#queryinterface)|Récupère un pointeur vers l'interface demandée.|  
|[CComAggObject::Release](#release)|Décrémente le décompte de références sur l’objet agrégée.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComAggObject::m_contained](#m_contained)|Délégués `IUnknown` appels à inconnu externe.|  
  
## <a name="remarks"></a>Remarques  
 `CComAggObject`implémente [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) pour un objet. `CComAggObject`a son propre **IUnknown** interface, distinct de l’objet externe **IUnknown** interface et son propre décompte de références.  
  
 Pour plus d’informations sur l’agrégation, consultez l’article [notions de base des objets COM ATL](../../atl/fundamentals-of-atl-com-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComAggObject`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
##  <a name="addref"></a>CComAggObject::AddRef  
 Incrémente le décompte de références sur l’objet agrégée.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur qui peut être utile pour les tests de diagnostic ou de test.  
  
##  <a name="ccomaggobject"></a>CComAggObject::CComAggObject  
 Constructeur.  
  
```
CComAggObject(void* pv);
```  
  
### <a name="parameters"></a>Paramètres  
 `pv`  
 [in] Inconnu externe.  
  
### <a name="remarks"></a>Remarques  
 Initialise le `CComContainedObject` membre, [m_contained](#m_contained)et incrémente le nombre de verrous du module.  
  
 Le décrémente destructeur le module nombre de verrous.  
  
##  <a name="dtor"></a>CComAggObject :: ~ CComAggObject  
 Destructeur.  
  
```
~CComAggObject();
```  
  
### <a name="remarks"></a>Remarques  
 Libère toutes les ressources attribuées, les appels [FinalRelease](#finalrelease), et décrémente le module nombre de verrous.  
  
##  <a name="createinstance"></a>CComAggObject::CreateInstance  
 Cette fonction statique vous permet de créer un nouveau **CComAggObject** `contained` **>** objet sans la surcharge de [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).  
  
```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```  
  
### <a name="parameters"></a>Paramètres  
 `pp`  
 [out] Un pointeur vers un **CComAggObject\<***contenus* **>** pointeur. Si `CreateInstance` échoue, `pp` a la valeur **NULL**.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Remarques  
 L’objet retourné est un décompte de références de zéro, appelez `AddRef` immédiatement, puis utilisez **version** pour libérer la référence sur le pointeur d’objet lorsque vous avez terminé.  
  
 Si vous n’avez besoin d’imposent pas accès à l’objet, mais que vous souhaitez toujours créer un nouvel objet sans subir la surcharge de `CoCreateInstance`, utilisez [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) à la place.  
  
##  <a name="finalconstruct"></a>CComAggObject::FinalConstruct  
 Appelée au cours des dernières étapes de la construction d’objet, cette méthode effectue une initialisation finale sur le [m_contained](#m_contained) membre.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
##  <a name="finalrelease"></a>CComAggObject::FinalRelease  
 Appelé lors de la destruction d’objets, cette méthode libère le [m_contained](#m_contained) membre.  
  
```
void FinalRelease();
```  
  
##  <a name="m_contained"></a>CComAggObject::m_contained  
 A [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) objet dérivé de votre classe.  
  
```
CComContainedObject<contained> m_contained;
```  
  
### <a name="parameters"></a>Paramètres  
 `contained`  
 [in] Votre classe, dérivée de [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) ou [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), ainsi que d’autres interfaces souhaitées prendre en charge sur l’objet.  
  
### <a name="remarks"></a>Notes  
 Tous les **IUnknown** appelle via `m_contained` sont déléguées à inconnu externe.  
  
##  <a name="queryinterface"></a>CComAggObject::QueryInterface  
 Récupère un pointeur vers l'interface demandée.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```  
  
### <a name="parameters"></a>Paramètres  
 `iid`  
 [in] Identificateur de l’interface demandée.  
  
 `ppvObject`  
 [out] Un pointeur vers le pointeur d’interface identifié par `iid`. Si l’objet ne prend pas en charge cette interface, `ppvObject` a la valeur **NULL**.  
  
 `pp`  
 [out] Un pointeur vers le pointeur d’interface identifié par le type `Q`. Si l’objet ne prend pas en charge cette interface, `pp` a la valeur **NULL**.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Remarques  
 Si l’interface demandée est **IUnknown**, `QueryInterface` retourne un pointeur vers l’agrégées propre à l’objet **IUnknown** et incrémente le décompte de références. Sinon, cette méthode recherche l’interface via la `CComContainedObject` membre, [m_contained](#m_contained).  
  
##  <a name="release"></a>CComAggObject::Release  
 Décrémente le décompte de références sur l’objet agrégée.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Dans les versions debug, **version** retourne une valeur qui peut être utile pour les tests de diagnostic ou de test. Dans les versions non debug, **version** retourne toujours 0.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de CComObject](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject (classe)](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)   
 [DECLARE_ONLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_only_aggregatable)   
 [DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

