---
title: Classe CDHtmlDialog | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDHtmlDialog
dev_langs:
- C++
helpviewer_keywords:
- CDHtmlDialog class
ms.assetid: 3f941c85-87e1-4f0f-9cc5-ffee8498b312
caps.latest.revision: 23
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
ms.openlocfilehash: adf3664da1ecd1bdde9a1bd13e5b43ab7695e4d7
ms.lasthandoff: 02/24/2017

---
# <a name="cdhtmldialog-class"></a>Classe CDHtmlDialog
Permet de créer des boîtes de dialogue qui utilisent HTML plutôt que les ressources de boîte de dialogue pour implémenter leur interface utilisateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CDHtmlDialog : public CDialog, public CDHtmlEventSink  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CDHtmlDialog::CDHtmlDialog](#cdhtmldialog)|Construit un objet CDHtmlDialog.|  
|[CDHtmlDialog :: ~ CDHtmlDialog](#cdhtmldialog__~cdhtmldialog)|Détruit un objet CDHtmlDialog.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CDHtmlDialog::CanAccessExternal](#canaccessexternal)|Substituables qui est appelé une vérification pour voir si des objets de script sur la page chargée peuvent accéder à la distribution externe de contrôle d’accès. Vérifie que la répartition est sécurisé pour le script ou la zone en cours permet à des objets qui ne sont pas sécurisés pour les scripts.|  
|[CDHtmlDialog::CreateControlSite](#createcontrolsite)|Overridable utilisé pour créer une instance de site de contrôle pour héberger le contrôle WebBrowser sur la boîte de dialogue.|  
|[CDHtmlDialog::DDX_DHtml_AxControl](#ddx_dhtml_axcontrol)|Échange des données entre une variable de membre et la valeur de propriété d’un contrôle ActiveX sur une page HTML.|  
|[CDHtmlDialog::DDX_DHtml_CheckBox](#ddx_dhtml_checkbox)|Échange des données entre une variable membre et une case à cocher sur une page HTML.|  
|[CDHtmlDialog::DDX_DHtml_ElementText](#ddx_dhtml_elementtext)|Échange des données entre une variable de membre et de n’importe quelle propriété d’élément HTML dans une page HTML.|  
|[CDHtmlDialog::DDX_DHtml_Radio](#ddx_dhtml_radio)|Échange des données entre une variable membre et une case d’option sur une page HTML.|  
|[CDHtmlDialog::DDX_DHtml_SelectIndex](#ddx_dhtml_selectindex)|Obtient ou définit l’index d’une zone de liste sur une page HTML.|  
|[CDHtmlDialog::DDX_DHtml_SelectString](#ddx_dhtml_selectstring)|Obtient ou définit le texte d’affichage d’une entrée de zone de liste (selon l’index actuel) sur une page HTML.|  
|[CDHtmlDialog::DDX_DHtml_SelectValue](#ddx_dhtml_selectvalue)|Obtient ou définit la valeur d’une entrée de zone de liste (selon l’index actuel) sur une page HTML.|  
|[CDHtmlDialog::DestroyModeless](#destroymodeless)|Détruit une boîte de dialogue non modale.|  
|[CDHtmlDialog::EnableModeless](#enablemodeless)|Permet de boîtes de dialogue non modale.|  
|[CDHtmlDialog::FilterDataObject](#filterdataobject)|Permet à la boîte de dialogue Filtrer les objets de données du Presse-papiers créés par le navigateur hébergé.|  
|[CDHtmlDialog::GetControlDispatch](#getcontroldispatch)|Récupère le `IDispatch` interface sur un contrôle ActiveX incorporé dans le document HTML.|  
|[CDHtmlDialog::GetControlProperty](#getcontrolproperty)|Récupère la propriété demandée du contrôle ActiveX spécifié.|  
|[CDHtmlDialog::GetCurrentUrl](#getcurrenturl)|Récupère l’URL Uniform Resource Locator () associé avec le document actif.|  
|[CDHtmlDialog::GetDHtmlDocument](#getdhtmldocument)|Récupère l’interface IHTMLDocument2 dans le document HTML actuellement chargé.|  
|[CDHtmlDialog::GetDropTarget](#getdroptarget)|Appelée par le contrôle WebBrowser contenu lorsqu’il est utilisé comme cible de déplacement pour permettre à la boîte de dialogue fournir une alternative [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679).|  
|[CDHtmlDialog::GetElement](#getelement)|Obtient une interface sur un élément HTML.|  
|[CDHtmlDialog::GetElementHtml](#getelementhtml)|Récupère le **innerHTML** propriété d’un élément HTML.|  
|[CDHtmlDialog::GetElementInterface](#getelementinterface)|Récupère le pointeur d’interface demandé à partir d’un élément HTML.|  
|[CDHtmlDialog::GetElementProperty](#getelementproperty)|Récupère la valeur de propriété d’un élément HTML.|  
|[CDHtmlDialog::GetElementText](#getelementtext)|Récupère le **innerText** propriété d’un élément HTML.|  
|[CDHtmlDialog::GetEvent](#getevent)|Obtient le **IHTMLEventObj** pointeur vers l’objet d’événement en cours.|  
|[CDHtmlDialog::GetExternal](#getexternal)|Obtient l’hôte `IDispatch` interface.|  
|[CDHtmlDialog::GetHostInfo](#gethostinfo)|Récupère les fonctionnalités de l’interface utilisateur de l’ordinateur hôte.|  
|[CDHtmlDialog::GetOptionKeyPath](#getoptionkeypath)|Récupère la clé de Registre sous laquelle sont stockés les préférences de l’utilisateur.|  
|[CDHtmlDialog::HideUI](#hideui)|Masque l’interface utilisateur de l’ordinateur hôte.|  
|[CDHtmlDialog::IsExternalDispatchSafe](#isexternaldispatchsafe)|Indique si l’hôte `IDispatch` interface est sécurisé pour le script.|  
|[CDHtmlDialog::LoadFromResource](#loadfromresource)|Charge la ressource spécifiée dans le contrôle WebBrowser.|  
|[CDHtmlDialog::Navigate](#navigate)|Navigue vers l’URL spécifiée.|  
|[CDHtmlDialog::OnBeforeNavigate](#onbeforenavigate)|Appelé par l’infrastructure avant le déclenche d’un événement de navigation.|  
|[CDHtmlDialog::OnDocumentComplete](#ondocumentcomplete)|Appelée par l’infrastructure pour avertir une application lorsqu’un document atteint le `READYSTATE_COMPLETE` état.|  
|[CDHtmlDialog::OnDocWindowActivate](#ondocwindowactivate)|Appelé par l’infrastructure lorsque la fenêtre de document est activée ou désactivée.|  
|[CDHtmlDialog::OnFrameWindowActivate](#onframewindowactivate)|Appelé par l’infrastructure lorsque la fenêtre frame est activée ou désactivée.|  
|[CDHtmlDialog::OnInitDialog](#oninitdialog)|Appelé en réponse à la **WM_INITDIALOG** message.|  
|[CDHtmlDialog::OnNavigateComplete](#onnavigatecomplete)|Appelé par l’infrastructure après un événement de navigation.|  
|[CDHtmlDialog::ResizeBorder](#resizeborder)|Avertit l’objet dont il a besoin de son espace de la bordure de redimensionnement.|  
|[CDHtmlDialog::SetControlProperty](#setcontrolproperty)|Définit la propriété d’un contrôle ActiveX à une nouvelle valeur.|  
|[CDHtmlDialog::SetElementHtml](#setelementhtml)|Définit les **innerHTML** propriété d’un élément HTML.|  
|[CDHtmlDialog::SetElementProperty](#setelementproperty)|Définit une propriété d’un élément HTML.|  
|[CDHtmlDialog::SetElementText](#setelementtext)|Définit les **innerText** propriété d’un élément HTML.|  
|[CDHtmlDialog::SetExternalDispatch](#setexternaldispatch)|Définit l’hôte `IDispatch` interface.|  
|[CDHtmlDialog::SetHostFlags](#sethostflags)|Définit les indicateurs de l’interface utilisateur de l’ordinateur hôte.|  
|[CDHtmlDialog::ShowContextMenu](#showcontextmenu)|Appelée lorsqu’un menu contextuel est sur le point d’être affiché.|  
|[CDHtmlDialog::ShowUI](#showui)|Affiche l’interface utilisateur de l’ordinateur hôte.|  
|[CDHtmlDialog::TranslateAccelerator](#translateaccelerator)|Appelé pour traiter les messages de touche d’accès rapide de menu.|  
|[CDHtmlDialog::TranslateUrl](#translateurl)|Appelée pour modifier l’URL à charger.|  
|[CDHtmlDialog::UpdateUI](#updateui)|Appelé pour avertir l’hôte que l’état de la commande a changé.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CDHtmlDialog::m_bUseHtmlTitle](#m_busehtmltitle)|Indique s’il faut utiliser le titre d’un document HTML en tant que légende de la boîte de dialogue.|  
|[CDHtmlDialog::m_nHtmlResID](#m_nhtmlresid)|Ressource ID de HTML à afficher.|  
|[CDHtmlDialog::m_pBrowserApp](#m_pbrowserapp)|Pointeur vers une application de navigateur Web.|  
|[CDHtmlDialog::m_spHtmlDoc](#m_sphtmldoc)|Pointeur vers un document HTML.|  
|[CDHtmlDialog::m_strCurrentUrl](#m_strcurrenturl)|L’URL actuelle.|  
|[CDHtmlDialog::m_szHtmlResID](#m_szhtmlresid)|Version de chaîne de l’ID de ressource HTML.|  
  
## <a name="remarks"></a>Notes  
 **CDHtmlDialog** peut charger le code HTML à afficher à partir d’une ressource HTML ou une URL.  
  
 `CDHtmlDialog`peuvent également données exchange avec les contrôles HTML et gérer les événements de contrôles HTML, tels que les clics de bouton.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDHtmlSinkHandlerBase2`  
  
 `CDHtmlSinkHandlerBase1`  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDHtmlSinkHandler`  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDHtmlEventSink`  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CDHtmlDialog`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdhtml.h  
  
##  <a name="a-nameddxdhtmlhelpermacrosa--ddxdhtml-helper-macros"></a><a name="ddx_dhtml_helper_macros"></a>Macros d’assistance DDX_DHtml  
 Les macros d’assistance DDX_DHtml permettent un accès facile aux propriétés courantes des contrôles sur une page HTML.  
  
### <a name="data-exchange-macros"></a>Macros de données Exchange  
  
|||  
|-|-|  
|[DDX_DHtml_ElementValue](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementvalue)|Définit ou récupère la propriété Value du contrôle sélectionné.|  
|[DDX_DHtml_ElementInnerText](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnertext)|Définit ou récupère le texte entre les balises de début et de fin de l’élément actuel.|  
|[DDX_DHtml_ElementInnerHtml](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnerhtml)|Définit ou récupère le code HTML entre les balises de début et de fin de l’élément actuel.|  
|[DDX_DHtml_Anchor_Href](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_href)|Définit ou récupère la destination URL ou point d’ancrage.|  
|[DDX_DHtml_Anchor_Target](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_target)|Définit ou récupère la fenêtre ou frame cible.|  
|[DDX_DHtml_Img_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_img_src)|Définit ou récupère le nom d’une image ou un clip vidéo dans le document.|  
|[DDX_DHtml_Frame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_frame_src)|Définit ou extrait l’URL de l’image associée.|  
|[DDX_DHtml_IFrame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_iframe_src)|Définit ou extrait l’URL de l’image associée.|  
  
##  <a name="a-namecanaccessexternala--cdhtmldialogcanaccessexternal"></a><a name="canaccessexternal"></a>CDHtmlDialog::CanAccessExternal  
 Substituables qui est appelé une vérification pour voir si des objets de script sur la page chargée peuvent accéder à la distribution externe de contrôle d’accès. Vérifie que la répartition est sécurisé pour le script ou la zone en cours permet à des objets qui ne sont pas sécurisés pour les scripts.  
  
```  
virtual BOOL CanAccessExternal();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
##  <a name="a-namecdhtmldialoga--cdhtmldialogcdhtmldialog"></a><a name="cdhtmldialog"></a>CDHtmlDialog::CDHtmlDialog  
 Construit une boîte de dialogue dynamique HTML ressource.  
  
```  
CDHtmlDialog();

 
CDHtmlDialog(
    LPCTSTR lpszTemplateName,  
    LPCTSTR szHtmlResID,  
    CWnd *pParentWnd = NULL);

 
CDHtmlDialog(
    UINT nIDTemplate,  
    UINT nHtmlResID = 0,  
    CWnd *pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszTemplateName`  
 Chaîne terminée par le caractère null qui correspond au nom d’une ressource modèle de boîte de dialogue.  
  
 `szHtmlResID`  
 Chaîne terminée par le caractère null qui correspond au nom d’une ressource HTML.  
  
 `pParentWnd`  
 Un pointeur vers l’objet de fenêtre parente ou propriétaire (de type [CWnd](../../mfc/reference/cwnd-class.md)) auquel appartient l’objet de la boîte de dialogue. S’il s’agit **NULL**, la boîte de dialogue fenêtre l’objet parent est définie dans la fenêtre principale de l’application.  
  
 `nIDTemplate`  
 Contient le numéro d’ID d’une ressource modèle de boîte de dialogue.  
  
 `nHtmlResID`  
 Contient le numéro d’ID d’une ressource HTML.  
  
### <a name="remarks"></a>Remarques  
 La deuxième forme du constructeur permet d’accéder à la ressource de boîte de dialogue via le nom du modèle. La troisième forme du constructeur permet d’accéder à la ressource de boîte de dialogue avec le code du modèle de ressource. En règle générale, le code commence par la **IDD_** préfixe.  
  
##  <a name="a-namedtorcdhtmldialoga--cdhtmldialogcdhtmldialog"></a><a name="_dtorcdhtmldialog"></a>CDHtmlDialog :: ~ CDHtmlDialog  
 Détruit un objet CDHtmlDialog.  
  
```  
virtual ~CDHtmlDialog();
```  
  
### <a name="remarks"></a>Remarques  
 Le [CWnd::DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) fonction membre doit être utilisée pour détruire les boîtes de dialogue non modale qui sont créés par [CDialog::Create](../../mfc/reference/cdialog-class.md#create).  
  
##  <a name="a-namecreatecontrolsitea--cdhtmldialogcreatecontrolsite"></a><a name="createcontrolsite"></a>CDHtmlDialog::CreateControlSite  
 Overridable utilisé pour créer une instance de site de contrôle pour héberger le contrôle WebBrowser sur la boîte de dialogue.  
  
```  
virtual BOOL CreateControlSite(
    COleControlContainer* pContainer,  
    COleControlSite** ppSite,  
    UINT /* nID */,  
    REFCLSID /* clsid */);
```  
  
### <a name="parameters"></a>Paramètres  
 `pContainer`  
 Un pointeur vers le [COleControlContainer](../../mfc/reference/colecontrolcontainer-class.md) objet  
  
 `ppSite`  
 Un pointeur vers un pointeur vers un [COleControlSite](../../mfc/reference/colecontrolsite-class.md).  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Vous pouvez remplacer cette fonction membre pour retourner une instance de votre propre classe de site du contrôle.  
  
##  <a name="a-nameddxdhtmlaxcontrola--cdhtmldialogddxdhtmlaxcontrol"></a><a name="ddx_dhtml_axcontrol"></a>CDHtmlDialog::DDX_DHtml_AxControl  
 Échange des données entre une variable de membre et la valeur de propriété d’un contrôle ActiveX sur une page HTML.  
  
```  
void DDX_DHtml_AxControl(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    VARIANT& var);

 
void DDX_DHtml_AxControl(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    LPCTSTR szPropName,  
    VARIANT& var);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDX`  
 Un pointeur vers un [CDataExchange](../../mfc/reference/cdataexchange-class.md) objet.  
  
 `szId`  
 La valeur du paramètre d’ID de la balise object dans la source HTML pour le contrôle ActiveX.  
  
 `dispid`  
 L’ID de dispatch de la propriété avec laquelle vous souhaitez échanger des données.  
  
 `szPropName`  
 Nom de la propriété.  
  
 `var`  
 Le membre de données de type `VARIANT`, [COleVariant](../../mfc/reference/colevariant-class.md), ou [CComVariant](../../atl/reference/ccomvariant-class.md), qui contient la valeur échangée avec la propriété du contrôle ActiveX.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCHtmlHttp n °&1;](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_1.cpp)]  
  
##  <a name="a-nameddxdhtmlcheckboxa--cdhtmldialogddxdhtmlcheckbox"></a><a name="ddx_dhtml_checkbox"></a>CDHtmlDialog::DDX_DHtml_CheckBox  
 Échange des données entre une variable membre et une case à cocher sur une page HTML.  
  
```  
void DDX_DHtml_CheckBox(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    int& value);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDX`  
 Un pointeur vers un [CDataExchange](../../mfc/reference/cdataexchange-class.md) objet.  
  
 `szId`  
 La valeur que vous avez spécifié pour le paramètre d’ID du contrôle HTML.  
  
 *value*  
 La valeur qui est échangée.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCHtmlHttp n °&2;](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_2.cpp)]  
  
##  <a name="a-nameddxdhtmlelementtexta--cdhtmldialogddxdhtmlelementtext"></a><a name="ddx_dhtml_elementtext"></a>CDHtmlDialog::DDX_DHtml_ElementText  
 Échange des données entre une variable de membre et de n’importe quelle propriété d’élément HTML dans une page HTML.  
  
```  
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    CString& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    short& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    int& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    long& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    DWORD& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    float& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    double& value);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDX`  
 Un pointeur vers un [CDataExchange](../../mfc/reference/cdataexchange-class.md) objet.  
  
 `szId`  
 La valeur que vous avez spécifié pour le paramètre d’ID du contrôle HTML.  
  
 *DISPID*  
 L’ID de dispatch de l’élément HTML auquel vous souhaitez échanger des données.  
  
 *value*  
 La valeur qui est échangée.  
  
##  <a name="a-nameddxdhtmlradioa--cdhtmldialogddxdhtmlradio"></a><a name="ddx_dhtml_radio"></a>CDHtmlDialog::DDX_DHtml_Radio  
 Échange des données entre une variable membre et une case d’option sur une page HTML.  
  
```  
void DDX_DHtml_Radio(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    long& value);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDX`  
 Un pointeur vers un [CDataExchange](../../mfc/reference/cdataexchange-class.md) objet.  
  
 `szId`  
 La valeur que vous avez spécifié pour le paramètre d’ID du contrôle HTML.  
  
 *value*  
 La valeur qui est échangée.  
  
##  <a name="a-nameddxdhtmlselectindexa--cdhtmldialogddxdhtmlselectindex"></a><a name="ddx_dhtml_selectindex"></a>CDHtmlDialog::DDX_DHtml_SelectIndex  
 Obtient ou définit l’index d’une zone de liste sur une page HTML.  
  
```  
void DDX_DHtml_SelectIndex(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    long& value);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDX`  
 Un pointeur vers un [CDataExchange](../../mfc/reference/cdataexchange-class.md) objet.  
  
 `szId`  
 La valeur que vous avez spécifié pour le paramètre d’id du contrôle HTML.  
  
 *value*  
 La valeur qui est échangée.  
  
##  <a name="a-nameddxdhtmlselectstringa--cdhtmldialogddxdhtmlselectstring"></a><a name="ddx_dhtml_selectstring"></a>CDHtmlDialog::DDX_DHtml_SelectString  
 Obtient ou définit le texte d’affichage d’une entrée de zone de liste (selon l’index actuel) sur une page HTML.  
  
```  
void DDX_DHtml_SelectString(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    CString& value);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDX`  
 Un pointeur vers un [CDataExchange](../../mfc/reference/cdataexchange-class.md) objet.  
  
 `szId`  
 La valeur que vous avez spécifié pour le paramètre d’ID du contrôle HTML.  
  
 *value*  
 La valeur qui est échangée.  
  
##  <a name="a-nameddxdhtmlselectvaluea--cdhtmldialogddxdhtmlselectvalue"></a><a name="ddx_dhtml_selectvalue"></a>CDHtmlDialog::DDX_DHtml_SelectValue  
 Obtient ou définit la valeur d’une entrée de zone de liste (selon l’index actuel) sur une page HTML.  
  
```  
void DDX_DHtml_SelectValue(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    CString& value);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDX`  
 Un pointeur vers un [CDataExchange](../../mfc/reference/cdataexchange-class.md) objet.  
  
 `szId`  
 La valeur que vous avez spécifié pour le paramètre d’ID du contrôle HTML.  
  
 *value*  
 La valeur qui est échangée.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCHtmlHttp n °&3;](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_3.cpp)]  
  
##  <a name="a-namedestroymodelessa--cdhtmldialogdestroymodeless"></a><a name="destroymodeless"></a>CDHtmlDialog::DestroyModeless  
 Détache une boîte de dialogue non modale à partir de la `CDHtmlDialog` de l’objet et détruit l’objet.  
  
```  
void DestroyModeless();
```  
  
##  <a name="a-nameenablemodelessa--cdhtmldialogenablemodeless"></a><a name="enablemodeless"></a>CDHtmlDialog::EnableModeless  
 Permet de boîtes de dialogue non modale.  
  
```  
STDMETHOD(EnableModeless)(BOOL fEnable);
```  
  
### <a name="parameters"></a>Paramètres  
 `fEnable`  
 Consultez la page `fEnable` dans [IDocHostUIHandler::EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **E_NOTIMPL**.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre est mise en oeuvre de CDHtmlDialog de [IDocHostUIHandler::EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namefilterdataobjecta--cdhtmldialogfilterdataobject"></a><a name="filterdataobject"></a>CDHtmlDialog::FilterDataObject  
 Permet à la boîte de dialogue Filtrer les objets de données du Presse-papiers créés par le navigateur hébergé.  
  
```  
STDMETHOD(FilterDataObject)(
    IDataObject* pDO,  
    IDataObject** ppDORet);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDO`  
 Consultez la page `pDO` dans [IDocHostUIHandler::FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `ppDORet`  
 Consultez la page `ppDORet` dans **IDocHostUIHandler::FilterDataObject** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **S_FALSE**.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre est mise en oeuvre de CDHtmlDialog de [IDocHostUIHandler::FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetcontroldispatcha--cdhtmldialoggetcontroldispatch"></a><a name="getcontroldispatch"></a>CDHtmlDialog::GetControlDispatch  
 Récupère le `IDispatch` interface sur un contrôle ActiveX incorporé dans le document HTML renvoyé par [GetDHtmlDocument](#getdhtmldocument).  
  
```  
HRESULT GetControlDispatch(
    LPCTSTR szId,  
    IDispatch** ppdisp);
```  
  
### <a name="parameters"></a>Paramètres  
 `szId`  
 Le code HTML d’un contrôle ActiveX.  
  
 *ppdisp*  
 Le `IDispatch` interface du contrôle si trouvé dans la page Web.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
##  <a name="a-namegetcontrolpropertya--cdhtmldialoggetcontrolproperty"></a><a name="getcontrolproperty"></a>CDHtmlDialog::GetControlProperty  
 Récupère la propriété demandée du contrôle ActiveX spécifié.  
  
```  
VARIANT GetControlProperty(
    LPCTSTR szId,  
    LPCTSTR szPropName);

 
VARIANT GetControlProperty(
    LPCTSTR szId,  
    DISPID dispid);

 
VARIANT GetControlProperty(
    IDispatch* pdispControl,  
    DISPID dispid);
```  
  
### <a name="parameters"></a>Paramètres  
 `szId`  
 Le code HTML d’un contrôle ActiveX.  
  
 `szPropName`  
 Le nom d’une propriété dans les paramètres régionaux par défaut de l’utilisateur actuel.  
  
 `pdispControl`  
 Le `IDispatch` pointeur d’un contrôle ActiveX.  
  
 `dispid`  
 L’ID de dispatch d’une propriété.  
  
### <a name="return-value"></a>Valeur de retour  
 Variant qui contient la propriété demandée ou une variante vide si le contrôle ou la propriété est introuvable.  
  
### <a name="remarks"></a>Remarques  
 Les surcharges sont répertoriées de la moins efficace en haut à la plus efficace en bas.  
  
##  <a name="a-namegetcurrenturla--cdhtmldialoggetcurrenturl"></a><a name="getcurrenturl"></a>CDHtmlDialog::GetCurrentUrl  
 Récupère l’URL Uniform Resource Locator () associé avec le document actif.  
  
```  
void GetCurrentUrl(CString& szUrl);
```  
  
### <a name="parameters"></a>Paramètres  
 `szUrl`  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) objet contenant l’URL à récupérer.  
  
##  <a name="a-namegetdhtmldocumenta--cdhtmldialoggetdhtmldocument"></a><a name="getdhtmldocument"></a>CDHtmlDialog::GetDHtmlDocument  
 Récupère le [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx) interface sur le document HTML actuellement chargé.  
  
```  
HRESULT GetDHtmlDocument(IHTMLDocument2 **pphtmlDoc);
```  
  
### <a name="parameters"></a>Paramètres  
 *\*\*pphtmlDoc*  
 Pointeur vers un pointeur vers un document HTML.  
  
### <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard. Retourne `S_OK` en cas de réussite.  
  
##  <a name="a-namegetdroptargeta--cdhtmldialoggetdroptarget"></a><a name="getdroptarget"></a>CDHtmlDialog::GetDropTarget  
 Appelée par le contrôle WebBrowser contenu lorsqu’il est utilisé comme cible de déplacement pour permettre à la boîte de dialogue fournir une alternative [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679).  
  
```  
STDMETHOD(GetDropTarget)(
    IDropTarget* pDropTarget,  
    IDropTarget** ppDropTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDropTarget`  
 Consultez la page `pDropTarget` dans [IDocHostUIHandler::GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `ppDropTarget`  
 Consultez la page `ppDropTarget` dans **IDocHostUIHandler::GetDropTarget** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **E_NOTIMPL**.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre est mise en oeuvre de CDHtmlDialog de [IDocHostUIHandler::GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetelementa--cdhtmldialoggetelement"></a><a name="getelement"></a>CDHtmlDialog::GetElement  
 Retourne une interface sur l’élément HTML spécifié par `szElementId`.  
  
```  
HRESULT GetElement(
    LPCTSTR szElementId,  
    IDispatch** ppdisp,  
    BOOL* pbCollection = NULL);

 
HRESULT GetElement(
    LPCTSTR szElementId,  
    IHTMLElement** pphtmlElement);
```  
  
### <a name="parameters"></a>Paramètres  
 `szElementId`  
 L’ID d’un élément HTML.  
  
 *ppdisp*  
 Un `IDispatch` pointeur vers l’élément demandé ou une collection d’éléments.  
  
 *pbCollection*  
 A **BOOL** indiquant si l’objet représenté par *ppdisp* est un élément unique ou une collection d’éléments.  
  
 *pphtmlElement*  
 Un **IHTMLElement** pointeur vers l’élément demandé.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Notes  
 Utilisez la première surcharge si vous avez besoin gérer les conditions dans lesquelles peuvent être plus d’un élément avec l’ID spécifié. Vous pouvez utiliser le dernier paramètre pour déterminer si le pointeur d’interface retourné est une collection ou un seul élément. Si le pointeur d’interface est une collection, vous pouvez interroger pour le **IHTMLElementCollection** et utiliser ses **élément** propriété pour faire référence aux éléments par position ordinale.  
  
 La deuxième surcharge échoue s’il existe plusieurs éléments avec le même ID dans la page.  
  
##  <a name="a-namegetelementhtmla--cdhtmldialoggetelementhtml"></a><a name="getelementhtml"></a>CDHtmlDialog::GetElementHtml  
 Récupère le **innerHTML** propriété de l’élément HTML identifié par `szElementId`.  
  
```  
BSTR GetElementHtml(LPCTSTR szElementId);
```  
  
### <a name="parameters"></a>Paramètres  
 `szElementId`  
 L’ID d’un élément HTML.  
  
### <a name="return-value"></a>Valeur de retour  
 Le **innerHTML** propriété de l’élément HTML identifié par `szElementId` ou **NULL** si l’élément est introuvable.  
  
##  <a name="a-namegetelementinterfacea--cdhtmldialoggetelementinterface"></a><a name="getelementinterface"></a>CDHtmlDialog::GetElementInterface  
 Récupère le pointeur d’interface demandé à partir de l’élément HTML identifié par `szElementId`.  
  
```  
template <class Q> HRESULT GetElementInterface(
    LPCTSTR szElementId,  
    Q** ppvObj);

 
HRESULT GetElementInterface(
    LPCTSTR szElementId,  
    REFIID riid,  
    void** ppvObj);
```  
  
### <a name="parameters"></a>Paramètres  
 `szElementId`  
 L’ID d’un élément HTML.  
  
 `ppvObj`  
 Adresse d’un pointeur qui est rempli avec le pointeur d’interface demandé si l’élément est trouvé et la requête aboutit.  
  
 `riid`  
 L’interface ID (IID) de l’interface demandée.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCHtmlHttp n °&4;](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_4.cpp)]  
  
##  <a name="a-namegetelementpropertya--cdhtmldialoggetelementproperty"></a><a name="getelementproperty"></a>CDHtmlDialog::GetElementProperty  
 Récupère la valeur de la propriété identifiée par `dispid` à partir de l’élément HTML identifié par `szElementId`.  
  
```  
VARIANT GetElementProperty(
    LPCTSTR szElementId,  
    DISPID dispid);
```  
  
### <a name="parameters"></a>Paramètres  
 `szElementId`  
 L’ID d’un élément HTML.  
  
 `dispid`  
 L’ID de dispatch d’une propriété.  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur de la propriété ou une variante vide si la propriété ou l’élément est introuvable.  
  
##  <a name="a-namegetelementtexta--cdhtmldialoggetelementtext"></a><a name="getelementtext"></a>CDHtmlDialog::GetElementText  
 Récupère le **innerText** propriété de l’élément HTML identifié par `szElementId`.  
  
```  
BSTR GetElementText(LPCTSTR szElementId);
```  
  
### <a name="parameters"></a>Paramètres  
 `szElementId`  
 L’ID d’un élément HTML.  
  
### <a name="return-value"></a>Valeur de retour  
 Le **innerText** propriété de l’élément HTML identifié par `szElementId` ou **NULL** si la propriété ou l’élément est introuvable.  
  
##  <a name="a-namegeteventa--cdhtmldialoggetevent"></a><a name="getevent"></a>CDHtmlDialog::GetEvent  
 Retourne le **IHTMLEventObj** pointeur vers l’objet d’événement en cours.  
  
```  
HRESULT GetEvent(IHTMLEventObj** ppEventObj);
```  
  
### <a name="parameters"></a>Paramètres  
 `ppEventObj`  
 Adresse d’un pointeur qui sera rempli avec les **IHTMLEventObj** pointeur d’interface.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction doit uniquement être appelée à partir d’un gestionnaire d’événements DHTML.  
  
##  <a name="a-namegetexternala--cdhtmldialoggetexternal"></a><a name="getexternal"></a>CDHtmlDialog::GetExternal  
 Obtient l’hôte `IDispatch` interface.  
  
```  
STDMETHOD(GetExternal)(IDispatch** ppDispatch);
```  
  
### <a name="parameters"></a>Paramètres  
 *ppDispatch*  
 Consultez la page *ppDispatch* dans [IDocHostUIHandler::GetExternal](https://msdn.microsoft.com/library/aa753256.aspx) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `S_OK` en cas de réussite ou **E_NOTIMPL** en cas d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre est mise en oeuvre de CDHtmlDialog de [IDocHostUIHandler::GetExternal](https://msdn.microsoft.com/library/aa753256.aspx), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegethostinfoa--cdhtmldialoggethostinfo"></a><a name="gethostinfo"></a>CDHtmlDialog::GetHostInfo  
 Récupère les fonctionnalités de l’interface utilisateur de l’ordinateur hôte.  
  
```  
STDMETHOD(GetHostInfo)(DOCHOSTUIINFO* pInfo);
```  
  
### <a name="parameters"></a>Paramètres  
 `pInfo`  
 Consultez la page `pInfo` dans [IDocHostUIHandler::GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `S_OK`.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre est mise en oeuvre de CDHtmlDialog de [IDocHostUIHandler::GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetoptionkeypatha--cdhtmldialoggetoptionkeypath"></a><a name="getoptionkeypath"></a>CDHtmlDialog::GetOptionKeyPath  
 Récupère la clé de Registre sous laquelle sont stockés les préférences de l’utilisateur.  
  
```  
STDMETHOD(GetOptionKeyPath)(
    LPOLESTR* pchKey,  
    DWORD dw);
```  
  
### <a name="parameters"></a>Paramètres  
 `pchKey`  
 Consultez la page `pchKey` dans [IDocHostUIHandler::GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dw`  
 Consultez la page `dw` dans **IDocHostUIHandler::GetOptionKeyPath** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **E_NOTIMPL**.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre est mise en oeuvre de CDHtmlDialog de [IDocHostUIHandler::GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namehideuia--cdhtmldialoghideui"></a><a name="hideui"></a>CDHtmlDialog::HideUI  
 Masque l’interface utilisateur de l’ordinateur hôte.  
  
```  
STDMETHOD(HideUI)(void);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **E_NOTIMPL**.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre est mise en oeuvre de CDHtmlDialog de [IDocHostUIHandler::HideUI](https://msdn.microsoft.com/library/aa753259.aspx), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameisexternaldispatchsafea--cdhtmldialogisexternaldispatchsafe"></a><a name="isexternaldispatchsafe"></a>CDHtmlDialog::IsExternalDispatchSafe  
 Indique si l’hôte `IDispatch` interface est sécurisé pour le script.  
  
```  
virtual BOOL IsExternalDispatchSafe();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **FALSE**.  
  
##  <a name="a-nameloadfromresourcea--cdhtmldialogloadfromresource"></a><a name="loadfromresource"></a>CDHtmlDialog::LoadFromResource  
 Charge la ressource spécifiée dans le contrôle WebBrowser dans la boîte de dialogue DHTML.  
  
```  
BOOL LoadFromResource(LPCTSTR lpszResource);  
BOOL LoadFromResource(UINT nRes);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszResource`  
 Pointeur vers une chaîne contenant le nom de la ressource à charger.  
  
 `nRes`  
 ID de la ressource à charger.  
  
### <a name="return-value"></a>Valeur de retour  
 **TRUE** cas de réussite ; sinon **FALSE**.  
  
##  <a name="a-namembusehtmltitlea--cdhtmldialogmbusehtmltitle"></a><a name="m_busehtmltitle"></a>CDHtmlDialog::m_bUseHtmlTitle  
 Indique s’il faut utiliser le titre d’un document HTML en tant que légende de la boîte de dialogue.  
  
```  
BOOL m_bUseHtmlTitle;  
```  
  
### <a name="remarks"></a>Remarques  
 Si **m**_ **bUseHtmlTitle** est **true**, la légende de la boîte de dialogue est la valeur égale au titre du document HTML ; sinon, la légende dans la ressource de boîte de dialogue est utilisée.  
  
##  <a name="a-namemnhtmlresida--cdhtmldialogmnhtmlresid"></a><a name="m_nhtmlresid"></a>CDHtmlDialog::m_nHtmlResID  
 Ressource ID de HTML à afficher.  
  
```  
UINT m_nHtmlResID;  
```  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCHtmlHttp n °&5;](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_5.cpp)]  
  
##  <a name="a-namempbrowserappa--cdhtmldialogmpbrowserapp"></a><a name="m_pbrowserapp"></a>CDHtmlDialog::m_pBrowserApp  
 Pointeur vers une application de navigateur Web.  
  
```  
CComPtr <IWebBrowser2> m_pBrowserApp;  
```  
  
##  <a name="a-namemsphtmldoca--cdhtmldialogmsphtmldoc"></a><a name="m_sphtmldoc"></a>CDHtmlDialog::m_spHtmlDoc  
 Pointeur vers un document HTML.  
  
```  
CComPtr<IHTMLDocument2> m_spHtmlDoc;  
```  
  
##  <a name="a-namemstrcurrenturla--cdhtmldialogmstrcurrenturl"></a><a name="m_strcurrenturl"></a>CDHtmlDialog::m_strCurrentUrl  
 L’URL actuelle.  
  
```  
CString m_strCurrentUrl;  
```  
  
##  <a name="a-namemszhtmlresida--cdhtmldialogmszhtmlresid"></a><a name="m_szhtmlresid"></a>CDHtmlDialog::m_szHtmlResID  
 Version de chaîne de l’ID de ressource HTML.  
  
```  
LPTSTR m_szHtmlResID;  
```  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCHtmlHttp n °&6;](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_6.cpp)]  
  
##  <a name="a-namenavigatea--cdhtmldialognavigate"></a><a name="navigate"></a>CDHtmlDialog::Navigate  
 Accède à la ressource identifiée par l’URL spécifiée par `lpszURL`.  
  
```  
void Navigate(
    LPCTSTR lpszURL,  
    DWORD dwFlags = 0,  
    LPCTSTR lpszTargetFrameName = NULL,  
    LPCTSTR lpszHeaders = NULL,  
    LPVOID lpvPostData = NULL,  
    DWORD dwPostDataLen = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszURL`  
 Pointeur vers une chaîne contenant l’URL à cibler.  
  
 `dwFlags`  
 Les indicateurs d’une variable qui spécifie s’il faut ajouter la ressource à la liste historique, s’il faut lire dans le cache ou écrire à partir du cache et s’il faut afficher la ressource dans une nouvelle fenêtre. La variable peut être une combinaison des valeurs définies par le [BrowserNavConstants](https://msdn.microsoft.com/library/aa768360.aspx) (énumération).  
  
 `lpszTargetFrameName`  
 Pointeur vers une chaîne qui contient le nom du frame dans lequel afficher la ressource.  
  
 `lpszHeaders`  
 Pointeur vers une valeur qui spécifie les en-têtes HTTP à envoyer au serveur. Ces en-têtes sont ajoutés aux en-têtes Internet Explorer par défaut. Les en-têtes peuvent spécifier ces informations comme l’action requise du serveur, le type de données transmis au serveur, ou un code d’état. Ce paramètre est ignoré si l’URL n’est pas une URL HTTP.  
  
 `lpvPostData`  
 Pointeur vers les données à envoyer avec la transaction HTTP POST. Par exemple, la transaction POST est utilisée pour envoyer des données collectées par un formulaire HTML. Si ce paramètre ne spécifie pas toutes les données post, **naviguer** émet une transaction HTTP GET. Ce paramètre est ignoré si l’URL n’est pas une URL HTTP.  
  
 `dwPostDataLen`  
 Données à envoyer avec la transaction HTTP POST. Par exemple, la transaction POST est utilisée pour envoyer des données collectées par un formulaire HTML. Si ce paramètre ne spécifie pas toutes les données post, **naviguer** émet une transaction HTTP GET. Ce paramètre est ignoré si l’URL n’est pas une URL HTTP.  
  
##  <a name="a-nameonbeforenavigatea--cdhtmldialogonbeforenavigate"></a><a name="onbeforenavigate"></a>CDHtmlDialog::OnBeforeNavigate  
 Appelé par l’infrastructure pour provoquer un événement se déclenche avant une navigation se produit.  
  
```  
virtual void OnBeforeNavigate(
    LPDISPATCH pDisp,  
    LPCTSTR szUrl);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDisp`  
 Pointeur vers un objet `IDispatch` .  
  
 `szUrl`  
 Pointeur vers une chaîne contenant l’URL à atteindre.  
  
##  <a name="a-nameondocumentcompletea--cdhtmldialogondocumentcomplete"></a><a name="ondocumentcomplete"></a>CDHtmlDialog::OnDocumentComplete  
 Appelée par l’infrastructure pour avertir une application lorsqu’un document a atteint la `READYSTATE_COMPLETE` état.  
  
```  
virtual void OnDocumentComplete(
    LPDISPATCH pDisp,  
    LPCTSTR szUrl);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDisp`  
 Pointeur vers un objet `IDispatch` .  
  
 `szUrl`  
 Pointeur vers une chaîne contenant l’URL qui a été atteinte.  
  
##  <a name="a-nameondocwindowactivatea--cdhtmldialogondocwindowactivate"></a><a name="ondocwindowactivate"></a>CDHtmlDialog::OnDocWindowActivate  
 Appelé par l’infrastructure lorsque la fenêtre de document est activée ou désactivée.  
  
```  
STDMETHOD(OnDocWindowActivate)(BOOL fActivate);
```  
  
### <a name="parameters"></a>Paramètres  
 `fActivate`  
 Consultez la page `fActivate` dans [IDocHostUIHandler::OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **E_NOTIMPL**.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre est l’implémentation de CDHtmlDialog de [IDocHostUIHandler::OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameonframewindowactivatea--cdhtmldialogonframewindowactivate"></a><a name="onframewindowactivate"></a>CDHtmlDialog::OnFrameWindowActivate  
 Appelé par l’infrastructure lorsque la fenêtre frame est activée ou désactivée.  
  
```  
STDMETHOD(OnFrameWindowActivate)(BOOL fActivate);
```  
  
### <a name="parameters"></a>Paramètres  
 `fActivate`  
 Consultez la page `fActivate` dans [IDocHostUIHandler::OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **E_NOTIMPL**.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre est mise en oeuvre de CDHtmlDialog de [IDocHostUIHandler::OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameoninitdialoga--cdhtmldialogoninitdialog"></a><a name="oninitdialog"></a>CDHtmlDialog::OnInitDialog  
 Appelé en réponse à la **WM_INITDIALOG** message.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’implémentation par défaut retourne **TRUE**.  
  
### <a name="remarks"></a>Remarques  
 Ce message est envoyé à la boîte de dialogue lors de la **créer**, `CreateIndirect`, ou `DoModal` appels, qui se produisent immédiatement avant l’affichage de la boîte de dialogue.  
  
 Remplacez cette fonction membre, si vous avez besoin exécuter un traitement spécial lors de l’initialisation de la boîte de dialogue. Dans la version substituée, appelez d’abord la classe de base `OnInitDialog` mais ne pas tenir compte de sa valeur de retour. Vous allez normalement retourner **TRUE** à partir de votre fonction membre substitué.  
  
 Appels Windows le `OnInitDialog` fonctionner à travers de la procédure standard global-boîte de dialogue commune à toutes les boîtes de dialogue Microsoft Foundation Class Library, plutôt que via votre table des messages, par conséquent, il est inutile une entrée de table des messages pour cette fonction membre.  
  
##  <a name="a-nameonnavigatecompletea--cdhtmldialogonnavigatecomplete"></a><a name="onnavigatecomplete"></a>CDHtmlDialog::OnNavigateComplete  
 Appelé par l’infrastructure après la navigation vers l’URL spécifiée.  
  
```  
virtual void OnNavigateComplete(
    LPDISPATCH pDisp,  
    LPCTSTR szUrl);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDisp`  
 Pointeur vers un objet `IDispatch` .  
  
 `szUrl`  
 Pointeur vers une chaîne contenant l’URL qui a été atteinte.  
  
##  <a name="a-nameresizebordera--cdhtmldialogresizeborder"></a><a name="resizeborder"></a>CDHtmlDialog::ResizeBorder  
 Avertit l’objet dont il a besoin de son espace de la bordure de redimensionnement.  
  
```  
STDMETHOD(ResizeBorder)(
    LPCRECT prcBorder,  
    IOleInPlaceUIWindow* pUIWindow,  
    BOOL fRameWindow);
```  
  
### <a name="parameters"></a>Paramètres  
 `prcBorder`  
 Consultez la page `prcBorder` dans [IDocHostUIHandler::ResizeBorder](https://msdn.microsoft.com/library/aa753263.aspx) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pUIWindow`  
 Consultez la page `pUIWindow` dans **IDocHostUIHandler::ResizeBorder** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `fFrameWindow`  
 Consultez la page *fFrameWindow* dans **IDocHostUIHandler::ResizeBorder** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **E_NOTIMPL**.  
  
##  <a name="a-namesetcontrolpropertya--cdhtmldialogsetcontrolproperty"></a><a name="setcontrolproperty"></a>CDHtmlDialog::SetControlProperty  
 Définit la propriété d’un contrôle ActiveX à une nouvelle valeur.  
  
```  
void SetControlProperty(
    LPCTSTR szElementId,  
    DISPID dispid,  
    VARIANT* pVar);

 
void SetControlProperty(
    IDispatch* pdispControl,  
    DISPID dispid,  
    VARIANT* pVar);

 
void SetControlProperty(
    LPCTSTR szElementId,  
    LPCTSTR szPropName,  
    VARIANT* pVar);
```  
  
### <a name="parameters"></a>Paramètres  
 `szElementId`  
 Le code HTML d’un contrôle ActiveX.  
  
 `dispid`  
 L’ID de dispatch de la propriété à définir.  
  
 *pVar*  
 Pointeur vers un **variante** contenant la nouvelle valeur de propriété.  
  
 `pdispControl`  
 Pointeur vers un contrôle ActiveX `IDispatch` interface.  
  
 `szPropName`  
 Chaîne contenant le nom de la propriété à définir.  
  
##  <a name="a-namesetelementhtmla--cdhtmldialogsetelementhtml"></a><a name="setelementhtml"></a>CDHtmlDialog::SetElementHtml  
 Définit les **innerHTML** propriété d’un élément HTML.  
  
```  
void SetElementHtml(
    LPCTSTR szElementId,  
    BSTR bstrText);

 
void SetElementHtml(
    IUnknown* punkElem,  
    BSTR bstrText);
```  
  
### <a name="parameters"></a>Paramètres  
 `szElementId`  
 L’ID d’un élément HTML.  
  
 `bstrText`  
 La nouvelle valeur de la **innerHTML** propriété.  
  
 `punkElem`  
 Le **IUnknown** pointeur d’un élément HTML.  
  
##  <a name="a-namesetelementpropertya--cdhtmldialogsetelementproperty"></a><a name="setelementproperty"></a>CDHtmlDialog::SetElementProperty  
 Définit une propriété d’un élément HTML.  
  
```  
void SetElementProperty(
    LPCTSTR szElementId,  
    DISPID dispid,  
    VARIANT* pVar);
```  
  
### <a name="parameters"></a>Paramètres  
 `szElementId`  
 L’ID d’un élément HTML.  
  
 `dispid`  
 L’ID de dispatch de la propriété à définir.  
  
 *pVar*  
 Nouvelle valeur de la propriété.  
  
##  <a name="a-namesetelementtexta--cdhtmldialogsetelementtext"></a><a name="setelementtext"></a>CDHtmlDialog::SetElementText  
 Définit les **innerText** propriété d’un élément HTML.  
  
```  
void SetElementText(
    LPCTSTR szElementId,  
    BSTR bstrText);

 
void SetElementText(
    IUnknown* punkElem,  
    BSTR bstrText);
```  
  
### <a name="parameters"></a>Paramètres  
 `szElementId`  
 L’ID d’un élément HTML.  
  
 `bstrText`  
 La nouvelle valeur de la **innerText** propriété.  
  
 `punkElem`  
 Le **IUnknown** pointeur d’un élément HTML.  
  
##  <a name="a-namesetexternaldispatcha--cdhtmldialogsetexternaldispatch"></a><a name="setexternaldispatch"></a>CDHtmlDialog::SetExternalDispatch  
 Définit l’hôte `IDispatch` interface.  
  
```  
void SetExternalDispatch(IDispatch* pdispExternal);
```  
  
### <a name="parameters"></a>Paramètres  
 *pdispExternal*  
 La nouvelle `IDispatch` interface.  
  
##  <a name="a-namesethostflagsa--cdhtmldialogsethostflags"></a><a name="sethostflags"></a>CDHtmlDialog::SetHostFlags  
 Définit l’hôte des indicateurs de l’interface utilisateur.  
  
```  
void SetHostFlags(DWORD dwFlags);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwFlags`  
 Pour les valeurs possibles, consultez la page [DOCHOSTUIFLAG](https://msdn.microsoft.com/library/aa753277.aspx) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameshowcontextmenua--cdhtmldialogshowcontextmenu"></a><a name="showcontextmenu"></a>CDHtmlDialog::ShowContextMenu  
 Appelée lorsqu’un menu contextuel est sur le point d’être affiché.  
  
```  
STDMETHOD(ShowContextMenu)(
    DWORD dwID,  
    POINT* ppt,  
    IUnknown* pcmdtReserved,  
    IDispatch* pdispReserved);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwID`  
 Consultez la page `dwID` dans [IDocHostUIHandler::ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `ppt`  
 Consultez la page `ppt` dans **IDocHostUIHandler::ShowContextMenu** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pcmdtReserved`  
 Consultez la page `pcmdtReserved` dans **IDocHostUIHandler::ShowContextMenu** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pdispReserved`  
 Consultez la page `pdispReserved` dans **IDocHostUIHandler::ShowContextMenu** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **S_FALSE**.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre est mise en oeuvre de CDHtmlDialog de [IDocHostUIHandler::ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameshowuia--cdhtmldialogshowui"></a><a name="showui"></a>CDHtmlDialog::ShowUI  
 Affiche l’interface utilisateur de l’ordinateur hôte.  
  
```  
STDMETHOD(ShowUI)(
    DWORD dwID,  
    IOleInPlaceActiveObject* pActiveObject,  
    IOleCommandTarget* pCommandTarget,  
    IOleInPlaceFrame* pFrame,  
    IOleInPlaceUIWindow* pDoc);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwID`  
 Consultez la page `dwID` dans [IDocHostUIHandler::ShowUI](https://msdn.microsoft.com/library/aa753265.aspx) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pActiveObject`  
 Consultez la page *pActiveObject d* dans **IDocHostUIHandler::ShowUI** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pCommandTarget`  
 Consultez la page `pCommandTarget` dans **IDocHostUIHandler::ShowUI** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pFrame`  
 Consultez la page `pFrame` dans **IDocHostUIHandler::ShowUI** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pDoc`  
 Consultez la page `pDoc` dans **IDocHostUIHandler::ShowUI** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **S_FALSE**.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre est mise en oeuvre de CDHtmlDialog de [IDocHostUIHandler::ShowUI](https://msdn.microsoft.com/library/aa753265.aspx), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nametranslateacceleratora--cdhtmldialogtranslateaccelerator"></a><a name="translateaccelerator"></a>CDHtmlDialog::TranslateAccelerator  
 Appelé pour traiter les messages de touche d’accès rapide de menu.  
  
```  
STDMETHOD(TranslateAccelerator)(
    LPMSG lpMsg,  
    const GUID* pguidCmdGroup,  
    DWORD nCmdID);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpMsg`  
 Consultez la page `lpMsg` dans [IDocHostUIHandler::TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pguidCmdGroup`  
 Consultez la page `pguidCmdGroup` dans **IDocHostUIHandler::TranslateAccelerator** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `nCmdID`  
 Consultez la page `nCmdID` dans **IDocHostUIHandler::TranslateAccelerator** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **S_FALSE**.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre est mise en oeuvre de CDHtmlDialog de [IDocHostUIHandler::TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nametranslateurla--cdhtmldialogtranslateurl"></a><a name="translateurl"></a>CDHtmlDialog::TranslateUrl  
 Appelée pour modifier l’URL à charger.  
  
```  
STDMETHOD(TranslateUrl)(
    DWORD dwTranslate,  
    OLECHAR* pchURLIn,  
    OLECHAR** ppchURLOut);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwTranslate`  
 Consultez la page `dwTranslate` dans [IDocHostUIHandler::TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pchURLIn`  
 Consultez la page `pchURLIn` dans **IDocHostUIHandler::TranslateUrl** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `ppchURLOut`  
 Consultez la page `ppchURLOut` dans **IDocHostUIHandler::TranslateUrl** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **S_FALSE**.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre est mise en oeuvre de CDHtmlDialog de [IDocHostUIHandler::TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameupdateuia--cdhtmldialogupdateui"></a><a name="updateui"></a>CDHtmlDialog::UpdateUI  
 Appelé pour avertir l’hôte que l’état de la commande a changé.  
  
```  
STDMETHOD(UpdateUI)(void);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **E_NOTIMPL**.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre est mise en oeuvre de CDHtmlDialog de [IDocHostUIHandler::UpdateUI](https://msdn.microsoft.com/library/aa753268.aspx), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [MFC exemple DHtmlExplore](../../visual-cpp-samples.md)   
 [Macros d’assistance DDX_DHtml](#ddx_dhtml_helper_macros)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)



