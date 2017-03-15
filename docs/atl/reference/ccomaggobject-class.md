---
title: Classe de CComAggObject | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CComAggObject<contained>
- ATL.CComAggObject
- ATL.CComAggObject<contained>
- CComAggObject
- ATL::CComAggObject
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 386ab09418c879c0de0d82d729a3de1b2e270016
ms.lasthandoff: 02/24/2017

---
# <a name="ccomaggobject-class"></a>CComAggObject (classe)
Cette classe implémente le [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) interface pour un objet. Par définition, un objet est contenu dans un objet externe. Le `CComAggObject` classe est semblable à la [CComObject classe](../../atl/reference/ccomobject-class.md), sauf qu’il expose une interface qui est directement accessible aux clients externes.  
  
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
|[CComAggObject::AddRef](#addref)|Incrémente le décompte de références sur l’objet agrégé.|  
|[CComAggObject::CreateInstance](#createinstance)|Cette fonction statique vous permet de créer un nouveau **CComAggObject** `contained` ** > ** objet sans avoir à [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).|  
|[CComAggObject::FinalConstruct](#finalconstruct)|Effectue une initialisation finale de `m_contained`.|  
|[CComAggObject::FinalRelease](#finalrelease)|Effectue la destruction finale de `m_contained`.|  
|[CComAggObject::QueryInterface](#queryinterface)|Récupère un pointeur vers l'interface demandée.|  
|[CComAggObject::Release](#release)|Décrémente le décompte de références sur l’objet agrégé.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComAggObject::m_contained](#m_contained)|Délégués `IUnknown` les appels vers l’inconnu extérieur.|  
  
## <a name="remarks"></a>Remarques  
 `CComAggObject`implémente [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) pour un objet. `CComAggObject`a son propre **IUnknown** interface, distinct de l’objet externe **IUnknown** interface et conserve son propre compte de référence.  
  
 Pour plus d’informations sur l’agrégation, consultez l’article [principes de base des objets COM ATL](../../atl/fundamentals-of-atl-com-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComAggObject`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
##  <a name="a-nameaddrefa--ccomaggobjectaddref"></a><a name="addref"></a>CComAggObject::AddRef  
 Incrémente le décompte de références sur l’objet agrégé.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur qui peut être utile pour les tests de diagnostic ou de test.  
  
##  <a name="a-nameccomaggobjecta--ccomaggobjectccomaggobject"></a><a name="ccomaggobject"></a>CComAggObject::CComAggObject  
 Constructeur.  
  
```
CComAggObject(void* pv);
```  
  
### <a name="parameters"></a>Paramètres  
 `pv`  
 [in] Inconnu externe.  
  
### <a name="remarks"></a>Notes  
 Initialise le `CComContainedObject` membre, [m_contained](#m_contained)et incrémente le nombre de verrous du module.  
  
 Le décrémente destructeur le module nombre de verrous.  
  
##  <a name="a-namedtora--ccomaggobjectccomaggobject"></a><a name="dtor"></a>CComAggObject :: ~ CComAggObject  
 Destructeur.  
  
```
~CComAggObject();
```  
  
### <a name="remarks"></a>Remarques  
 Libère toutes les ressources attribuées, les appels [FinalRelease](#finalrelease), et décrémente le module nombre de verrous.  
  
##  <a name="a-namecreateinstancea--ccomaggobjectcreateinstance"></a><a name="createinstance"></a>CComAggObject::CreateInstance  
 Cette fonction statique vous permet de créer un nouveau **CComAggObject** `contained` ** > ** objet sans avoir à [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).  
  
```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```  
  
### <a name="parameters"></a>Paramètres  
 `pp`  
 [out] Un pointeur vers un **CComAggObject\<***contenus* ** > ** pointeur. Si `CreateInstance` a échoué, `pp` a **NULL**.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Remarques  
 L’objet retourné est un décompte de références de zéro, appelez `AddRef` immédiatement, puis utilisez **version** pour libérer la référence sur le pointeur d’objet lorsque vous avez terminé.  
  
 Si vous ne pas besoin un accès direct à l’objet, mais que vous souhaitez toujours créer un nouvel objet sans avoir à `CoCreateInstance`, utilisez [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) à la place.  
  
##  <a name="a-namefinalconstructa--ccomaggobjectfinalconstruct"></a><a name="finalconstruct"></a>CComAggObject::FinalConstruct  
 Appelé pendant les dernières étapes de construction d’objets, cette méthode effectue une initialisation finale sur le [m_contained](#m_contained) membre.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
##  <a name="a-namefinalreleasea--ccomaggobjectfinalrelease"></a><a name="finalrelease"></a>CComAggObject::FinalRelease  
 Appelée pendant la destruction d’objets, cette méthode libère le [m_contained](#m_contained) membre.  
  
```
void FinalRelease();
```  
  
##  <a name="a-namemcontaineda--ccomaggobjectmcontained"></a><a name="m_contained"></a>CComAggObject::m_contained  
 A [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) objet dérivé votre classe.  
  
```
CComContainedObject<contained> m_contained;
```  
  
### <a name="parameters"></a>Paramètres  
 `contained`  
 [in] Votre classe, dérivée de [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) ou [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), ainsi que d’autres interfaces souhaitées prendre en charge sur l’objet.  
  
### <a name="remarks"></a>Remarques  
 Tous les **IUnknown** appelle via `m_contained` sont déléguées à l’inconnu extérieur.  
  
##  <a name="a-namequeryinterfacea--ccomaggobjectqueryinterface"></a><a name="queryinterface"></a>CComAggObject::QueryInterface  
 Récupère un pointeur vers l'interface demandée.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```  
  
### <a name="parameters"></a>Paramètres  
 `iid`  
 [in] L’identificateur de l’interface demandée.  
  
 `ppvObject`  
 [out] Un pointeur vers le pointeur d’interface identifié par `iid`. Si l’objet ne prend pas en charge cette interface, `ppvObject` a **NULL**.  
  
 `pp`  
 [out] Un pointeur vers le pointeur d’interface identifié par le type `Q`. Si l’objet ne prend pas en charge cette interface, `pp` a **NULL**.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Remarques  
 Si l’interface demandée est **IUnknown**, `QueryInterface` retourne un pointeur vers l’agrégées propre à l’objet **IUnknown** et incrémente le décompte de références. Sinon, cette méthode interroge l’interface via la `CComContainedObject` membre, [m_contained](#m_contained).  
  
##  <a name="a-namereleasea--ccomaggobjectrelease"></a><a name="release"></a>CComAggObject::Release  
 Décrémente le décompte de références sur l’objet agrégé.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Dans les versions debug, **version** retourne une valeur qui peut être utile pour les tests de diagnostic ou de test. Dans les versions non debug **version** retourne toujours 0.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de CComObject](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject (classe)](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE_AGGREGATABLE](http://msdn.microsoft.com/library/e7e568d7-04e0-4226-b5dc-224deed229ab)   
 [DECLARE_ONLY_AGGREGATABLE](http://msdn.microsoft.com/library/a54220df-4330-4e4d-b7fb-8b63dd62d337)   
 [DECLARE_NOT_AGGREGATABLE](http://msdn.microsoft.com/library/2a116c7c-bab8-4f2a-a9ad-03d7aba0f762)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

