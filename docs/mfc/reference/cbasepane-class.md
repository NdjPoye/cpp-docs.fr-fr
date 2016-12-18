---
title: "CBasePane Class | Microsoft Docs"
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
  - "CBasePane::get_accKeyboardShortcut"
  - "CBasePane.get_accKeyboardShortcut"
  - "CBasePane.accSelect"
  - "get_accDefaultAction"
  - "accSelect"
  - "CBasePane.accHitTest"
  - "CBasePane.get_accRole"
  - "get_accKeyboardShortcut"
  - "CBasePane::Serialize"
  - "CBasePane"
  - "CBasePane::get_accDefaultAction"
  - "get_accParent"
  - "CBasePane::accSelect"
  - "accLocation"
  - "CBasePane.get_accDescription"
  - "get_accName"
  - "CBasePane::get_accChildCount"
  - "CBasePane.get_accChild"
  - "CBasePane::accHitTest"
  - "accHitTest"
  - "get_accHelp"
  - "CBasePane.get_accChildCount"
  - "CBasePane.get_accValue"
  - "CBasePane::get_accDescription"
  - "get_accChildCount"
  - "CBasePane.accLocation"
  - "CBasePane.PreTranslateMessage"
  - "CBasePane.get_accName"
  - "PreTranslateMessage"
  - "CBasePane::get_accFocus"
  - "get_accDescription"
  - "CBasePane::get_accRole"
  - "get_accValue"
  - "CBasePane.Serialize"
  - "CBasePane::accLocation"
  - "get_accRole"
  - "CBasePane::get_accChild"
  - "get_accFocus"
  - "CBasePane::get_accHelp"
  - "CBasePane.get_accDefaultAction"
  - "CBasePane.get_accHelp"
  - "CBasePane::PreTranslateMessage"
  - "CBasePane::get_accState"
  - "CBasePane.get_accParent"
  - "CBasePane::get_accParent"
  - "get_accChild"
  - "CBasePane::get_accValue"
  - "Serialize"
  - "get_accState"
  - "CBasePane.get_accState"
  - "CBasePane.get_accFocus"
  - "CBasePane::get_accName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "accHitTest method"
  - "accLocation method"
  - "accSelect method"
  - "CBasePane class"
  - "get_accChild method"
  - "get_accChildCount method"
  - "get_accDefaultAction method"
  - "get_accDescription method"
  - "get_accFocus method"
  - "get_accHelp method"
  - "get_accKeyboardShortcut method"
  - "get_accName method"
  - "get_accParent method"
  - "get_accRole method"
  - "get_accState method"
  - "get_accValue method"
  - "PreTranslateMessage method"
  - "Serialize method"
ms.assetid: 8163dd51-d7c7-4def-9c74-61f8ecdfad82
caps.latest.revision: 43
caps.handback.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBasePane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Classe de base pour tous les volets dans MFC.  
  
## Syntaxe  
  
```  
class CBasePane : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CBasePane::CBasePane`|Constructeur par défaut.|  
|`CBasePane::~CBasePane`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|`CBasePane::accHitTest`|Appelé par l'infrastructure pour récupérer l'élément enfant ou l'objet enfant à un point donné sur l'écran.  \(Substitutions [CWnd::accHitTest](../Topic/CWnd::accHitTest.md).\)|  
|`CBasePane::accLocation`|Appelé par l'infrastructure pour récupérer l'emplacement actuel d'écran pour l'objet spécifié.  \(Substitutions [CWnd::accLocation](../Topic/CWnd::accLocation.md).\)|  
|[CBasePane::AccNotifyObjectFocusEvent](../Topic/CBasePane::AccNotifyObjectFocusEvent.md)|`CBasePane` n'utilise pas cette méthode.|  
|`CBasePane::accSelect`|Appelé par l'infrastructure pour modifier la sélection ou pour déplacer le focus clavier de l'objet spécifié.  \(Substitutions [CWnd::accSelect](../Topic/CWnd::accSelect.md).\)|  
|[CBasePane::AddPane](../Topic/CBasePane::AddPane.md)|Ajoute un volet au gestionnaire d'ancrage.|  
|[CBasePane::AdjustDockingLayout](../Topic/CBasePane::AdjustDockingLayout.md)|Effectue un appel au gestionnaire d'ancrage pour ajuster la disposition d'ancrage.|  
|[CBasePane::AdjustLayout](../Topic/CBasePane::AdjustLayout.md)|Appelé par l'infrastructure lorsque le volet doit régler sa disposition interne.|  
|[CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md)|Calcule la taille horizontale d'une barre de contrôles.|  
|[CBasePane::CanAcceptPane](../Topic/CBasePane::CanAcceptPane.md)|Détermine si un autre volet peut être ancré au volet.|  
|[CBasePane::CanAutoHide](../Topic/CBasePane::CanAutoHide.md)|Détermine si le prend en charge du volet masquer automatiquement le mode.|  
|[CBasePane::CanBeAttached](../Topic/CBasePane::CanBeAttached.md)|Détermine si le volet peut être ancré à un autre volet.|  
|[CBasePane::CanBeClosed](../Topic/CBasePane::CanBeClosed.md)|Détermine si le volet peut être fermé.|  
|[CBasePane::CanBeDocked](../Topic/CBasePane::CanBeDocked.md)|Détermine si le volet peut être ancré à un autre volet.|  
|[CBasePane::CanBeResized](../Topic/CBasePane::CanBeResized.md)|Détermine si le volet peut être redimensionné.|  
|[CBasePane::CanBeTabbedDocument](../Topic/CBasePane::CanBeTabbedDocument.md)|Spécifie si le volet peut être converti en un document avec onglets MDI.|  
|[CBasePane::CanFloat](../Topic/CBasePane::CanFloat.md)|Détermine si le volet flottant peut.|  
|[CBasePane::CanFocus](../Topic/CBasePane::CanFocus.md)|Spécifie si le volet peut recevoir le focus.|  
|[CBasePane::CopyState](../Topic/CBasePane::CopyState.md)|Copie l'état d'un volet donné.|  
|[CBasePane::CreateDefaultMiniframe](../Topic/CBasePane::CreateDefaultMiniframe.md)|Si le volet flottant peut, crée une fenêtre mini\-frame.|  
|[CBasePane::CreateEx](../Topic/CBasePane::CreateEx.md)|Crée le contrôle de volet.|  
|[CBasePane::DockPane](../Topic/CBasePane::DockPane.md)|Ancre un volet à un autre volet ou à une fenêtre frame.|  
|[CBasePane::DockPaneUsingRTTI](../Topic/CBasePane::DockPaneUsingRTTI.md)|Ancre le volet à l'aide de les informations de type au moment de l'exécution.|  
|[CBasePane::DockToFrameWindow](../Topic/CBasePane::DockToFrameWindow.md)|Ancre un volet ancrable à un frame.|  
|[CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md)|Détermine si un autre volet peut être dynamiquement inséré entre ce volet et le frame parent.|  
|[CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md)|Active l'ancrage du volet au frame principal.|  
|[CBasePane::EnableGripper](../Topic/CBasePane::EnableGripper.md)|Active ou désactive la pince.  Si la pince est activée, l'utilisateur peut le faire glisser de repositionner le volet.|  
|`CBasePane::FillWindowRect`|Utilisé en interne.|  
|[CBasePane::FloatPane](../Topic/CBasePane::FloatPane.md)|Flotte le volet.|  
|`CBasePane::get_accChild`|Appelé par l'infrastructure pour récupérer l'adresse d'une interface d' `IDispatch` pour l'enfant spécifié.  \(Substitutions [CWnd::get\_accChild](../Topic/CWnd::get_accChild.md).\)|  
|`CBasePane::get_accChildCount`|Appelé par l'infrastructure pour récupérer le nombre d'enfants qui appartiennent à cet objet.  \(Substitutions [CWnd::get\_accChildCount](../Topic/CWnd::get_accChildCount.md).\)|  
|`CBasePane::get_accDefaultAction`|Appelé par l'infrastructure pour récupérer une chaîne qui décrit l'action par défaut pour l'objet.  \(Substitutions [CWnd::get\_accDefaultAction](../Topic/CWnd::get_accDefaultAction.md).\)|  
|`CBasePane::get_accDescription`|Appelé par l'infrastructure pour récupérer une chaîne qui décrit l'apparence visuelle de l'objet spécifié.  \(Substitutions [CWnd::get\_accDescription](../Topic/CWnd::get_accDescription.md).\)|  
|`CBasePane::get_accFocus`|Appelé par l'infrastructure pour récupérer l'objet qui a le focus clavier.  \(Substitutions [CWnd::get\_accFocus](../Topic/CWnd::get_accFocus.md).\)|  
|`CBasePane::get_accHelp`|Appelé par l'infrastructure pour récupérer une chaîne help de propriété pour l'objet.  \(Substitutions [CWnd::get\_accHelp](../Topic/CWnd::get_accHelp.md).\)|  
|[CBasePane::get\_accHelpTopic](../Topic/CBasePane::get_accHelpTopic.md)|Appelé par l'infrastructure pour récupérer le chemin d'accès complet duWinHelpfile associé à l'objet spécifié et l'identificateur de la rubrique appropriée dans ce fichier.  \(Substitutions [CWnd::get\_accHelpTopic](../Topic/CWnd::get_accHelpTopic.md).\)|  
|`CBasePane::get_accKeyboardShortcut`|Appelé par l'infrastructure pour récupérer la touche de raccourci spécifiée pour l'objet.  \(Substitutions [CWnd::get\_accKeyboardShortcut](../Topic/CWnd::get_accKeyboardShortcut.md).\)|  
|`CBasePane::get_accName`|Appelé par l'infrastructure pour extraire le nom de l'objet spécifié.  \(Substitutions [CWnd::get\_accName](../Topic/CWnd::get_accName.md).\)|  
|`CBasePane::get_accParent`|Appelé par l'infrastructure pour récupérer l'interface d' `IDispatch` pour le parent de l'objet.  \(Substitutions [CWnd::get\_accParent](../Topic/CWnd::get_accParent.md).\)|  
|`CBasePane::get_accRole`|Appelé par l'infrastructure pour récupérer des informations qui décrivent le rôle de l'objet spécifié.  \(Substitutions [CWnd::get\_accRole](../Topic/CWnd::get_accRole.md).\)|  
|[CBasePane::get\_accSelection](../Topic/CBasePane::get_accSelection.md)|Appelé par l'infrastructure pour récupérer les enfants sélectionnés de faire objet.  \(Substitutions [CWnd::get\_accSelection](../Topic/CWnd::get_accSelection.md).\)|  
|`CBasePane::get_accState`|Appelé par l'infrastructure pour récupérer l'état actuel de l'objet spécifié.  \(Substitutions [CWnd::get\_accState](../Topic/CWnd::get_accState.md).\)|  
|`CBasePane::get_accValue`|Appelé par l'infrastructure pour récupérer la valeur de l'objet spécifié.  \(Substitutions [CWnd::get\_accValue](../Topic/CWnd::get_accValue.md).\)|  
|[CBasePane::GetCaptionHeight](../Topic/CBasePane::GetCaptionHeight.md)|Retourne la hauteur de légende.|  
|[CBasePane::GetControlBarStyle](../Topic/CBasePane::GetControlBarStyle.md)|Retourne le style de barres de contrôles.|  
|[CBasePane::GetCurrentAlignment](../Topic/CBasePane::GetCurrentAlignment.md)|Retourne l'alignement actuel de volet.|  
|[CBasePane::GetDockingMode](../Topic/CBasePane::GetDockingMode.md)|Retourne l'état actuel d'ancrage de le volet.|  
|[CBasePane::GetDockSiteFrameWnd](../Topic/CBasePane::GetDockSiteFrameWnd.md)|Retourne un pointeur vers la fenêtre qui est le site d'ancrage du volet.|  
|[CBasePane::GetEnabledAlignment](../Topic/CBasePane::GetEnabledAlignment.md)|Retourne les styles de CBRS\_ALIGN\_ appliqués au volet.|  
|[CBasePane::GetMFCStyle](../Topic/CBasePane::GetMFCStyle.md)|Retourne les styles de volet propres à MFC.|  
|[CBasePane::GetPaneIcon](../Topic/CBasePane::GetPaneIcon.md)|Retourne un handle vers l'icône de volet.|  
|`CBasePane::GetPaneRect`|Utilisé en interne.|  
|[CBasePane::GetPaneRow](../Topic/CBasePane::GetPaneRow.md)|Retourne un pointeur vers l'objet de [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)où le volet est ancré.|  
|[CBasePane::GetPaneStyle](../Topic/CBasePane::GetPaneStyle.md)|Retourne le style de volet.|  
|[CBasePane::GetParentDockSite](../Topic/CBasePane::GetParentDockSite.md)|Retourne un pointeur vers le site parent d'ancrage.|  
|[CBasePane::GetParentMiniFrame](../Topic/CBasePane::GetParentMiniFrame.md)|Retourne un pointeur vers la fenêtre mini\-frame parente.|  
|[CBasePane::GetParentTabbedPane](../Topic/CBasePane::GetParentTabbedPane.md)|Retourne un pointeur vers le volet à onglets parent.|  
|[CBasePane::GetParentTabWnd](../Topic/CBasePane::GetParentTabWnd.md)|Retourne un pointeur vers la fenêtre parente qui est à l'intérieur d'une table.|  
|[CBasePane::GetRecentVisibleState](../Topic/CBasePane::GetRecentVisibleState.md)|L'infrastructure appelle cette méthode lorsqu'un volet est restauré d'une archive.|  
|[CBasePane::HideInPrintPreviewMode](../Topic/CBasePane::HideInPrintPreviewMode.md)|Spécifie si le volet est masqué dans l'aperçu avant impression.|  
|[CBasePane::InsertPane](../Topic/CBasePane::InsertPane.md)|Stocke le volet spécifié par le gestionnaire d'ancrage.|  
|[CBasePane::IsAccessibilityCompatible](../Topic/CBasePane::IsAccessibilityCompatible.md)|Spécifie si le volet prend en charge Active accessibilité.|  
|[CBasePane::IsAutoHideMode](../Topic/CBasePane::IsAutoHideMode.md)|Détermine si un volet est masquer automatiquement dans la vue.|  
|[CBasePane::IsDialogControl](../Topic/CBasePane::IsDialogControl.md)|Spécifie si le volet est un contrôle de boîte de dialogue.|  
|[CBasePane::IsDocked](../Topic/CBasePane::IsDocked.md)|Détermine si le volet est ancré.|  
|[CBasePane::IsFloating](../Topic/CBasePane::IsFloating.md)|Détermine si le volet flottant est.|  
|[CBasePane::IsHorizontal](../Topic/CBasePane::IsHorizontal.md)|Détermine si le volet est ancré horizontalement.|  
|[CBasePane::IsInFloatingMultiPaneFrameWnd](../Topic/CBasePane::IsInFloatingMultiPaneFrameWnd.md)|Spécifie si le volet est dans une fenêtre frame de plusieurs volet.|  
|[CBasePane::IsMDITabbed](../Topic/CBasePane::IsMDITabbed.md)|Détermine si le volet a été ajouté à une fenêtre MDI enfant comme document avec onglets.|  
|[CBasePane::IsPaneVisible](../Topic/CBasePane::IsPaneVisible.md)|Spécifie si la balise d' `WS_VISIBLE` est définie pour le volet.|  
|[CBasePane::IsPointNearDockSite](../Topic/CBasePane::IsPointNearDockSite.md)|Détermine si un point spécifié est vers le site d'ancrage.|  
|[CBasePane::IsResizable](../Topic/CBasePane::IsResizable.md)|Détermine si le volet peut être redimensionné.|  
|[CBasePane::IsRestoredFromRegistry](../Topic/CBasePane::IsRestoredFromRegistry.md)|Détermine si le volet est restauré du Registre.|  
|[CBasePane::IsTabbed](../Topic/CBasePane::IsTabbed.md)|Détermine si le volet a été inséré dans le contrôle onglet d'une fenêtre avec onglets.|  
|`CBasePane::IsTooltipTopmost`|Utilisé en interne.|  
|[CBasePane::IsVisible](../Topic/CBasePane::IsVisible.md)|Détermine si le volet est visible.|  
|[CBasePane::LoadState](../Topic/CBasePane::LoadState.md)|Charge l'état du volet du Registre.|  
|[CBasePane::MoveWindow](../Topic/CBasePane::MoveWindow.md)|Déplace le volet.|  
|[CBasePane::OnAfterChangeParent](../Topic/CBasePane::OnAfterChangeParent.md)|Appelé par l'infrastructure lorsque le parent du volet a été modifié.|  
|[CBasePane::OnBeforeChangeParent](../Topic/CBasePane::OnBeforeChangeParent.md)|Appelé par l'infrastructure juste avant le volet modifie sa fenêtre parente.|  
|[CBasePane::OnDrawCaption](../Topic/CBasePane::OnDrawCaption.md)|L'infrastructure appelle cette méthode lorsque la légende est dessinée.|  
|[CBasePane::OnMovePaneDivider](../Topic/CBasePane::OnMovePaneDivider.md)|Cette méthode n'est pas actuellement utilisée.|  
|[CBasePane::OnPaneContextMenu](../Topic/CBasePane::OnPaneContextMenu.md)|Appelé par l'infrastructure lorsqu'il génère un menu qui contient une liste des volets.|  
|[CBasePane::OnRemoveFromMiniFrame](../Topic/CBasePane::OnRemoveFromMiniFrame.md)|Appelé par l'infrastructure lorsqu'un volet est supprimé de sa mini fenêtre frame parente.|  
|[CBasePane::OnSetAccData](../Topic/CBasePane::OnSetAccData.md)|`CBasePane` n'utilise pas cette méthode.|  
|`CBasePane::OnUpdateCmdUI`|Utilisé en interne.|  
|[CBasePane::PaneFromPoint](../Topic/CBasePane::PaneFromPoint.md)|Retourne le volet qui contient le point donné.|  
|`CBasePane::PreTranslateMessage`|Utilisé par la classe [CWinApp](../../mfc/reference/cwinapp-class.md) pour convertir des messages de fenêtre pour qu'ils soient distribués aux fonctions Windows de [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et de [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) .  \(Substitutions [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).\)|  
|[CBasePane::RecalcLayout](../Topic/CBasePane::RecalcLayout.md)|`CBasePane` n'utilise pas cette méthode.|  
|[CBasePane::RemovePaneFromDockManager](../Topic/CBasePane::RemovePaneFromDockManager.md)|Annule l'inscription d'un volet et le supprimer de la liste dans le gestionnaire d'ancrage.|  
|[CBasePane::SaveState](../Topic/CBasePane::SaveState.md)|Enregistre l'état du volet au Registre.|  
|[CBasePane::SelectDefaultFont](../Topic/CBasePane::SelectDefaultFont.md)|Sélectionne la police par défaut pour un contexte donné de périphérique.|  
|`CBasePane::Serialize`|Lit ou écrit cet objet ou y retourne une archive.  \(Substitutions [CObject::Serialize](../Topic/CObject::Serialize.md).\)|  
|[CBasePane::SetControlBarStyle](../Topic/CBasePane::SetControlBarStyle.md)|Définit le style de barres de contrôles.|  
|[CBasePane::SetDockingMode](../Topic/CBasePane::SetDockingMode.md)|Définit le mode d'ancrage de le volet.|  
|`CBasePane::SetMDITabbed`|Utilisé en interne.|  
|[CBasePane::SetPaneAlignment](../Topic/CBasePane::SetPaneAlignment.md)|Définit l'alignement du volet.|  
|`CBasePane::SetPaneRect`|Utilisé en interne.|  
|[CBasePane::SetPaneStyle](../Topic/CBasePane::SetPaneStyle.md)|Définit le style du volet.|  
|`CBasePane::SetRestoredFromRegistry`|Utilisé en interne.|  
|[CBasePane::SetWindowPos](../Topic/CBasePane::SetWindowPos.md)|Modifie la taille, la position, et l'ordre de plan d'un volet.|  
|[CBasePane::ShowPane](../Topic/CBasePane::ShowPane.md)|Affiche ou masque le volet.|  
|[CBasePane::StretchPane](../Topic/CBasePane::StretchPane.md)|Étire un volet verticalement ou horizontalement.|  
|[CBasePane::UndockPane](../Topic/CBasePane::UndockPane.md)|Supprime le volet du site d'ancrage, du curseur par défaut, ou de la fenêtre mini\-frame où il est actuellement ancré.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CBasePane::DoPaint](../Topic/CBasePane::DoPaint.md)|Remplit l'arrière\-plan du volet.|  
  
## Notes  
 Si vous souhaitez créer une classe de volet qui prend en charge les fonctionnalités étendues d'ancrage disponibles dans MFC, vous devez le dériver d' `CBasePane` ou de [CPane Class](../../mfc/reference/cpane-class.md).  
  
## Conseils de personnalisation  
 Les conseils de personnalisation suivantes concernent [CBasePane Class](../../mfc/reference/cbasepane-class.md) et les classes qui héritent de celui\-ci :  
  
-   Lorsque vous créez un volet, vous pouvez appliquer plusieurs nouveaux styles :  
  
    -   `AFX_CBRS_FLOAT` fait le volet flottant.  
  
    -   `AFX_CBRS_AUTOHIDE` active masquer automatiquement le mode.  
  
    -   `AFX_CBRS_CLOSE` permet au volet d'être fermé \(masqué\).  
  
     Ce sont des balises que vous pouvez associer avec une opération de bits OR.  
  
     `CBasePane` implémente les méthodes virtuelles booléennes suivantes pour refléter ces balises : [CBasePane::CanBeClosed](../Topic/CBasePane::CanBeClosed.md), [CBasePane::CanAutoHide](../Topic/CBasePane::CanAutoHide.md), [CBasePane::CanFloat](../Topic/CBasePane::CanFloat.md).  Vous pouvez les substituer dans les classes dérivées de personnaliser leur comportement.  
  
-   Vous pouvez personnaliser le comportement d'ancrage en substituant [CBasePane::CanAcceptPane](../Topic/CBasePane::CanAcceptPane.md).  Ayez le retour `FALSE` de volet de cette méthode pour empêcher un autre volet d'ancrage lui.  
  
-   Si vous souhaitez créer un volet statique qui ne peut pas flottant et qui empêché tout autre volet d'ancrage avant lui \(similaire à la barre Outlook dans l'exemple OutlookDemo\), créez\- le comme non flottant et remplacez [CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md) pour retourner `FALSE`.  L'implémentation par défaut retourne `FALSE` si le volet est créé sans style d' `AFX_CBRS_FLOAT` .  
  
-   Créez tous les volets avec des identificateurs autres que \-1.  
  
-   Pour déterminer la visibilité de volet, utilisez [CBasePane::IsVisible](../Topic/CBasePane::IsVisible.md).  Il gère correctement l'état de visibilité dans l'onglet et masque automatiquement les modes.  
  
-   Si vous souhaitez créer un volet redimensionnable non flottant, créez\- le sans style d' `AFX_CBRS_FLOAT` et appelez [CFrameWnd::DockControlBar](../Topic/CFrameWnd::DockControlBar.md).  
  
-   Pour exclure un volet d'une disposition d'ancrage ou supprimer une barre d'outils de sa barre d'ancrage, appelez [CBasePane::UndockPane](../Topic/CBasePane::UndockPane.md).  N'appelez pas cette méthode pour les volets masquer automatiquement dans l'état ou pour les volets qui résident dans les onglets windows à onglet.  
  
-   Si vous souhaitez flottant ou détacher un volet qui est dans masquer automatiquement le mode, vous devez appeler [CDockablePane::SetAutoHideMode](../Topic/CDockablePane::SetAutoHideMode.md) avec `FALSE` que le premier argument avant d'appeler [CBasePane::FloatPane](../Topic/CBasePane::FloatPane.md) ou [CBasePane::UndockPane](../Topic/CBasePane::UndockPane.md).  
  
## Exemple  
 L'exemple suivant montre comment utiliser différentes méthodes dans la classe d' `CBasePane` .  L'exemple montre comment récupérer un volet de la classe d' `CFrameWndEx` et comment définir le mode d'ancrage, l'alignement de volet, et le style de volet.  Le code est d' [Exemple de protection de Word](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#2](../../mfc/reference/codesnippet/CPP/cbasepane-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
## Configuration requise  
 **en\-tête :** afxbasepane.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CPane](../../mfc/reference/cbasepane-class.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)