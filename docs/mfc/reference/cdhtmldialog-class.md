---
title: "CDHtmlDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDHtmlDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDHtmlDialog class"
ms.assetid: 3f941c85-87e1-4f0f-9cc5-ffee8498b312
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDHtmlDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Est utilisé pour créer des boîtes de dialogue qui utilisent le HTML plutôt que des ressources de boîte de dialogue pour implémenter leur interface utilisateur.  
  
## Syntaxe  
  
```  
class CDHtmlDialog : public CDialog, public CDHtmlEventSink  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDHtmlDialog::CDHtmlDialog](../Topic/CDHtmlDialog::CDHtmlDialog.md)|Crée un objet de CDHtmlDialog.|  
|[CDHtmlDialog::~CDHtmlDialog](../Topic/CDHtmlDialog::~CDHtmlDialog.md)|Détruit un objet de CDHtmlDialog.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDHtmlDialog::CanAccessExternal](../Topic/CDHtmlDialog::CanAccessExternal.md)|Substituable appelé comme vérification de l'accès pour voir si les objets de script sur la page chargée peuvent accéder à l'expédition externe du site de contrôle.  Les contrôles pour garantir l'expédition est ou sans risque pour le script ou la zone actuelle autorise les objets qui ne sont pas assurés pour le script.|  
|[CDHtmlDialog::CreateControlSite](../Topic/CDHtmlDialog::CreateControlSite.md)|Substituable utilisé pour créer une instance de contrôle de site pour héberger le contrôle WebBrowser dans la boîte de dialogue.|  
|[CDHtmlDialog::DDX\_DHtml\_AxControl](../Topic/CDHtmlDialog::DDX_DHtml_AxControl.md)|Données d'échange entre une variable membre et la valeur de propriété d'un contrôle ActiveX sur une page HTML.|  
|[CDHtmlDialog::DDX\_DHtml\_CheckBox](../Topic/CDHtmlDialog::DDX_DHtml_CheckBox.md)|Données d'échange entre une variable membre et une case à cocher dans une page HTML.|  
|[CDHtmlDialog::DDX\_DHtml\_ElementText](../Topic/CDHtmlDialog::DDX_DHtml_ElementText.md)|Données d'échange entre une variable membre et toute propriété d'un élément HTML d'une page HTML.|  
|[CDHtmlDialog::DDX\_DHtml\_Radio](../Topic/CDHtmlDialog::DDX_DHtml_Radio.md)|Données d'échange entre une variable membre et une case d'option dans une page HTML.|  
|[CDHtmlDialog::DDX\_DHtml\_SelectIndex](../Topic/CDHtmlDialog::DDX_DHtml_SelectIndex.md)|Obtient ou définit l'index d'une zone de liste sur une page HTML.|  
|[CDHtmlDialog::DDX\_DHtml\_SelectString](../Topic/CDHtmlDialog::DDX_DHtml_SelectString.md)|Obtient ou définit le texte d'une entrée de zone de liste \(selon l'index actuel\) sur une page HTML.|  
|[CDHtmlDialog::DDX\_DHtml\_SelectValue](../Topic/CDHtmlDialog::DDX_DHtml_SelectValue.md)|Obtient ou définit la valeur d'une entrée de zone de liste \(selon l'index actuel\) sur une page HTML.|  
|[CDHtmlDialog::DestroyModeless](../Topic/CDHtmlDialog::DestroyModeless.md)|Détruit une boîte de dialogue non modale.|  
|[CDHtmlDialog::EnableModeless](../Topic/CDHtmlDialog::EnableModeless.md)|Active les boîtes de dialogue non modale.|  
|[CDHtmlDialog::FilterDataObject](../Topic/CDHtmlDialog::FilterDataObject.md)|Permet la boîte de dialogue des objets de données du Presse\-papiers de filtre créés par le navigateur hébergé.|  
|[CDHtmlDialog::GetControlDispatch](../Topic/CDHtmlDialog::GetControlDispatch.md)|Récupère l'interface d' `IDispatch` sur un contrôle ActiveX incorporé dans le document HTML.|  
|[CDHtmlDialog::GetControlProperty](../Topic/CDHtmlDialog::GetControlProperty.md)|Récupère la propriété demandée du contrôle ActiveX spécifié.|  
|[CDHtmlDialog::GetCurrentUrl](../Topic/CDHtmlDialog::GetCurrentUrl.md)|Récupère l'URL \(URL\) associé au document actif.|  
|[CDHtmlDialog::GetDHtmlDocument](../Topic/CDHtmlDialog::GetDHtmlDocument.md)|Récupère l'interface IHTMLDocument2 sur le document HTML actuellement chargé.|  
|[CDHtmlDialog::GetDropTarget](../Topic/CDHtmlDialog::GetDropTarget.md)|Appelé par le contrôle contenu WebBrowser lorsqu'il est utilisé comme cible de déplacement pour permettre au dialogue pour fournir autre [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679).|  
|[CDHtmlDialog::GetElement](../Topic/CDHtmlDialog::GetElement.md)|Obtient une interface d'un élément HTML.|  
|[CDHtmlDialog::GetElementHtml](../Topic/CDHtmlDialog::GetElementHtml.md)|Récupère la propriété d' **innerHTML** d'un élément HTML.|  
|[CDHtmlDialog::GetElementInterface](../Topic/CDHtmlDialog::GetElementInterface.md)|Récupère le pointeur d'interface demandé d'un élément HTML.|  
|[CDHtmlDialog::GetElementProperty](../Topic/CDHtmlDialog::GetElementProperty.md)|Récupère la valeur de la propriété d'un élément HTML.|  
|[CDHtmlDialog::GetElementText](../Topic/CDHtmlDialog::GetElementText.md)|Récupère la propriété d' **innerText** d'un élément HTML.|  
|[CDHtmlDialog::GetEvent](../Topic/CDHtmlDialog::GetEvent.md)|Obtient le pointeur d' **IHTMLEventObj** à l'objet d'événement actuel.|  
|[CDHtmlDialog::GetExternal](../Topic/CDHtmlDialog::GetExternal.md)|Obtient l'interface d' `IDispatch` de l'hôte.|  
|[CDHtmlDialog::GetHostInfo](../Topic/CDHtmlDialog::GetHostInfo.md)|Récupère les fonctionnalités de l'interface utilisateur de l'hôte.|  
|[CDHtmlDialog::GetOptionKeyPath](../Topic/CDHtmlDialog::GetOptionKeyPath.md)|Extrait la clé de Registre sous lequel les préférences de l'utilisateur sont stockées.|  
|[CDHtmlDialog::HideUI](../Topic/CDHtmlDialog::HideUI.md)|Masque l'interface utilisateur de l'hôte.|  
|[CDHtmlDialog::IsExternalDispatchSafe](../Topic/CDHtmlDialog::IsExternalDispatchSafe.md)|Indique si l'interface d' `IDispatch` de l'hôte est sûre pour le script.|  
|[CDHtmlDialog::LoadFromResource](../Topic/CDHtmlDialog::LoadFromResource.md)|Charge la ressource spécifiée dans le contrôle WebBrowser.|  
|[CDHtmlDialog::Navigate](../Topic/CDHtmlDialog::Navigate.md)|Accède à l'URL spécifiée.|  
|[CDHtmlDialog::OnBeforeNavigate](../Topic/CDHtmlDialog::OnBeforeNavigate.md)|Appelé par l'infrastructure avant un événement de navigation est déclenché.|  
|[CDHtmlDialog::OnDocumentComplete](../Topic/CDHtmlDialog::OnDocumentComplete.md)|Appelé par l'infrastructure pour indiquer une application lorsqu'un document a atteint l'état d' `READYSTATE_COMPLETE` .|  
|[CDHtmlDialog::OnDocWindowActivate](../Topic/CDHtmlDialog::OnDocWindowActivate.md)|Appelé par l'infrastructure lorsque la fenêtre de document est activée ou désactivée.|  
|[CDHtmlDialog::OnFrameWindowActivate](../Topic/CDHtmlDialog::OnFrameWindowActivate.md)|Appelé par l'infrastructure lorsque la fenêtre frame est activée ou désactivée.|  
|[CDHtmlDialog::OnInitDialog](../Topic/CDHtmlDialog::OnInitDialog.md)|Appelé en réponse à **WM\_INITDIALOG** le message.|  
|[CDHtmlDialog::OnNavigateComplete](../Topic/CDHtmlDialog::OnNavigateComplete.md)|Appelé par l'infrastructure après un événement de navigation est terminé.|  
|[CDHtmlDialog::ResizeBorder](../Topic/CDHtmlDialog::ResizeBorder.md)|Signale l'objet qu'il doit redimensionner son espace de bordure.|  
|[CDHtmlDialog::SetControlProperty](../Topic/CDHtmlDialog::SetControlProperty.md)|Définit la propriété d'un contrôle ActiveX à une nouvelle valeur.|  
|[CDHtmlDialog::SetElementHtml](../Topic/CDHtmlDialog::SetElementHtml.md)|Définit la propriété d' **innerHTML** d'un élément HTML.|  
|[CDHtmlDialog::SetElementProperty](../Topic/CDHtmlDialog::SetElementProperty.md)|Définit une propriété d'un élément HTML.|  
|[CDHtmlDialog::SetElementText](../Topic/CDHtmlDialog::SetElementText.md)|Définit la propriété d' **innerText** d'un élément HTML.|  
|[CDHtmlDialog::SetExternalDispatch](../Topic/CDHtmlDialog::SetExternalDispatch.md)|Définit l'interface d' `IDispatch` de l'hôte.|  
|[CDHtmlDialog::SetHostFlags](../Topic/CDHtmlDialog::SetHostFlags.md)|Définit les balises de l'interface utilisateur de l'hôte.|  
|[CDHtmlDialog::ShowContextMenu](../Topic/CDHtmlDialog::ShowContextMenu.md)|Appelé lorsqu'un menu contextuel est sur le point d'être affiché.|  
|[CDHtmlDialog::ShowUI](../Topic/CDHtmlDialog::ShowUI.md)|Affiche l'interface utilisateur de l'hôte.|  
|[CDHtmlDialog::TranslateAccelerator](../Topic/CDHtmlDialog::TranslateAccelerator.md)|Appelé pour traiter des messages de touche accélérateur de menu.|  
|[CDHtmlDialog::TranslateUrl](../Topic/CDHtmlDialog::TranslateUrl.md)|Appelé pour modifier l'URL à charger.|  
|[CDHtmlDialog::UpdateUI](../Topic/CDHtmlDialog::UpdateUI.md)|Appelé pour informer l'hôte que l'état de commande a changé.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDHtmlDialog::m\_bUseHtmlTitle](../Topic/CDHtmlDialog::m_bUseHtmlTitle.md)|Indique s'il faut utiliser le titre du document HTML comme légende de dialogue.|  
|[CDHtmlDialog::m\_nHtmlResID](../Topic/CDHtmlDialog::m_nHtmlResID.md)|ID de ressource de ressources HTML à afficher.|  
|[CDHtmlDialog::m\_pBrowserApp](../Topic/CDHtmlDialog::m_pBrowserApp.md)|Un pointeur vers une application de navigateur web.|  
|[CDHtmlDialog::m\_spHtmlDoc](../Topic/CDHtmlDialog::m_spHtmlDoc.md)|Un pointeur vers un document HTML.|  
|[CDHtmlDialog::m\_strCurrentUrl](../Topic/CDHtmlDialog::m_strCurrentUrl.md)|L'URL actuel.|  
|[CDHtmlDialog::m\_szHtmlResID](../Topic/CDHtmlDialog::m_szHtmlResID.md)|Version de chaîne de l'ID de ressource HTML|  
  
## Notes  
 **CDHtmlDialog** peut charger le HTML à afficher pour une ressource HTML ou d'une URL.  
  
 `CDHtmlDialog` peut également faire l'échange de données avec des contrôles HTML et gérez les événements des contrôles HTML, tels que les clics de bouton.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDHtmlSinkHandlerBase2`  
  
 `CDHtmlSinkHandlerBase1`  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDHtmlSinkHandler`  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDHtmlEventSink`  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CDHtmlDialog`  
  
## Configuration requise  
 **Header:** afxdhtml.h  
  
## Voir aussi  
 [MFC exemple DHtmlExplore](../../top/visual-cpp-samples.md)   
 [DDX\_DHtml Helper Macros](../../mfc/reference/ddx-dhtml-helper-macros.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)