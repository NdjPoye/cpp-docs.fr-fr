---
title: Classe de CComTearOffObject | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComTearOffObject
- ATLCOM/ATL::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::AddRef
- ATLCOM/ATL::CComTearOffObject::QueryInterface
- ATLCOM/ATL::CComTearOffObject::Release
- ATLCOM/ATL::CComTearOffObjectBase
- ATLCOM/ATL::m_pOwner
dev_langs:
- C++
helpviewer_keywords:
- tear-off interfaces, ATL
- tear-off interfaces
- CComTearOffObject class
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
caps.latest.revision: 20
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 3e8e997f26df1adca8050bd4d967a38297685831
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="ccomtearoffobject-class"></a>CComTearOffObject (classe)
Cette classe implémente une interface détachables.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class Base>
class CComTearOffObject : public Base
```  
  
#### <a name="parameters"></a>Paramètres  
 `Base`  
 Votre classe détachables, dérivée de `CComTearOffObjectBase` et les interfaces que votre objet détachable pour prendre en charge.  
  
 ATL implémente ses interfaces détachables en deux phases : la `CComTearOffObjectBase` méthodes gèrent le décompte de références et `QueryInterface`, tandis que `CComTearOffObject` implémente [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509).  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComTearOffObject::CComTearOffObject](#ccomtearoffobject)|Constructeur.|  
|[CComTearOffObject :: ~ CComTearOffObject](#dtor)|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CComTearOffObject::AddRef](#addref)|Incrémente le décompte de références pour un `CComTearOffObject` objet.|  
|[CComTearOffObject::QueryInterface](#queryinterface)|Retourne un pointeur vers l’interface demandée sur votre classe détachable ou la classe propriétaire.|  
|[CComTearOffObject::Release](#release)|Décrémente le décompte de références pour un `CComTearOffObject` de l’objet et détruit.|  
  
### <a name="ccomtearoffobjectbase-methods"></a>Méthodes CComTearOffObjectBase  
  
|||  
|-|-|  
|[CComTearOffObjectBase](#ccomtearoffobjectbase)|Constructeur.|  
  
### <a name="ccomtearoffobjectbase-data-members"></a>Membres de données de CComTearOffObjectBase  
  
|||  
|-|-|  
|[m_pOwner](#m_powner)|Un pointeur vers un `CComObject` dérivé de la classe propriétaire.|  
  
## <a name="remarks"></a>Notes  
 `CComTearOffObject`implémente une interface détachable comme un objet distinct est instancié uniquement lorsque cette interface est recherchée. Le volant est supprimé lorsque son décompte de références est égal à zéro. En général, vous générez une interface détachable pour une interface qui est rarement utilisée, car à l’aide un détachables enregistre un pointeur vtable dans toutes les instances de votre objet principal.  
  
 Vous devez dériver de la classe qui implémente la détacher de `CComTearOffObjectBase` et à partir de quelle que soit l’interfaces votre objet détachable pour prendre en charge. `CComTearOffObjectBase`mise en modèle sur la classe propriétaire et le modèle de thread. La classe propriétaire est la classe de l’objet pour lequel un détachable est implémentée. Si vous ne spécifiez pas un modèle de thread, le modèle de thread par défaut est utilisé.  
  
 Vous devez créer un mappage COM pour votre classe détachables. ATL instancie le détacher, créera **CComTearOffObject\<CYourTearOffClass >** ou **CComCachedTearOffObject\<CYourTearOffClass >**.  
  
 Par exemple, dans l’exemple BEEPER, le `CBeeper2` classe est la classe détachable et `CBeeper` classe est la classe propriétaire :  
  
 [!code-cpp[NVC_ATL_COM&#43;](../../atl/codesnippet/cpp/ccomtearoffobject-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `Base`  
  
 `CComTearOffObject`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
##  <a name="addref"></a>CComTearOffObject::AddRef  
 Incrémente le décompte de références de le `CComTearOffObject` l’objet d’une unité.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur qui peut être utile pour les tests de diagnostic et de test.  
  
##  <a name="ccomtearoffobject"></a>CComTearOffObject::CComTearOffObject  
 Constructeur.  
  
```
CComTearOffObject(void* pv);
```  
  
### <a name="parameters"></a>Paramètres  
 `pv`  
 [in] Pointeur qui va être converti en un pointeur vers un **CComObject\<propriétaire >** objet.  
  
### <a name="remarks"></a>Notes  
 Incrémente le décompte de références du propriétaire d’une unité.  
  
##  <a name="dtor"></a>CComTearOffObject :: ~ CComTearOffObject  
 Destructeur.  
  
```
~CComTearOffObject();
```  
  
### <a name="remarks"></a>Notes  
 Libère toutes les ressources attribuées, les appels FinalRelease et décrémente le module de verrouillage de compte.  
  
##  <a name="ccomtearoffobjectbase"></a>CComTearOffObject::CComTearOffObjectBase  
 Constructeur.  
  
```
CComTearOffObjectBase();
```  
  
### <a name="remarks"></a>Remarques  
 Initialise le [m_pOwner](#m_powner) membre **NULL**.  
  
##  <a name="m_powner"></a>CComTearOffObject::m_pOwner  
 Un pointeur vers un [CComObject](../../atl/reference/ccomobject-class.md) objet dérivé *propriétaire*.  
  
```
CComObject<Owner>* m_pOwner;
```  
  
### <a name="parameters"></a>Paramètres  
 *Propriétaire*  
 [in] La classe pour laquelle un détachable est implémentée.  
  
### <a name="remarks"></a>Remarques  
 Le pointeur est initialisé à **NULL** pendant la construction.  
  
##  <a name="queryinterface"></a>CComTearOffObject::QueryInterface  
 Récupère un pointeur vers l'interface demandée.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Paramètres  
 `iid`  
 [in] L’IID de l’interface demandée.  
  
 `ppvObject`  
 [out] Un pointeur vers le pointeur d’interface identifié par `iid`, ou **NULL** si l’interface est introuvable.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Remarques  
 Interroge d’abord les interfaces sur votre classe détachables. Si l’interface n’est pas visible, les requêtes pour l’interface sur l’objet propriétaire. Si l’interface demandée est **IUnknown**, retourne le **IUnknown** du propriétaire.  
  
##  <a name="release"></a>CComTearOffObject::Release  
 Décrémente le décompte de références d’une unité et, si le décompte de références est égal à zéro, supprime la `CComTearOffObject`.  
  
```
STDMETHOD_ULONG Release();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Dans les versions non debug retourne toujours zéro. Dans les versions debug, retourne une valeur qui peut être utile pour les tests de diagnostic ou de test.  
  
## <a name="see-also"></a>Voir aussi  
 [CComCachedTearOffObject (classe)](../../atl/reference/ccomcachedtearoffobject-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

