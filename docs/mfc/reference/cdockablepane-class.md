---
title: "CDockablePane Class | Microsoft Docs"
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
  - "CDockablePane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDockablePane class"
ms.assetid: e2495f4c-765f-48f9-a2e2-e45e47608d91
caps.latest.revision: 34
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDockablePane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente un volet qui peut être ancré dans un site d'ancrage ou être inclus dans un volet à onglets.  
  
## Syntaxe  
  
```  
class CDockablePane : public CPane  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDockablePane::CDockablePane](../Topic/CDockablePane::CDockablePane.md)|Les éléments et initialise un objet d' `CDockablePane` .|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDockablePane::AttachToTabWnd](../Topic/CDockablePane::AttachToTabWnd.md)|Joint un volet à un autre volet.  Cela crée un volet à onglets.|  
|[CDockablePane::CalcFixedLayout](../Topic/CDockablePane::CalcFixedLayout.md)|Retourne la taille du rectangle de volet.|  
|[CDockablePane::CanAcceptMiniFrame](../Topic/CDockablePane::CanAcceptMiniFrame.md)|Détermine si le mini frame spécifié peut être ancré au volet.|  
|[CDockablePane::CanAcceptPane](../Topic/CDockablePane::CanAcceptPane.md)|Détermine si un autre volet peut être ancré au volet actif.|  
|[CDockablePane::CanAutoHide](../Topic/CDockablePane::CanAutoHide.md)|Détermine si le prend en charge du volet masquer automatiquement le mode.  \(Substitutions [CBasePane::CanAutoHide](../Topic/CBasePane::CanAutoHide.md).\)|  
|[CDockablePane::CanBeAttached](../Topic/CDockablePane::CanBeAttached.md)|Détermine si le volet actuel peut être ancré à un autre volet.|  
|[CDockablePane::ConvertToTabbedDocument](../Topic/CDockablePane::ConvertToTabbedDocument.md)|Convertit un ou plusieurs volets ancrables aux documents avec onglet MDI.|  
|[CDockablePane::CopyState](../Topic/CDockablePane::CopyState.md)|Copie l'état d'un volet ancrable.|  
|[CDockablePane::Create](../Topic/CDockablePane::Create.md)|Crée le contrôle Windows et l'attache à l'objet d' `CDockablePane` .|  
|[CDockablePane::CreateDefaultPaneDivider](../Topic/CDockablePane::CreateDefaultPaneDivider.md)|Crée un diviseur par défaut du volet à mesure qu'il est ancré à une fenêtre frame.|  
|[CDockablePane::CreateEx](../Topic/CDockablePane::CreateEx.md)|Crée le contrôle Windows et l'attache à l'objet d' `CDockablePane` .|  
|[CDockablePane::CreateTabbedPane](../Topic/CDockablePane::CreateTabbedPane.md)|Crée un volet à onglets du volet actif.|  
|[CDockablePane::DockPaneContainer](../Topic/CDockablePane::DockPaneContainer.md)|Ancre un conteneur au volet.|  
|[CDockablePane::DockPaneStandard](../Topic/CDockablePane::DockPaneStandard.md)|Ancre un volet à l'aide de l'ancrage \(standard\) d'ensemble.|  
|`CDockablePane::DockToFrameWindow`|Utilisé en interne.  Pour ancrer un volet, l'utilisation [CPane::DockPane](../Topic/CPane::DockPane.md) ou un [CDockablePane::DockToWindow](../Topic/CDockablePane::DockToWindow.md).|  
|[CDockablePane::DockToRecentPos](../Topic/CDockablePane::DockToRecentPos.md)|Ancre un volet à sa position récente stockée d'ancrage.|  
|[CDockablePane::DockToWindow](../Topic/CDockablePane::DockToWindow.md)|S'ancre un volet d'ancrage à un autre volet d'ancrage.|  
|[CDockablePane::EnableAutohideAll](../Topic/CDockablePane::EnableAutohideAll.md)|Active ou désactive les masquer automatiquement le mode de ce volet avec d'autres volets dans le conteneur.|  
|[CDockablePane::EnableGripper](../Topic/CDockablePane::EnableGripper.md)|Affiche ou masque la légende pince \(\).|  
|[CDockablePane::GetAHRestoredRect](../Topic/CDockablePane::GetAHRestoredRect.md)|Spécifie la position du volet si visible masquer automatiquement dans la vue.|  
|[CDockablePane::GetAHSlideMode](../Topic/CDockablePane::GetAHSlideMode.md)|Récupère le mode automatique de diapositive de masquage du volet.|  
|`CDockablePane::GetAutoHideButton`|Utilisé en interne.|  
|`CDockablePane::GetAutoHideToolBar`|Utilisé en interne.|  
|[CDockablePane::GetCaptionHeight](../Topic/CDockablePane::GetCaptionHeight.md)|Retourne la hauteur de la légende active.|  
|[CDockablePane::GetDefaultPaneDivider](../Topic/CDockablePane::GetDefaultPaneDivider.md)|Retourne le diviseur par défaut du volet pour le conteneur du volet.|  
|[CDockablePane::GetDockingStatus](../Topic/CDockablePane::GetDockingStatus.md)|Détermine la capacité d'un volet d'être ancré en fonction de l'emplacement fourni de pointeur.|  
|[CDockablePane::GetDragSensitivity](../Topic/CDockablePane::GetDragSensitivity.md)|Retourne le critère de distribution de glisser\-déplacer d'un volet d'ancrage.|  
|[CDockablePane::GetLastPercentInPaneContainer](../Topic/CDockablePane::GetLastPercentInPaneContainer.md)|Récupère le pourcentage d'espace qu'un volet occupe dans son conteneur.|  
|[CDockablePane::GetTabArea](../Topic/CDockablePane::GetTabArea.md)|Extrait la zone d'onglet du volet.|  
|[CDockablePane::GetTabbedPaneRTC](../Topic/CDockablePane::GetTabbedPaneRTC.md)|Retourne les informations de classe d'exécution sur une fenêtre avec onglets qui est créé lorsqu'un autre volet s'ancre au volet actif.|  
|[CDockablePane::HasAutoHideMode](../Topic/CDockablePane::HasAutoHideMode.md)|Spécifie si à un volet d'ancrage peut être basculé masquer automatiquement le mode.|  
|[CDockablePane::HitTest](../Topic/CDockablePane::HitTest.md)|Spécifie l'emplacement spécifique dans un volet lorsque l'utilisateur clique sur une souris.|  
|`CDockablePane::IsAccessibilityCompatible`|Utilisé en interne.|  
|[CDockablePane::IsAutohideAllEnabled](../Topic/CDockablePane::IsAutohideAllEnabled.md)|Indique si le volet d'ancrage et tous les autres volets dans le conteneur peuvent être placés dans masquer automatiquement le mode.|  
|[CDockablePane::IsAutoHideMode](../Topic/CDockablePane::IsAutoHideMode.md)|Détermine si un volet est masquer automatiquement dans la vue.|  
|`CDockablePane::IsChangeState`|Utilisé en interne.|  
|[CDockablePane::IsDocked](../Topic/CDockablePane::IsDocked.md)|Détermine si le volet actif est ancré.|  
|[CDockablePane::IsHideInAutoHideMode](../Topic/CDockablePane::IsHideInAutoHideMode.md)|Détermine le comportement d'un volet qui est masquer automatiquement dans le mode s'il est affiché ou masqué \(\) en appelant `ShowPane`.|  
|[CDockablePane::IsInFloatingMultiPaneFrameWnd](../Topic/CDockablePane::IsInFloatingMultiPaneFrameWnd.md)|Spécifie si le volet est dans une fenêtre frame de plusieurs volet.|  
|[CDockablePane::IsResizable](../Topic/CDockablePane::IsResizable.md)|Spécifie si le volet est redimensionnable.|  
|[CDockablePane::IsTabLocationBottom](../Topic/CDockablePane::IsTabLocationBottom.md)|Spécifie si les onglets sont situés en haut ou en bas du volet.|  
|[CDockablePane::IsTracked](../Topic/CDockablePane::IsTracked.md)|Spécifie si un volet est déplacé par l'utilisateur.|  
|[CDockablePane::IsVisible](../Topic/CDockablePane::IsVisible.md)|Détermine si le volet actif est visible.|  
|[CDockablePane::LoadState](http://msdn.microsoft.com/fr-fr/96110136-4f46-4764-8a76-3b4abaf77917)|Utilisé en interne.|  
|[CDockablePane::OnAfterChangeParent](../Topic/CDockablePane::OnAfterChangeParent.md)|Appelé par l'infrastructure lorsque le parent d'un volet a changé.  \(Substitutions [CPane::OnAfterChangeParent](../Topic/CPane::OnAfterChangeParent.md).\)|  
|[CDockablePane::OnAfterDockFromMiniFrame](../Topic/CDockablePane::OnAfterDockFromMiniFrame.md)|Appelé par l'infrastructure lorsqu'une barre flottante d'ancrage s'ancre à une fenêtre frame.|  
|[CDockablePane::OnBeforeChangeParent](../Topic/CDockablePane::OnBeforeChangeParent.md)|Appelé par l'infrastructure lorsque le parent du volet est sur le point de modifier.  \(Substitutions [CPane::OnBeforeChangeParent](../Topic/CPane::OnBeforeChangeParent.md).\)|  
|[CDockablePane::OnBeforeFloat](../Topic/CDockablePane::OnBeforeFloat.md)|Appelé par l'infrastructure lorsqu'un volet est sur le point de flotter.  \(Substitutions [CPane::OnBeforeFloat](../Topic/CPane::OnBeforeFloat.md).\)|  
|[CDockablePane::RemoveFromDefaultPaneDividier](../Topic/CDockablePane::RemoveFromDefaultPaneDividier.md)|L'infrastructure appelle cette méthode lorsqu'un volet est détaché.|  
|[CDockablePane::ReplacePane](../Topic/CDockablePane::ReplacePane.md)|Remplace le volet avec un volet spécifié.|  
|[CDockablePane::RestoreDefaultPaneDivider](../Topic/CDockablePane::RestoreDefaultPaneDivider.md)|L'infrastructure appelle cette méthode comme un volet est désérialisé pour restaurer le diviseur par défaut de volet.|  
|`CDockablePane::SaveState`|Utilisé en interne.|  
|`CDockablePane::Serialize`|Sérialise le volet.  \(Substitutions `CBasePane::Serialize`.\)|  
|[CDockablePane::SetAutoHideMode](../Topic/CDockablePane::SetAutoHideMode.md)|Bascule le volet d'ancrage entre visible et masque automatiquement le mode.|  
|[CDockablePane::SetAutoHideParents](../Topic/CDockablePane::SetAutoHideParents.md)|Définit le bouton de masquer automatiquement et masque automatiquement la barre d'outils du volet.|  
|`CDockablePane::SetDefaultPaneDivider`|Utilisé en interne.|  
|[CDockablePane::SetLastPercentInPaneContainer](../Topic/CDockablePane::SetLastPercentInPaneContainer.md)|Définit le pourcentage d'espace qu'un volet occupe dans son conteneur.|  
|`CDockablePane::SetResizeMode`|Utilisé en interne.|  
|[CDockablePane::SetRestoredDefaultPaneDivider](../Topic/CDockablePane::SetRestoredDefaultPaneDivider.md)|Définit le diviseur par défaut restauré de volet.|  
|[CDockablePane::SetTabbedPaneRTC](../Topic/CDockablePane::SetTabbedPaneRTC.md)|Définit les informations de classe d'exécution d'une fenêtre avec onglets qui est créée lorsque deux volets les accueillent ensemble.|  
|[CDockablePane::ShowPane](../Topic/CDockablePane::ShowPane.md)|Affiche ou masque le volet.|  
|[CDockablePane::Slide](../Topic/CDockablePane::Slide.md)|Affiche ou masque le volet avec une animation de faire glisser ce qui affiche uniquement lorsque le volet est masquer automatiquement dans la vue.|  
|[CDockablePane::ToggleAutoHide](../Topic/CDockablePane::ToggleAutoHide.md)|Les bascule masquer automatiquement le mode.  \(Substitutions [CPane::ToggleAutoHide](../Topic/CPane::ToggleAutoHide.md) .\)|  
|[CDockablePane::UndockPane](../Topic/CDockablePane::UndockPane.md)|Détache un volet de la fenêtre frame principale ou d'un conteneur de fenêtre mini\-frame.|  
|`CDockablePane::UnSetAutoHideMode`|Utilisé en interne.  Pour définir le mode de masquer automatiquement, utilisez [CDockablePane::SetAutoHideMode](../Topic/CDockablePane::SetAutoHideMode.md)|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CDockablePane::CheckAutoHideCondition](../Topic/CDockablePane::CheckAutoHideCondition.md)|Détermine si le volet d'ancrage est masqué \(en masquer automatiquement le mode\).|  
|[CDockablePane::CheckStopSlideCondition](../Topic/CDockablePane::CheckStopSlideCondition.md)|Détermine si un volet d'ancrage de masquer automatiquement doit cesser de glisser.|  
|[CDockablePane::DrawCaption](../Topic/CDockablePane::DrawCaption.md)|Dessine la légende du volet d'ancrage pince \(\).|  
|[CDockablePane::OnPressButtons](../Topic/CDockablePane::OnPressButtons.md)|Appelé lorsque l'utilisateur appuie sur un bouton de légende autre que les boutons d' `AFX_HTCLOSE` et d' `AFX_HTMAXBUTTON` .|  
|[CDockablePane::OnSlide](../Topic/CDockablePane::OnSlide.md)|Appelé par l'infrastructure pour afficher l'effet de diapositive de masquer automatiquement lorsque le volet est affiché ou masqué.|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CDockablePane::m\_bDisableAnimation](../Topic/CDockablePane::m_bDisableAnimation.md)|Spécifie si masquer automatiquement l'animation du volet ancrable est désactivé.|  
|[CDockablePane::m\_bHideInAutoHideMode](../Topic/CDockablePane::m_bHideInAutoHideMode.md)|Détermine le comportement du volet lorsque le volet est masquer automatiquement dans la vue.|  
|[CDockablePane::m\_nSlideSteps](../Topic/CDockablePane::m_nSlideSteps.md)|Spécifie la vitesse d'animation du volet lorsqu'il est affiché ou masqué lorsque masquer automatiquement dans la vue.|  
  
## Notes  
 `CDockablePane` implémente les fonctionnalités suivantes :  
  
-   Ancrer un volet à une fenêtre frame principale.  
  
-   En basculant un volet à masquer automatiquement le mode.  
  
-   Liaison d'un volet à une fenêtre avec onglets.  
  
-   Flottant d'un volet dans une fenêtre mini\-frame.  
  
-   Un volet d'ancrage à un autre volet flottant qui est dans une fenêtre mini\-frame.  
  
-   Redimensionner un volet.  
  
-   État de chargement et d'enregistrement pour un volet d'ancrage.  
  
    > [!NOTE]
    >  Les informations d'état sont enregistrés dans le Registre Windows.  
  
-   Créer un volet avec ou sans légende.  La légende peut avoir une étiquette de texte et elle peut être remplie avec une couleur de dégradé.  
  
-   Faire glisser un volet en affichant le contenu du volet  
  
-   Faire glisser un volet en affichant un rectangle de glisser\-déplacer.  
  
 Pour utiliser un volet d'ancrage dans votre application, dérivez votre classe de volet de la classe d' `CDockablePane` .  Incluez l'objet dérivé dans l'objet de fenêtre frame principale ou dans un objet window qui contrôle l'instance de votre volet.  Appelez la méthode de [CDockablePane::Create](../Topic/CDockablePane::Create.md) ou la méthode de [CDockablePane::CreateEx](../Topic/CDockablePane::CreateEx.md) lorsque vous utilisez le message d' `WM_CREATE` dans la fenêtre frame principale.  Enfin, installez l'objet de volet en appelant [CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md), [CBasePane::DockPane](../Topic/CBasePane::DockPane.md), ou [CDockablePane::AttachToTabWnd](../Topic/CDockablePane::AttachToTabWnd.md).  
  
## Conseils de personnalisation  
 Les conseils suivants s'appliquent à `CDockablePane` des objets :  
  
-   Si vous appelez [CDockablePane::AttachToTabWnd](../Topic/CDockablePane::AttachToTabWnd.md) pour les deux volets avec onglets et non ancrables, un pointeur vers une fenêtre avec onglets est retourné dans le paramètre d' `ppTabbedControlBar` .  Vous pouvez continuer à ajouter des onglets à la fenêtre à onglets à l'aide de ce paramètre.  
  
-   Le type de volet à onglets qui est créé par [CDockablePane::AttachToTabWnd](../Topic/CDockablePane::AttachToTabWnd.md) est déterminé par l'objet d' `CDockablePane` dans le paramètre d' `pTabControlBarAttachTo` .  Vous pouvez appeler [CDockablePane::SetTabbedPaneRTC](../Topic/CDockablePane::SetTabbedPaneRTC.md) pour définir le type de volet à onglets qu' `CDockablePane` crée.  Le type par défaut est déterminé par `dwTabbedStyle` de [CDockablePane::Create](../Topic/CDockablePane::Create.md) lorsque vous commencez `CDockablePane`.  Si `dwTabbedStyle` est AFX\_CBRS\_OUTLOOK\_TABS le type par défaut est [CMFCOutlookBar, Classe](../../mfc/reference/cmfcoutlookbar-class.md); si `dwTabbedStyle` est AFX\_CBRS\_REGULAR\_TABS le type par défaut est [CTabbedPane Class](../../mfc/reference/ctabbedpane-class.md).  
  
-   Si vous souhaitez ancrer un volet ancrable à un autre, appelez la méthode de [CDockablePane::DockToWindow](../Topic/CDockablePane::DockToWindow.md) .  Le volet d'origine doit être ancré à un endroit avant d'appeler cette méthode.  
  
-   Les contrôles de [CDockablePane::m\_bHideInAutoHideMode](../Topic/CDockablePane::m_bHideInAutoHideMode.md) de variable membre comment les volets ancrables se comportent en mode de fonction masquer automatiquement lorsque vous appelez [CDockablePane::ShowPane](../Topic/CDockablePane::ShowPane.md).  Si cette variable membre est définie à `TRUE`, les volets ancrables et les boutons automatiques de masquer sont masqués.  Sinon, ils glisseront dans et.  
  
-   Vous pouvez désactiver masquer automatiquement l'animation en définissant la variable membre de [CDockablePane::m\_bDisableAnimation](../Topic/CDockablePane::m_bDisableAnimation.md) à `TRUE`.  
  
## Exemple  
 L'exemple suivant montre comment configurer un objet d' `CDockablePane` en utilisant différentes méthodes dans la classe d' `CDockablePane` .  L'exemple montre comment activer le masquer automatiquement toutes les fonctionnalités du volet ancrable, activer la légende ou la pince, activer le mode de masquer automatiquement, afficher le volet, et animer un volet qui est dans masquer automatiquement le mode.  Cet extrait de code fait partie d' [Exemple de démonstration de Visual Studio](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#27](../../mfc/codesnippet/CPP/cdockablepane-class_1.cpp)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#28](../../mfc/codesnippet/CPP/cdockablepane-class_2.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
## Configuration requise  
 **en\-tête :** afxDockablePane.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CPane Class](../../mfc/reference/cpane-class.md)