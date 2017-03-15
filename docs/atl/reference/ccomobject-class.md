---
title: Classe de CComObject | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComObject<Base>
- ATL::CComObject
- ATL::CComObject<Base>
- ATL.CComObject
- CComObject
dev_langs:
- C++
helpviewer_keywords:
- CComObject class
ms.assetid: e2b6433b-6349-4749-b4bc-acbd7a22c8b0
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5f752b96d4a722fbddfcc9e5be3a82b8b12a86a1
ms.lasthandoff: 02/24/2017

---
# <a name="ccomobject-class"></a>Classe de CComObject
Cette classe implémente **IUnknown** pour un objet non regroupées en agrégats.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class Base>  
class CComObject : public Base
```  
  
#### <a name="parameters"></a>Paramètres  
 `Base`  
 Votre classe, dérivée de [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) ou [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), ainsi que d’autres interfaces souhaitées prendre en charge sur l’objet.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComObject::CComObject](#ccomobject)|Constructeur.|  
|[CComObject :: ~ CComObject](#dtor)|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CComObject::AddRef](#addref)|Incrémente le décompte de références sur l’objet.|  
|[CComObject::CreateInstance](#createinstance)|(Statique) Crée un objet `CComObject` objet.|  
|[CComObject::QueryInterface](#queryinterface)|Récupère un pointeur vers l'interface demandée.|  
|[CComObject::Release](#release)|Décrémente le décompte de références sur l’objet.|  
  
## <a name="remarks"></a>Remarques  
 `CComObject`implémente [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) pour un objet non regroupées en agrégats. Toutefois, les appels à `QueryInterface`, `AddRef`, et **version** sont déléguées à `CComObjectRootEx`.  
  
 Pour plus d’informations sur l’utilisation de `CComObject`, consultez l’article [principes de base des objets COM ATL](../../atl/fundamentals-of-atl-com-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `Base`  
  
 `CComObject`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
##  <a name="a-nameaddrefa--ccomobjectaddref"></a><a name="addref"></a>CComObject::AddRef  
 Incrémente le décompte de références sur l’objet.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Cette fonction retourne le nouveau nombre incrémenté de référence sur l’objet. Cette valeur peut être utile de diagnostic ou de test.  
  
##  <a name="a-nameccomobjecta--ccomobjectccomobject"></a><a name="ccomobject"></a>CComObject::CComObject  
 Le constructeur incrémente le nombre de verrous du module.  
  
```
CComObject(void* = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 **void\***  
 [in] Ce paramètre sans nom n’est pas utilisé. Il existe pour la symétrie avec d’autres **CCom***XXX*`Object`*XXX* constructeurs.  
  
### <a name="remarks"></a>Remarques  
 Le décrémente destructeur il.  
  
 Si un `CComObject`-objet dérivé est construit correctement à l’aide de la **nouveau** opérateur, le décompte de références initial est 0. Pour définir le nombre de références à la valeur appropriée (1), effectuez un appel à la [AddRef](#addref) (fonction).  
  
##  <a name="a-namedtora--ccomobjectccomobject"></a><a name="dtor"></a>CComObject :: ~ CComObject  
 Destructeur.  
  
```
CComObject();
```  
  
### <a name="remarks"></a>Remarques  
 Libère toutes les ressources attribuées, les appels [FinalRelease](ccomobjectrootex-class.md#finalrelease), et décrémente le module nombre de verrous.  

  
##  <a name="a-namecreateinstancea--ccomobjectcreateinstance"></a><a name="createinstance"></a>CComObject::CreateInstance  
 Cette fonction statique vous permet de créer un nouveau **CComObject** `Base` ** > ** objet, sans avoir à [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).  
  
```
static HRESULT WINAPI CreateInstance(CComObject<Base>** pp);
```  
  
### <a name="parameters"></a>Paramètres  
 `pp`  
 [out] Un pointeur vers un **CComObject** `Base` ** > ** pointeur. Si `CreateInstance` a échoué, `pp` a **NULL**.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Remarques  
 L’objet retourné est un décompte de références de zéro, appelez `AddRef` immédiatement, puis utilisez **version** pour libérer la référence sur le pointeur d’objet lorsque vous avez terminé.  
  
 Si vous ne pas besoin un accès direct à l’objet, mais que vous souhaitez toujours créer un nouvel objet sans avoir à `CoCreateInstance`, utilisez [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) à la place.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_COM&#38;](../../atl/codesnippet/cpp/ccomobject-class_1.h)]  
  
 [!code-cpp[NVC_ATL_COM N °&39;](../../atl/codesnippet/cpp/ccomobject-class_2.cpp)]  
  
##  <a name="a-namequeryinterfacea--ccomobjectqueryinterface"></a><a name="queryinterface"></a>CComObject::QueryInterface  
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
  
##  <a name="a-namereleasea--ccomobjectrelease"></a><a name="release"></a>CComObject::Release  
 Décrémente le décompte de références sur l’objet.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Cette fonction retourne le nombre de références décrémenté nouveau sur l’objet. Dans les versions debug, la valeur de retour peut être utile pour les tests de diagnostic ou de test. Dans les versions non debug **version** retourne toujours 0.  
  
## <a name="see-also"></a>Voir aussi  
 [CComAggObject (classe)](../../atl/reference/ccomaggobject-class.md)   
 [CComPolyObject (classe)](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE_AGGREGATABLE](http://msdn.microsoft.com/library/e7e568d7-04e0-4226-b5dc-224deed229ab)   
 [DECLARE_NOT_AGGREGATABLE](http://msdn.microsoft.com/library/2a116c7c-bab8-4f2a-a9ad-03d7aba0f762)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

