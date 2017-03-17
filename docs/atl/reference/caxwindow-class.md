---
title: "Classe d’objet CAxWindow | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAxWindow
- ATLWIN/ATL::CAxWindow
- ATLWIN/ATL::AttachControl
- ATLWIN/ATL::CAxWindow
- ATLWIN/ATL::CreateControl
- ATLWIN/ATL::CreateControlEx
- ATLWIN/ATL::GetWndClassName
- ATLWIN/ATL::QueryControl
- ATLWIN/ATL::QueryHost
- ATLWIN/ATL::SetExternalDispatch
- ATLWIN/ATL::SetExternalUIHandler
dev_langs:
- C++
helpviewer_keywords:
- CAxWindow class
- ATL, hosting ActiveX controls
ms.assetid: 85e79261-43e4-4770-bde0-1ff87f222b0f
caps.latest.revision: 24
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
ms.openlocfilehash: 202c68fa4044a7c7a6c47c52b8095c5e7227b56d
ms.lasthandoff: 02/24/2017

---
# <a name="caxwindow-class"></a>Classe d’objet CAxWindow
Cette classe fournit des méthodes pour manipuler une fenêtre qui héberge un contrôle ActiveX.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CAxWindow : public CWindow
```  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[AttachControl](#attachcontrol)|Attache un contrôle ActiveX pour le `CAxWindow` objet.|  
|[Objet CAxWindow](#caxwindow)|Construit un objet `CAxWindow`.|  
|[CreateControl](#createcontrol)|Crée un contrôle ActiveX, il initialise et héberge ce dernier dans la `CAxWindow` fenêtre.|  
|[CreateControlEx](#createcontrolex)|Crée un contrôle ActiveX et récupère un pointeur d’interface (ou pointeurs) du contrôle.|  
|[GetWndClassName](#getwndclassname)|(Statique) Récupère le nom de la classe prédéfinie de la `CAxWindow` objet.|  
|[QueryControl](#querycontrol)|Récupère le **IUnknown** du contrôle ActiveX hébergé.|  
|[QueryHost](#queryhost)|Récupère le **IUnknown** le pointeur de la `CAxWindow` objet.|  
|[SetExternalDispatch](#setexternaldispatch)|Définit l’interface de dispatch externe utilisée par le `CAxWindow` objet.|  
|[SetExternalUIHandler](#setexternaluihandler)|Définit l’externe **IDocHostUIHandler** interface utilisée par le `CAxWindow` objet.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[opérateur =](#operator_eq)|Assigne une **HWND** à un fichier **Caxwindow2** objet.|  
  
## <a name="remarks"></a>Remarques  
 Cette classe fournit des méthodes pour manipuler une fenêtre qui héberge un contrôle ActiveX. L’hébergement est fournie par « **AtlAxWin80 »**, qui est encapsulé par `CAxWindow`.  
  
 Classe `CAxWindow` est implémentée comme une spécialisation de la `CAxWindowT` classe. Cette spécialisation est déclarée en tant que :  
  
 `typedef CAxWindowT<CWindow> CAxWindow;`  
  
 Si vous devez modifier la classe de base, vous pouvez utiliser `CAxWindowT` et spécifiez la nouvelle classe de base comme un argument template.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h  
  
##  <a name="attachcontrol"></a>CAxWindow::AttachControl  
 Crée un objet hôte s’il n’est pas déjà présent et joint le contrôle spécifié à l’hôte.  
  
```
HRESULT AttachControl(
    IUnknown* pControl,
    IUnknown** ppUnkContainer);
```  
  
### <a name="parameters"></a>Paramètres  
 `pControl`  
 [in] Un pointeur vers le **IUnknown** du contrôle.  
  
 `ppUnkContainer`  
 [out] Un pointeur vers le **IUnknown** de l’hôte (le **AxWin** objet).  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Remarques  
 L’objet de contrôle qui est attaché doit être correctement initialisée avant d’appeler `AttachControl`.  
  
##  <a name="caxwindow"></a>CAxWindow::CAxWindow  
 Construit un `CAxWindow` à l’aide d’un handle d’objet fenêtre existante.  
  
```
CAxWindow(HWND hWnd = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `hWnd`  
 Handle vers un objet existant de la fenêtre.  
  
##  <a name="createcontrol"></a>CAxWindow::CreateControl  
 Crée un contrôle ActiveX, puis initialise et héberge ce dernier dans la fenêtre spécifiée.  
  
```
HRESULT CreateControl(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL);

HRESULT CreateControl(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszName`  
 Pointeur vers une chaîne pour créer le contrôle. Doit être mis en forme dans une des manières suivantes :  
  
-   Un ProgID tels que « MSCAL. Calendar.7 »  
  
-   CLSID tel que « {8E27C92B-1264-101C-8A2F-040224009C02} »  
  
-   Une URL telle que « http://www.microsoft.com »  
  
-   Une référence à un document actif comme « file://\\\Documents\MyDoc.doc »  
  
-   Un fragment de code HTML comme « MSHTML :\<HTML >\<corps > il s’agit d’une ligne de texte\</corps >\</HTML > »  
  
    > [!NOTE]
    >  « MSHTML : » doit précéder le fragment de code HTML afin qu’il est désigné comme étant un flux MSHTML. Seuls les ProgID et CLSID sont pris en charge dans les plateformes Windows Mobile. Windows CE incorporé plates-formes, autres que Windows Mobile avec Internet Explorer CE prise en charge pour tous les types, y compris les ProgID, CLSID, URL, font référence au document actif et le fragment de code HTML.  
  
 `pStream`  
 [in] Pointeur vers un flux qui est utilisé pour initialiser les propriétés du contrôle. Peut être **NULL**.  
  
 `ppUnkContainer`  
 [out] L’adresse d’un pointeur qui va recevoir la **IUnknown** du conteneur. Peut être **NULL**.  
  
 `dwResID`  
 L’ID de ressource d’une ressource HTML. Le contrôle WebBrowser est créé et chargé avec la ressource spécifiée.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Notes  
 Si la deuxième version de cette méthode est utilisée, un contrôle HTML est créé et lié à la ressource identifiée par `dwResID`.  
  
 Cette méthode vous donne le même résultat que l’appel :  
  
 [!code-cpp[NVC_ATL_Windowing&#42;](../../atl/codesnippet/cpp/caxwindow-class_1.cpp)]  
  
 Consultez la page [CAxWindow2T::CreateControlLic](../../atl/reference/caxwindow2t-class.md#createcontrollic) pour créer, initialiser et héberger un contrôle ActiveX sous licence.  
  
### <a name="example"></a>Exemple  
 Consultez la page [hébergement ActiveX des contrôles à l’aide de ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) pour obtenir un exemple qui utilise `CreateControl`.  
  
##  <a name="createcontrolex"></a>CAxWindow::CreateControlEx  
 Crée un contrôle ActiveX, puis initialise et héberge ce dernier dans la fenêtre spécifiée.  
  
```
HRESULT CreateControlEx(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);

HRESULT CreateControlEx(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszName`  
 Pointeur vers une chaîne pour créer le contrôle. Doit être mis en forme dans une des manières suivantes :  
  
-   Un ProgID tels que « MSCAL. Calendar.7 »  
  
-   CLSID tel que « {8E27C92B-1264-101C-8A2F-040224009C02} »  
  
-   Une URL telle que « http://www.microsoft.com »  
  
-   Une référence à un document actif comme « file://\\\Documents\MyDoc.doc »  
  
-   Un fragment de code HTML comme « MSHTML :\<HTML >\<corps > il s’agit d’une ligne de texte\</corps >\</HTML > »  
  
    > [!NOTE]
    >  « MSHTML : » doit précéder le fragment de code HTML afin qu’il est désigné comme étant un flux MSHTML. Seuls les ProgID et CLSID sont pris en charge dans les plateformes Windows Mobile. Windows CE incorporé plates-formes, autres que Windows Mobile avec Internet Explorer CE prise en charge pour tous les types, y compris les ProgID, CLSID, URL, font référence au document actif et le fragment de code HTML.  
  
 `pStream`  
 [in] Pointeur vers un flux qui est utilisé pour initialiser les propriétés du contrôle. Peut être **NULL**.  
  
 `ppUnkContainer`  
 [out] L’adresse d’un pointeur qui va recevoir la **IUnknown** du conteneur. Peut être **NULL**.  
  
 `ppUnkControl`  
 [out] L’adresse d’un pointeur qui va recevoir la **IUnknown** du contrôle. Peut être **NULL**.  
  
 `iidSink`  
 [in] L’identificateur d’interface d’une interface sortante sur l’objet de relation contenant-contenu. Peut être **IID_NULL**.  
  
 *punkSink*  
 [in] Un pointeur vers le **IUnknown** interface de l’objet de récepteur d’être connectés au point de connexion de l’objet de relation contenant-contenu spécifié par `iidSink`.  
  
 `dwResID`  
 [in] L’ID de ressource d’une ressource HTML. Le contrôle WebBrowser est créé et chargé avec la ressource spécifiée.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Notes  
 Cette méthode est similaire à [CAxWindow::CreateControl](#createcontrol), mais contrairement à cette méthode, `CreateControlEx` vous permet également de recevoir un pointeur d’interface au contrôle nouvellement créé et configuré un récepteur d’événements pour recevoir des événements déclenchés par le contrôle.  
  
 Consultez la page [CAxWindow2T::CreateControlLicEx](../../atl/reference/caxwindow2t-class.md#createcontrollicex) pour créer, initialiser et héberger un contrôle ActiveX sous licence.  
  
### <a name="example"></a>Exemple  
 Consultez la page [hébergement ActiveX des contrôles à l’aide de ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) pour obtenir un exemple qui utilise `CreateControlEx`.  
  
##  <a name="getwndclassname"></a>CAxWindow::GetWndClassName  
 Récupère le nom de la classe de fenêtre.  
  
```
static LPCTSTR GetWndClassName();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers une chaîne contenant le nom de la classe de fenêtre qui peut héberger des contrôles ActiveX sans licence.  
  
##  <a name="operator_eq"></a>CAxWindow::operator =  
 Assigne une `HWND` à un fichier `CAxWindow` objet.  
  
```
CAxWindow<TBase>& operator=(HWND hWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 `hWnd`  
 Handle d’une fenêtre existante.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une référence à l'objet `CAxWindow` actif.  
  
##  <a name="querycontrol"></a>CAxWindow::QueryControl  
 Récupère l’interface spécifiée du contrôle hébergé.  
  
```
HRESULT QueryControl(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryControl(Q** ppUnk);
```  
  
### <a name="parameters"></a>Paramètres  
 `iid`  
 [in] Spécifie l’IID de l’interface du contrôle.  
  
 `ppUnk`  
 [out] Pointeur vers l’interface du contrôle. Dans la version du modèle de cette méthode, il est inutile d’un ID de référence tant qu’une interface typée avec un UUID associé est passée.  
  
 `Q`  
 [in] L’interface qui est en cours d’interrogation.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
##  <a name="queryhost"></a>CAxWindow::QueryHost  
 Retourne l’interface spécifiée de l’ordinateur hôte.  
  
```
HRESULT QueryHost(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryHost(Q** ppUnk);
```  
  
### <a name="parameters"></a>Paramètres  
 `iid`  
 [in] Spécifie l’IID de l’interface du contrôle.  
  
 `ppUnk`  
 [out] Pointeur vers l’interface sur l’ordinateur hôte. Dans la version du modèle de cette méthode, il est inutile d’un ID de référence tant qu’une interface typée avec un UUID associé est passée.  
  
 `Q`  
 [in] L’interface qui est en cours d’interrogation.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Remarques  
 L’interface de l’hôte permet d’accéder à la fonctionnalité sous-jacente du code de fenêtre qui héberge, implémentée par **AxWin**.  
  
##  <a name="setexternaldispatch"></a>CAxWindow::SetExternalDispatch  
 Définit l’interface de dispatch externe pour le `CAxWindow` objet.  
  
```
HRESULT SetExternalDispatch(IDispatch* pDisp);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDisp`  
 [in] Un pointeur vers un `IDispatch` interface.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
##  <a name="setexternaluihandler"></a>CAxWindow::SetExternalUIHandler  
 Définit l’externe [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) de l’interface pour le `CAxWindow` objet.  
  
```
HRESULT SetExternalUIHandler(IDocHostUIHandlerDispatch* pUIHandler);
```  
  
### <a name="parameters"></a>Paramètres  
 *pUIHandler*  
 [in] Un pointeur vers un **IDocHostUIHandlerDispatch** interface.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Remarques  
 Externe `IDocHostUIHandlerDispatch` interface utilisée par les contrôles qui interroge le site de l’ordinateur hôte pour le `IDocHostUIHandlerDispatch` interface. Le contrôle WebBrowser est un contrôle qui effectue l’opération.  
  
## <a name="see-also"></a>Voir aussi  
 [ATLCON, exemple](../../visual-cpp-samples.md)   
 [CWindow (classe)](../../atl/reference/cwindow-class.md)   
 [Notions fondamentales du contrôle composite](../../atl/atl-composite-control-fundamentals.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)   
 [Forum aux questions sur la contenance de contrôles](../../atl/atl-control-containment-faq.md)


