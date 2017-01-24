---
title: "CHtmlView, classe | Microsoft Docs"
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
  - "CHtmlView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "navigateurs, prise en charge MFC pour"
  - "CHtmlView, classe"
  - "WebBrowser (contrôle)"
  - "Contrôle WebBrowser, prise en charge MFC"
ms.assetid: 904976af-73de-4aba-84ac-cfae8e2be09a
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHtmlView, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités du contrôle WebBrowser dans le contexte de l'architecture document\/vue de MFC.  
  
## Syntaxe  
  
```  
class CHtmlView : public CFormView  
```  
  
## Membres  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CHtmlView::Create](../Topic/CHtmlView::Create.md)|Crée le contrôle WebBrowser.|  
|[CHtmlView::CreateControlSite](../Topic/CHtmlView::CreateControlSite.md)|Méthode substituable permettant de créer une instance de site de contrôle pour héberger un contrôle sur le formulaire.|  
|[CHtmlView::ExecFormsCommand](../Topic/CHtmlView::ExecFormsCommand.md)|Exécute la commande spécifiée à l’aide de la méthode `IOleCommandTarget::Exec`.|  
|[CHtmlView::ExecWB](../Topic/CHtmlView::ExecWB.md)|Exécute une commande.|  
|[CHtmlView::GetAddressBar](../Topic/CHtmlView::GetAddressBar.md)|Détermine si la barre d’adresse de l’objet Internet Explorer est visible. \(Contrôle WebBrowser ignoré ; Internet Explorer uniquement.\)|  
|[CHtmlView::GetApplication](../Topic/CHtmlView::GetApplication.md)|Récupère un objet application représentant l’application qui contient l’instance actuelle de l’application Internet Explorer.|  
|[CHtmlView::GetBusy](../Topic/CHtmlView::GetBusy.md)|Récupère une valeur indiquant si un téléchargement ou une autre activité est toujours en cours.|  
|[CHtmlView::GetContainer](../Topic/CHtmlView::GetContainer.md)|Récupère le conteneur du contrôle WebBrowser.|  
|[CHtmlView::GetFullName](../Topic/CHtmlView::GetFullName.md)|Récupère le nom complet, notamment le chemin, de la ressource affichée dans le navigateur web. \(Contrôle WebBrowser ignoré ; Internet Explorer uniquement.\)|  
|[CHtmlView::GetFullScreen](../Topic/CHtmlView::GetFullScreen.md)|Indique si le contrôle WebBrowser fonctionne en mode Plein écran ou en mode Fenêtre normal.|  
|[CHtmlView::GetHeight](../Topic/CHtmlView::GetHeight.md)|Récupère la hauteur de la fenêtre principale d’Internet Explorer.|  
|[CHtmlView::GetHtmlDocument](../Topic/CHtmlView::GetHtmlDocument.md)|Récupère le document HTML actif.|  
|[CHtmlView::GetLeft](../Topic/CHtmlView::GetLeft.md)|Récupère les coordonnées d’écran du bord gauche de la fenêtre principale d’Internet Explorer.|  
|[CHtmlView::GetLocationName](../Topic/CHtmlView::GetLocationName.md)|Récupère le nom de la ressource actuellement affichée par WebBrowser.|  
|[CHtmlView::GetLocationURL](../Topic/CHtmlView::GetLocationURL.md)|Récupère l’URL de la ressource actuellement affichée par WebBrowser.|  
|[CHtmlView::GetMenuBar](../Topic/CHtmlView::GetMenuBar.md)|Récupère une valeur qui détermine si la barre de menus est visible.|  
|[CHtmlView::GetOffline](../Topic/CHtmlView::GetOffline.md)|Récupère une valeur qui détermine si le contrôle est hors connexion.|  
|[CHtmlView::GetParentBrowser](../Topic/CHtmlView::GetParentBrowser.md)|Récupère un pointeur vers l’interface `IDispatch`. Pour plus d'informations, consultez [Implementing the IDispatch Interface](http://msdn.microsoft.com/fr-fr/0e171f7f-0022-4e9b-ac8e-98192828e945).|  
|[CHtmlView::GetProperty](../Topic/CHtmlView::GetProperty.md)|Récupère la valeur actuelle d’une propriété associée à l’objet donné.|  
|[CHtmlView::GetReadyState](../Topic/CHtmlView::GetReadyState.md)|Récupère l’état Prêt de l’objet WebBrowser.|  
|[CHtmlView::GetRegisterAsBrowser](../Topic/CHtmlView::GetRegisterAsBrowser.md)|Indique si le contrôle WebBrowser est inscrit en tant que navigateur de niveau supérieur pour la résolution de nom cible.|  
|[CHtmlView::GetRegisterAsDropTarget](../Topic/CHtmlView::GetRegisterAsDropTarget.md)|Indique si le contrôle WebBrowser est inscrit en tant que cible de déplacement pour la navigation.|  
|[CHtmlView::GetSilent](../Topic/CHtmlView::GetSilent.md)|Indique si les boîtes de dialogue peuvent être affichées.|  
|[CHtmlView::GetSource](../Topic/CHtmlView::GetSource.md)|Code source HTML de la page web.|  
|[CHtmlView::GetStatusBar](../Topic/CHtmlView::GetStatusBar.md)|Indique si la barre d’état d’Internet Explorer est visible. \(Contrôle WebBrowser ignoré ; Internet Explorer uniquement.\)|  
|[CHtmlView::GetTheaterMode](../Topic/CHtmlView::GetTheaterMode.md)|Indique si le contrôle WebBrowser est en mode Cinéma.|  
|[CHtmlView::GetToolBar](../Topic/CHtmlView::GetToolBar.md)|Récupère une valeur qui détermine si la barre d’outils est visible.|  
|[CHtmlView::GetTop](../Topic/CHtmlView::GetTop.md)|Récupère les coordonnées d’écran du bord supérieur de la fenêtre principale d’Internet Explorer.|  
|[CHtmlView::GetTopLevelContainer](../Topic/CHtmlView::GetTopLevelContainer.md)|Récupère une valeur indiquant si l’objet actuel est le conteneur de niveau supérieur du contrôle WebBrowser.|  
|[CHtmlView::GetType](../Topic/CHtmlView::GetType.md)|Récupère le nom de type de l’objet document.|  
|[CHtmlView::GetVisible](../Topic/CHtmlView::GetVisible.md)|Récupère une valeur indiquant si l’objet est visible ou masqué.|  
|[CHtmlView::GetWidth](../Topic/CHtmlView::GetWidth.md)|Récupère la largeur de la fenêtre principale d’Internet Explorer.|  
|[CHtmlView::GoBack](../Topic/CHtmlView::GoBack.md)|Accède à l’élément précédent de l’historique.|  
|[CHtmlView::GoForward](../Topic/CHtmlView::GoForward.md)|Accède à l’élément suivant de l’historique.|  
|[CHtmlView::GoHome](../Topic/CHtmlView::GoHome.md)|Accède à la page d’accueil ou de démarrage actuelle.|  
|[CHtmlView::GoSearch](../Topic/CHtmlView::GoSearch.md)|Accède à la page de recherche actuelle.|  
|[CHtmlView::LoadFromResource](../Topic/CHtmlView::LoadFromResource.md)|Charge une ressource dans le contrôle WebBrowser.|  
|[CHtmlView::Navigate](../Topic/CHtmlView::Navigate.md)|Accède à la ressource identifiée par une URL.|  
|[CHtmlView::Navigate2](../Topic/CHtmlView::Navigate2.md)|Accède à la ressource identifiée par une URL ou au fichier identifié par un chemin complet.|  
|[CHtmlView::OnBeforeNavigate2](../Topic/CHtmlView::OnBeforeNavigate2.md)|Appelé avant le début d’une navigation dans le WebBrowser donné \(sur un élément fenêtre ou multiframe\).|  
|[CHtmlView::OnCommandStateChange](../Topic/CHtmlView::OnCommandStateChange.md)|Appelé pour avertir une application que l’état activé d’une commande de navigateur web a changé.|  
|[CHtmlView::OnDocumentComplete](../Topic/CHtmlView::OnDocumentComplete.md)|Appelé pour avertir une application qu’un document a atteint l’état `READYSTATE_COMPLETE`.|  
|[CHtmlView::OnDocWindowActivate](../Topic/CHtmlView::OnDocWindowActivate.md)|Appelé à partir de l’implémentation Internet Explorer ou MSHTML de [IOleInPlaceActiveObject::OnDocWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms687281), qui avertit l’objet sur place actif que la fenêtre de document du conteneur est activée ou désactivée.|  
|[CHtmlView::OnDownloadBegin](../Topic/CHtmlView::OnDownloadBegin.md)|Appelé pour avertir une application qu’une opération de navigation commence.|  
|[CHtmlView::OnDownloadComplete](../Topic/CHtmlView::OnDownloadComplete.md)|Appelé quand une opération de navigation aboutit, est interrompue ou échoue.|  
|[CHtmlView::OnEnableModeless](../Topic/CHtmlView::OnEnableModeless.md)|Appelé pour activer ou désactiver les boîtes de dialogue non modales quand le conteneur crée ou détruit une boîte de dialogue modale.|  
|[CHtmlView::OnFilterDataObject](../Topic/CHtmlView::OnFilterDataObject.md)|Appelé sur l’hôte par Internet Explorer ou MSHTML pour permettre à l’hôte de remplacer un objet de données Internet Explorer ou MSHTML.|  
|[CHtmlView::OnFrameWindowActivate](../Topic/CHtmlView::OnFrameWindowActivate.md)|Appelé à partir de [IOleInPlaceActiveObject::OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969) pour avertir l’objet que la fenêtre frame de niveau supérieur est activée ou désactivée.|  
|[CHtmlView::OnFullScreen](../Topic/CHtmlView::OnFullScreen.md)|Appelé quand la propriété FullScreen est modifiée.|  
|[CHtmlView::OnGetDropTarget](../Topic/CHtmlView::OnGetDropTarget.md)|Appelé par Internet Explorer ou MSHTML quand il est utilisé comme cible de déplacement pour permettre à l’hôte de fournir un autre [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679).|  
|[CHtmlView::OnGetExternal](../Topic/CHtmlView::OnGetExternal.md)|Appelé par Internet Explorer ou MSHTML pour obtenir l’interface `IDispatch` de l’hôte.|  
|[CHtmlView::OnGetHostInfo](../Topic/CHtmlView::OnGetHostInfo.md)|Récupère les fonctionnalités d’interface utilisateur de l’hôte Internet Explorer ou MSHTML.|  
|[CHtmlView::OnGetOptionKeyPath](../Topic/CHtmlView::OnGetOptionKeyPath.md)|Retourne la clé de Registre sous laquelle Internet Explorer ou MSHTML stocke les préférences utilisateur.|  
|[CHtmlView::OnHideUI](../Topic/CHtmlView::OnHideUI.md)|Appelé quand Internet Explorer ou MSHTML supprime ses menus et barres d’outils.|  
|[CHtmlView::OnMenuBar](../Topic/CHtmlView::OnMenuBar.md)|Appelé quand la propriété MenuBar est modifiée.|  
|[CHtmlView::OnNavigateComplete2](../Topic/CHtmlView::OnNavigateComplete2.md)|Appelé après la fin d’une navigation vers un lien hypertexte \(sur un élément fenêtre ou multiframe\).|  
|[CHtmlView::OnNavigateError](../Topic/CHtmlView::OnNavigateError.md)|Appelé par l’infrastructure en cas d’échec de la navigation vers un lien hypertexte.|  
|[CHtmlView::OnNewWindow2](../Topic/CHtmlView::OnNewWindow2.md)|Appelé quand une fenêtre doit être créée pour afficher une ressource.|  
|[CHtmlView::OnProgressChange](../Topic/CHtmlView::OnProgressChange.md)|Appelé pour avertir une application que la progression d’une opération de téléchargement a été mise à jour.|  
|[CHtmlView::OnPropertyChange](../Topic/CHtmlView::OnPropertyChange.md)|Appelé pour avertir une application que la méthode [PutProperty](../Topic/CHtmlView::PutProperty.md) a modifié la valeur d’une propriété.|  
|[CHtmlView::OnQuit](../Topic/CHtmlView::OnQuit.md)|Appelé pour avertir une application que l’application Internet Explorer est prête à être fermée. \(S’applique uniquement à Internet Explorer\)|  
|[CHtmlView::OnResizeBorder](../Topic/CHtmlView::OnResizeBorder.md)|Appelé à partir de l’implémentation Internet Explorer ou MSHTML de [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053), qui alerte l’objet qu’il doit redimensionner son espace de bordure.|  
|[CHtmlView::OnShowContextMenu](../Topic/CHtmlView::OnShowContextMenu.md)|Appelé à partir d’Internet Explorer ou MSHTML quand il est sur le point d’afficher son menu contextuel.|  
|[CHtmlView::OnShowUI](../Topic/CHtmlView::OnShowUI.md)|Appelé avant que Internet Explorer ou MSHTML affiche ses menus et barres d’outils.|  
|[CHtmlView::OnStatusBar](../Topic/CHtmlView::OnStatusBar.md)|Appelé quand la propriété StatusBar est modifiée.|  
|[CHtmlView::OnStatusTextChange](../Topic/CHtmlView::OnStatusTextChange.md)|Appelé pour avertir une application que le texte de la barre d’état associée au contrôle WebBrowser a changé.|  
|[CHtmlView::OnTheaterMode](../Topic/CHtmlView::OnTheaterMode.md)|Appelé quand la propriété TheaterMode est modifiée.|  
|[CHtmlView::OnTitleChange](../Topic/CHtmlView::OnTitleChange.md)|Appelé pour avertir une application que le titre d’un document contenu dans le contrôle WebBrowser est disponible ou a été modifié.|  
|[CHtmlView::OnToolBar](../Topic/CHtmlView::OnToolBar.md)|Appelé quand la propriété ToolBar est modifiée.|  
|[CHtmlView::OnTranslateAccelerator](../Topic/CHtmlView::OnTranslateAccelerator.md)|Appelé par Internet Explorer ou MSHTML quand [IOleInPlaceActiveObject::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) ou [IOleControlSite::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756) est appelé pour traiter les messages de touche d’accès rapide de menu à partir de la file d’attente de messages du conteneur.|  
|[CHtmlView::OnTranslateUrl](../Topic/CHtmlView::OnTranslateUrl.md)|Appelé par Internet Explorer ou MSHTML pour permettre à l’hôte de modifier l’URL à charger.|  
|[CHtmlView::OnUpdateUI](../Topic/CHtmlView::OnUpdateUI.md)|Avertit l’hôte que l’état de la commande a changé.|  
|[CHtmlView::OnVisible](../Topic/CHtmlView::OnVisible.md)|Appelé quand la fenêtre du contrôle WebBrowser doit être affichée\/masquée.|  
|[CHtmlView::PutProperty](../Topic/CHtmlView::PutProperty.md)|Définit la valeur d’une propriété associée à l’objet donné.|  
|[CHtmlView::QueryFormsCommand](../Topic/CHtmlView::QueryFormsCommand.md)|Demande l’état d’une ou plusieurs commandes générées par des événements d’interface utilisateur.|  
|[CHtmlView::QueryStatusWB](../Topic/CHtmlView::QueryStatusWB.md)|Demande l’état d’une commande actuellement traitée par le contrôle WebBrowser.|  
|[CHtmlView::Refresh](../Topic/CHtmlView::Refresh.md)|Recharge le fichier actif.|  
|[CHtmlView::Refresh2](../Topic/CHtmlView::Refresh2.md)|Recharge le fichier actif et empêche éventuellement l’envoi de l’en\-tête `pragma:nocache`.|  
|[CHtmlView::SetAddressBar](../Topic/CHtmlView::SetAddressBar.md)|Affiche ou masque la barre d’adresse de l’objet Internet Explorer. \(Contrôle WebBrowser ignoré ; Internet Explorer uniquement.\)|  
|[CHtmlView::SetFullScreen](../Topic/CHtmlView::SetFullScreen.md)|Définit une valeur pour déterminer si le contrôle fonctionne en mode Plein écran ou en mode Fenêtre normal. \(Contrôle WebBrowser ignoré ; Internet Explorer uniquement.\)|  
|[CHtmlView::SetHeight](../Topic/CHtmlView::SetHeight.md)|Définit la hauteur de la fenêtre principale d’Internet Explorer.|  
|[CHtmlView::SetLeft](../Topic/CHtmlView::SetLeft.md)|Définit la position horizontale de la fenêtre principale d’Internet Explorer.|  
|[CHtmlView::SetMenuBar](../Topic/CHtmlView::SetMenuBar.md)|Définit une valeur pour déterminer si la barre de menus du contrôle est visible. \(Contrôle WebBrowser ignoré ; Internet Explorer uniquement.\)|  
|[CHtmlView::SetOffline](../Topic/CHtmlView::SetOffline.md)|Définit une valeur pour déterminer si le contrôle est hors connexion.|  
|[CHtmlView::SetRegisterAsBrowser](../Topic/CHtmlView::SetRegisterAsBrowser.md)|Définit une valeur indiquant si le contrôle WebBrowser est inscrit en tant que navigateur de niveau supérieur pour la résolution de nom cible.|  
|[CHtmlView::SetRegisterAsDropTarget](../Topic/CHtmlView::SetRegisterAsDropTarget.md)|Définit une valeur indiquant si le contrôle WebBrowser est inscrit en tant que cible de déplacement pour la navigation.|  
|[CHtmlView::SetSilent](../Topic/CHtmlView::SetSilent.md)|Définit une valeur pour déterminer si le contrôle affiche les boîtes de dialogue.|  
|[CHtmlView::SetStatusBar](../Topic/CHtmlView::SetStatusBar.md)|Définit une valeur pour déterminer si la barre d’état d’Internet Explorer est visible. \(Contrôle WebBrowser ignoré ; Internet Explorer uniquement.\)|  
|[CHtmlView::SetTheaterMode](../Topic/CHtmlView::SetTheaterMode.md)|Définit une valeur indiquant si le contrôle WebBrowser est en mode Cinéma.|  
|[CHtmlView::SetToolBar](../Topic/CHtmlView::SetToolBar.md)|Définit une valeur pour déterminer si la barre d’outils du contrôle est visible. \(Contrôle WebBrowser ignoré ; Internet Explorer uniquement.\)|  
|[CHtmlView::SetTop](../Topic/CHtmlView::SetTop.md)|Définit la position verticale de la fenêtre principale d’Internet Explorer.|  
|[CHtmlView::SetVisible](../Topic/CHtmlView::SetVisible.md)|Définit une valeur indiquant si l’objet est visible ou masqué.|  
|[CHtmlView::SetWidth](../Topic/CHtmlView::SetWidth.md)|Définit la largeur de la fenêtre principale d’Internet Explorer.|  
|[CHtmlView::Stop](../Topic/CHtmlView::Stop.md)|Arrête l’ouverture d’un fichier.|  
  
## Notes  
 Le contrôle WebBrowser est une fenêtre dans laquelle l’utilisateur peut parcourir les sites du World Wide Web, ainsi que des dossiers dans le système de fichiers local et sur un réseau. Le contrôle WebBrowser prend en charge les liens hypertexte, la navigation par URL \(Uniform Resource Locator\) et tient à jour un historique.  
  
## Utilisation de la classe CHtmlView dans une application MFC  
 Dans l’application d’infrastructure MFC standard \(basée sur SDI ou MDI\), l’objet de vue dérive fréquemment d’un ensemble de classes spécialisé. Ces classes, toutes dérivées de `CView`, fournissent des fonctionnalités spécialisées au\-delà de celles fournies par `CView`.  
  
 En basant la classe de vue de l’application sur `CHtmlView`, la vue est fournie avec le contrôle WebBrowser. Cela fait effectivement de l’application un navigateur web. La méthode recommandée pour créer une application de type navigateur web consiste à utiliser l’Assistant Application MFC et à spécifier `CHtmlView` comme classe de vue. Pour plus d’informations sur l’implémentation et l’utilisation du contrôle WebBrowser dans les applications MFC, consultez [Création d’une application de type navigateur web](../../mfc/reference/creating-a-web-browser-style-mfc-application.md).  
  
> [!NOTE]
>  Le contrôle ActiveX WebBrowser \(et par conséquent `CHtmlView`\) est accessible uniquement aux programmes s’exécutant sur Windows NT version 4.0 ou ultérieure avec Internet Explorer 4.0 ou version ultérieure installé.  
  
 `CHtmlView` a été conçu pour les applications qui accèdent au web \(et\/ou documents HTML\). Les fonctions membres `CHtmlView` suivantes s’appliquent uniquement à l’application Internet Explorer. Même si ces fonctions aboutissent sur le contrôle WebBrowser, elles n’ont aucun effet visible.  
  
-   [GetAddressBar](../Topic/CHtmlView::GetAddressBar.md)  
  
-   [GetFullName](../Topic/CHtmlView::GetFullName.md)  
  
-   [GetStatusBar](../Topic/CHtmlView::GetStatusBar.md)  
  
-   [GetAddressBar](../Topic/CHtmlView::SetAddressBar.md)  
  
-   [SetFullScreen](../Topic/CHtmlView::SetFullScreen.md)  
  
-   [SetMenuBar](../Topic/CHtmlView::SetMenuBar.md)  
  
-   [SetStatusBar](../Topic/CHtmlView::SetStatusBar.md)  
  
-   [SetToolBar](../Topic/CHtmlView::SetToolBar.md)  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CHtmlView`  
  
## Configuration requise  
 **En\-tête :** afxhtml.h  
  
## Voir aussi  
 [MFC, exemple MFCIE](../../top/visual-cpp-samples.md)   
 [CFormView Class](../../mfc/reference/cformview-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [IWebBrowser2](https://msdn.microsoft.com/en-us/library/aa752127.aspx)