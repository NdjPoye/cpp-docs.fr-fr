---
title: Classe de CComClassFactoryAutoThread | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread::CreateInstance
- ATLCOM/ATL::CComClassFactoryAutoThread::LockServer
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactoryAutoThread class
ms.assetid: 22008042-533f-4dd9-bf7e-191ee571f9a1
caps.latest.revision: 21
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
ms.openlocfilehash: fcc5671fc136b061bf3e8109999ac91d302d3d3b
ms.lasthandoff: 02/24/2017

---
# <a name="ccomclassfactoryautothread-class"></a>CComClassFactoryAutoThread (classe)
Cette classe implémente le [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) de l’interface et permet aux objets d’être créés dans des compartiments à plusieurs.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CComClassFactoryAutoThread 
   : public IClassFactory, 
     public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CComClassFactoryAutoThread::CreateInstance](#createinstance)|Crée un objet du CLSID spécifié.|  
|[CComClassFactoryAutoThread::LockServer](#lockserver)|Verrouille la fabrique de classe en mémoire.|  
  
## <a name="remarks"></a>Remarques  
 `CComClassFactoryAutoThread`est semblable à [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), mais permet aux objets d’être créés dans des compartiments à plusieurs. Pour tirer parti de cette prise en charge, dérivez votre module EXE à partir de [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
 Objets ATL acquièrent normalement une fabrique de classe en dérivant de [CComCoClass](../../atl/reference/ccomcoclass-class.md). Cette classe inclut la macro [DECLARE_CLASSFACTORY](http://msdn.microsoft.com/library/51a6b925-07c0-4d3a-9174-0b8c808975e4), qui déclare [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) en tant que la fabrique de classe par défaut. Pour utiliser `CComClassFactoryAutoThread`, spécifiez la [DECLARE_CLASSFACTORY_AUTO_THREAD](http://msdn.microsoft.com/library/19d7105e-03e8-4412-9f5e-5384c8a5e18f) macro dans la définition de classe de votre objet. Exemple :  
  
 [!code-cpp[NVC_ATL_COM&#9;](../../atl/codesnippet/cpp/ccomclassfactoryautothread-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 `CComClassFactoryAutoThread`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
##  <a name="createinstance"></a>CComClassFactoryAutoThread::CreateInstance  
 Crée un objet du CLSID spécifié et récupère un pointeur d’interface vers cet objet.  
  
```
STDMETHODIMP CreateInstance(
    LPUNKNOWN pUnkOuter,
    REFIID riid,
    void** ppvObj);
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
 Si votre module dérive [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), `CreateInstance` sélectionne tout d’abord créer l’objet dans le compartiment associé à un thread.  
  
##  <a name="lockserver"></a>CComClassFactoryAutoThread::LockServer  
 Incrémente et décrémente le module nombre de verrous en appelant **_Module::Lock** et **_Module::Unlock**, respectivement.  
  
```
STDMETHODIMP LockServer(BOOL fLock);
```  
  
### <a name="parameters"></a>Paramètres  
 `fLock`  
 [in] Si **TRUE**, le nombre de verrous est incrémenté ; sinon, le nombre de verrous est décrémenté.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Remarques  
 Lorsque vous utilisez `CComClassFactoryAutoThread`, **_Module** fait généralement référence à l’instance globale de [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
 L’appel `LockServer` permet à un client à maintenir une fabrique de classe afin que plusieurs objets peuvent être rapidement créés.  
  
## <a name="see-also"></a>Voir aussi  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [CComClassFactory2 (classe)](../../atl/reference/ccomclassfactory2-class.md)   
 [CComClassFactorySingleton (classe)](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [CComObjectRootEx (classe)](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

