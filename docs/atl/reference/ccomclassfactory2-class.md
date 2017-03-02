---
title: Classe de CComClassFactory2 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CComClassFactory2<license>
- CComClassFactory2
- ATL.CComClassFactory2<license>
- ATL::CComClassFactory2
- ATL.CComClassFactory2
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactory2 class
ms.assetid: 19b66fd6-b9ed-47a0-822c-8132184f5a3e
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
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 3787214d5479e1cd57295c9c25335e87651a16bb
ms.lasthandoff: 02/24/2017

---
# <a name="ccomclassfactory2-class"></a>CComClassFactory2 (classe)
Cette classe implémente le [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) interface.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class license>  
class CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```  
  
#### <a name="parameters"></a>Paramètres  
 *licence*  
 Une classe qui implémente les fonctions statiques suivantes :  
  
- **static BOOL VerifyLicenseKey (BSTR** `bstr` **) ;**  
  
- **static BOOL GetLicenseKey (DWORD** `dwReserved` **, BSTR\* ** `pBstr` **) ;**  
  
- **statique (de) BOOL IsLicenseValid ;**  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CComClassFactory2::CreateInstance](#createinstance)|Crée un objet du CLSID spécifié.|  
|[CComClassFactory2::CreateInstanceLic](#createinstancelic)|Une clé de licence, crée un objet du CLSID spécifié.|  
|[CComClassFactory2::GetLicInfo](#getlicinfo)|Récupère des informations décrivant les fonctionnalités de gestion des licences de la fabrique de classe.|  
|[CComClassFactory2::LockServer](#lockserver)|Verrouille la fabrique de classe en mémoire.|  
|[CComClassFactory2::RequestLicKey](#requestlickey)|Crée et retourne une clé de licence.|  
  
## <a name="remarks"></a>Remarques  
 `CComClassFactory2`implémente le [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) interface, qui est une extension de [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364). **IClassFactory2** contrôles création une licence par le biais d’un objet. Une fabrique de classe s’exécutant sur un ordinateur sous licence peut fournir une clé de licence d’exécution. Cette clé de licence permet à une application instancier des objets lorsqu’une licence complète ordinateur n’existe pas.  
  
 Objets ATL acquièrent normalement une fabrique de classe en dérivant de [CComCoClass](../../atl/reference/ccomcoclass-class.md). Cette classe inclut la macro [DECLARE_CLASSFACTORY](http://msdn.microsoft.com/library/51a6b925-07c0-4d3a-9174-0b8c808975e4), qui déclare [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) en tant que la fabrique de classe par défaut. Pour utiliser `CComClassFactory2`, spécifiez la [macro DECLARE_CLASSFACTORY2](http://msdn.microsoft.com/library/38a6c969-7297-4bb1-9ba6-1fe2d355b285) macro dans la définition de classe de votre objet. Exemple :  
  
 [!code-cpp[NVC_ATL_COM N °&2;](../../atl/codesnippet/cpp/ccomclassfactory2-class_1.h)]  
  
 **CMyLicense**, le paramètre de modèle `CComClassFactory2`, doivent implémenter les fonctions statiques `VerifyLicenseKey`, `GetLicenseKey`, et `IsLicenseValid`. Voici un exemple d’une classe simple de licence :  
  
 [!code-cpp[NVC_ATL_COM N °&3;](../../atl/codesnippet/cpp/ccomclassfactory2-class_2.h)]  
  
 `CComClassFactory2`dérive les deux **CComClassFactory2Base** et *licence*. **CComClassFactory2Base**, à son tour, dérive de **IClassFactory2** et **CComObjectRootEx\< CComGlobalsThreadModel >**.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `CComObjectRootBase`  
  
 `license`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory2`  
  
 `CComClassFactory2`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
##  <a name="a-namecreateinstancea--ccomclassfactory2createinstance"></a><a name="createinstance"></a>CComClassFactory2::CreateInstance  
 Crée un objet du CLSID spécifié et récupère un pointeur d’interface vers cet objet.  
  
```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```  
  
### <a name="parameters"></a>Paramètres  
 `pUnkOuter`  
 [in] Si l’objet est créé dans le cadre d’un agrégat, puis `pUnkOuter` doit être inconnu externe. Dans le cas contraire, `pUnkOuter` doit être **NULL**.  
  
 `riid`  
 [in] L’IID de l’interface demandée. Si `pUnkOuter` est non - **NULL**, `riid` doit être **IID_IUnknown**.  
  
 `ppvObj`  
 [out] Un pointeur vers le pointeur d’interface identifié par `riid`. Si l’objet ne prend pas en charge cette interface, `ppvObj` a **NULL**.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Notes  
 Nécessite que l’ordinateur pour être entièrement sous licence. Si une licence de l’ordinateur complet n’existe pas, appelez [CreateInstanceLic](#createinstancelic).  
  
##  <a name="a-namecreateinstancelica--ccomclassfactory2createinstancelic"></a><a name="createinstancelic"></a>CComClassFactory2::CreateInstanceLic  
 Semblable à [CreateInstance](#createinstance), sauf que `CreateInstanceLic` requiert une clé de licence.  
  
```
STDMETHOD(CreateInstanceLic)(
    IUnknown* pUnkOuter,
    IUnknown* /* pUnkReserved
 */,
    REFIID riid,
    BSTR bstrKey,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Paramètres  
 `pUnkOuter`  
 [in] Si l’objet est créé dans le cadre d’un agrégat, puis `pUnkOuter` doit être inconnu externe. Dans le cas contraire, `pUnkOuter` doit être **NULL**.  
  
 *pUnkReserved*  
 [in] Non utilisé. Doit être **NULL**.  
  
 `riid`  
 [in] L’IID de l’interface demandée. Si `pUnkOuter` est non - **NULL**, `riid` doit être **IID_IUnknown**.  
  
 `bstrKey`  
 [in] La clé de licence de l’exécution est obtenu à partir d’un appel à `RequestLicKey`. Cette clé est obligatoire pour créer l’objet.  
  
 `ppvObject`  
 [out] Un pointeur vers le pointeur d’interface spécifié par `riid`. Si l’objet ne prend pas en charge cette interface, `ppvObject` a **NULL**.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Notes  
 Vous pouvez obtenir une clé de licence à l’aide [RequestLicKey](#requestlickey). Pour créer un objet sur un ordinateur sans licence, vous devez appeler `CreateInstanceLic`.  
  
##  <a name="a-namegetlicinfoa--ccomclassfactory2getlicinfo"></a><a name="getlicinfo"></a>CComClassFactory2::GetLicInfo  
 Remplit un [LICINFO](http://msdn.microsoft.com/library/windows/desktop/ms690590) structure avec des informations qui décrivent la fabrique de classe de licences de capacités.  
  
```
STDMETHOD(GetLicInfo)(LICINFO* pLicInfo);
```  
  
### <a name="parameters"></a>Paramètres  
 *pLicInfo*  
 [out] Pointeur vers un **LICINFO** structure.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Remarques  
 Le `fRuntimeKeyAvail` membre de cette structure indique si, étant donné une clé de licence, la fabrique de classe permet aux objets d’être créé sur un ordinateur sans licence. Le *fLicVerified* membre indique l’existence d’une licence de l’ordinateur complet.  
  
##  <a name="a-namelockservera--ccomclassfactory2lockserver"></a><a name="lockserver"></a>CComClassFactory2::LockServer  
 Incrémente et décrémente le module nombre de verrous en appelant **_Module::Lock** et **_Module::Unlock**, respectivement.  
  
```
STDMETHOD(LockServer)(BOOL fLock);
```  
  
### <a name="parameters"></a>Paramètres  
 `fLock`  
 [in] Si **TRUE**, le nombre de verrous est incrémenté ; sinon, le nombre de verrous est décrémenté.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Remarques  
 **_Module** fait référence à l’instance globale de [CComModule](../../atl/reference/ccommodule-class.md) ou d’une classe dérivée.  
  
 L’appel `LockServer` permet à un client à maintenir une fabrique de classe afin que plusieurs objets peuvent être rapidement créés.  
  
##  <a name="a-namerequestlickeya--ccomclassfactory2requestlickey"></a><a name="requestlickey"></a>CComClassFactory2::RequestLicKey  
 Crée et retourne une clé de licence, à condition que la `fRuntimeKeyAvail` membre de la [LICINFO](http://msdn.microsoft.com/library/windows/desktop/ms690590) structure est **TRUE**.  
  
```
STDMETHOD(RequestLicKey)(DWORD dwReserved, BSTR* pbstrKey);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwReserved`  
 [in] Non utilisé. Doit être égal à zéro.  
  
 `pbstrKey`  
 [out] Pointeur vers la clé de licence.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Notes  
 Une clé de licence est requise pour appeler la méthode [CreateInstanceLic](#createinstancelic) pour créer un objet sur un ordinateur sans licence. Si `fRuntimeKeyAvail` est **FALSE**, puis objets ne peuvent être créés sur un ordinateur sous licence complète.  
  
 Appelez [GetLicInfo](#getlicinfo) pour récupérer la valeur de `fRuntimeKeyAvail`.  
  
## <a name="see-also"></a>Voir aussi  
 [CComClassFactoryAutoThread (classe)](../../atl/reference/ccomclassfactoryautothread-class.md)   
 [CComClassFactorySingleton (classe)](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [CComObjectRootEx (classe)](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

