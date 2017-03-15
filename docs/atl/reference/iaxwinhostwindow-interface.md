---
title: "Interface de l’interface IAxWinHostWindow | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAxWinHostWindow
dev_langs:
- C++
helpviewer_keywords:
- IAxWinHostWindow interface
ms.assetid: 9821c035-cd52-4c46-b58a-9278064f09b4
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
ms.openlocfilehash: 6e366e7e30e7b4080462fbc21c29b4ecdf0214ae
ms.lasthandoff: 02/24/2017

---
# <a name="iaxwinhostwindow-interface"></a>Interface de l’interface IAxWinHostWindow
Cette interface fournit des méthodes pour manipuler un contrôle et son objet ordinateur hôte.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```
interface IAxWinHostWindow : IUnknown
```  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[AttachControl](#attachcontrol)|Attache un contrôle existant à l’objet hôte.|  
|[CreateControl](#createcontrol)|Crée un contrôle et l’attache à l’objet hôte.|  
|[CreateControlEx](#createcontrolex)|Crée un contrôle et l’attache à l’objet hôte éventuellement configure un gestionnaire d’événements.|  
|[QueryControl](#querycontrol)|Retourne un pointeur d’interface pour le contrôle hébergé.|  
|[SetExternalDispatch](#setexternaldispatch)|Définit l’externe `IDispatch` interface.|  
|[SetExternalUIHandler](#setexternaluihandler)|Définit l’externe `IDocHostUIHandlerDispatch` interface.|  
  
## <a name="remarks"></a>Remarques  
 Cette interface est exposée par le contrôle ActiveX d’ATL qui héberge les objets. Appelez les méthodes sur cette interface pour créer et/ou attacher un contrôle à l’objet ordinateur hôte, pour obtenir une interface à partir d’un contrôle hébergé, ou pour définir la dispinterface externe ou un gestionnaire d’interface utilisateur pour une utilisation lors de l’hébergement de navigateur Web.  
  
## <a name="requirements"></a>Spécifications  
 La définition de cette interface est disponible en tant que fichier IDL ou C++, comme indiqué ci-dessous.  
  
|Type de définition|Fichier|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|ATLIFace.h (également inclus dans ATLBase.h)|  
  
##  <a name="a-nameattachcontrola--iaxwinhostwindowattachcontrol"></a><a name="attachcontrol"></a>IAxWinHostWindow::AttachControl  
 Attache un contrôle existant (et précédemment initialisé) à l’objet ordinateur hôte à l’aide de la fenêtre identifiée par `hWnd`.  
  
```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 *pUnkControl*  
 [in] Un pointeur vers le **IUnknown** interface du contrôle à joindre à l’objet hôte.  
  
 `hWnd`  
 [in] Handle vers la fenêtre à utiliser pour l’hébergement.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
##  <a name="a-namecreatecontrola--iaxwinhostwindowcreatecontrol"></a><a name="createcontrol"></a>IAxWinHostWindow::CreateControl  
 Crée un contrôle, il initialise et héberge ce dernier dans la fenêtre identifiée par `hWnd`.  
  
```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpTricsData`  
 [in] Une chaîne qui identifie le contrôle à créer. Peut être un CLSID (doit inclure les accolades), un ProgID, une URL ou un code HTML brut (préfixé par **MSHTML :**).  
  
 `hWnd`  
 [in] Handle vers la fenêtre à utiliser pour l’hébergement.  
  
 `pStream`  
 [in] Un pointeur d’interface pour un flux contenant les données d’initialisation pour le contrôle. Peut être **NULL**.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Remarques  
 Cette fenêtre est sous-classé par l’objet hôte qui expose cette interface afin que les messages peuvent être reflétées sur le contrôle et autres fonctionnalités de conteneur fonctionneront.  
  
 Appel de cette méthode équivaut à appeler la méthode [IAxWinHostWindow::CreateControlEx](#createcontrolex).  
  
 Pour créer un contrôle ActiveX sous licence, consultez [IAxWinHostWindowLic::CreateControlLic](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex).  
  
##  <a name="a-namecreatecontrolexa--iaxwinhostwindowcreatecontrolex"></a><a name="createcontrolex"></a>IAxWinHostWindow::CreateControlEx  
 Crée un contrôle ActiveX, il initialise et héberge ce dernier dans la fenêtre spécifiée, comme [IAxWinHostWindow::CreateControl](#createcontrol).  
  
```
STDMETHOD(CreateControlEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpTricsData`  
 [in] Une chaîne qui identifie le contrôle à créer. Peut être un CLSID (doit inclure les accolades), un ProgID, une URL ou un code HTML brut (avec le préfixe **MSHTML :**).  
  
 `hWnd`  
 [in] Handle vers la fenêtre à utiliser pour l’hébergement.  
  
 `pStream`  
 [in] Un pointeur d’interface pour un flux contenant les données d’initialisation pour le contrôle. Peut être **NULL**.  
  
 `ppUnk`  
 [out] L’adresse d’un pointeur qui va recevoir la **IUnknown** interface du contrôle créé. Peut être **NULL**.  
  
 *riidAdvise*  
 [in] L’identificateur d’interface d’une interface sortante sur l’objet de relation contenant-contenu. Peut être **IID_NULL**.  
  
 *punkAdvise*  
 [in] Un pointeur vers le **IUnknown** interface de l’objet de récepteur d’être connectés au point de connexion de l’objet de relation contenant-contenu spécifié par `iidSink`.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Remarques  
 Contrairement à la `CreateControl` méthode `CreateControlEx` vous permet également de recevoir un pointeur d’interface au contrôle nouvellement créé et configuré un récepteur d’événements pour recevoir des événements déclenchés par le contrôle.  
  
 Pour créer un contrôle ActiveX sous licence, consultez [IAxWinHostWindowLic::CreateControlLicEx](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex).  
  
##  <a name="a-namequerycontrola--iaxwinhostwindowquerycontrol"></a><a name="querycontrol"></a>IAxWinHostWindow::QueryControl  
 Retourne le pointeur d’interface spécifié fourni par le contrôle hébergé.  
  
```
STDMETHOD(QueryControl)(
    REFIID riid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Paramètres  
 `riid`  
 [in] L’ID d’une interface sur le contrôle demandé.  
  
 `ppvObject`  
 [out] L’adresse d’un pointeur qui reçoit l’interface spécifiée du contrôle créé.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
##  <a name="a-namesetexternaldispatcha--iaxwinhostwindowsetexternaldispatch"></a><a name="setexternaldispatch"></a>IAxWinHostWindow::SetExternalDispatch  
 Définit la dispinterface externe, qui est disponible pour les contrôles contenus dans le [IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) (méthode).  
  
```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDisp`  
 [in] Un pointeur vers un `IDispatch` interface.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
##  <a name="a-namesetexternaluihandlera--iaxwinhostwindowsetexternaluihandler"></a><a name="setexternaluihandler"></a>IAxWinHostWindow::SetExternalUIHandler  
 Appelez cette fonction pour définir externe [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) de l’interface pour le `CAxWindow` objet.  
  
```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDisp`  
 [in] Un pointeur vers un **IDocHostUIHandlerDispatch** interface.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est utilisée par les contrôles (par exemple, le contrôle de navigateur Web) qui interroge le site de l’ordinateur hôte pour le `IDocHostUIHandlerDispatch` interface.  
  
## <a name="see-also"></a>Voir aussi  
 [Interface de IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)   
 [CAxWindow::QueryHost](../../atl/reference/caxwindow-class.md#queryhost)   
 [AtlAxGetHost](http://msdn.microsoft.com/library/ad1f4f16-608d-4e96-8d30-04d4ca906a7b)










