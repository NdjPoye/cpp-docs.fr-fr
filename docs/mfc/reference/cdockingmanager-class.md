---
title: "CDockingManager Class | Microsoft Docs"
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
  - "CDockingManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDockingManager class"
ms.assetid: 98e69c43-55d8-4f43-b861-4fda80ec1e32
caps.latest.revision: 37
caps.handback.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDockingManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente la fonctionnalité principale qui contrôle la disposition d'ancrage dans une fenêtre frame principale.  
  
## Syntaxe  
  
```  
class CDockingManager : public CObject  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDockingManager::AddDockSite](../Topic/CDockingManager::AddDockSite.md)|Crée un volet d'ancrage et l'ajoute à la liste des barres de contrôles.|  
|[CDockingManager::AddHiddenMDITabbedBar](../Topic/CDockingManager::AddHiddenMDITabbedBar.md)|Ajoute un handle d'un volet de barre à la liste des volets de barre tabulés masqués par MDI.|  
|[CDockingManager::AddMiniFrame](../Topic/CDockingManager::AddMiniFrame.md)|Ajoute un frame à la liste de mini frames.|  
|[CDockingManager::AddPane](../Topic/CDockingManager::AddPane.md)|Enregistre un volet avec le gestionnaire d'ancrage.|  
|[CDockingManager::AdjustDockingLayout](../Topic/CDockingManager::AdjustDockingLayout.md)|Recalcule et ajuste la disposition de tous les volets dans une fenêtre frame.|  
|[CDockingManager::AdjustPaneFrames](../Topic/CDockingManager::AdjustPaneFrames.md)|Entraîne l'affichage du message d' `WM_NCCALCSIZE` d'être envoyé à tous les volets et fenêtres d' `CPaneFrameWnd` .|  
|[CDockingManager::AdjustRectToClientArea](../Topic/CDockingManager::AdjustRectToClientArea.md)|Règle l'alignement d'un rectangle.|  
|[CDockingManager::AlignAutoHidePane](../Topic/CDockingManager::AlignAutoHidePane.md)|Redimensionne un volet d'ancrage masquer automatiquement dans la vue afin qu'il prenne la largeur ou la hauteur de la zone cliente du frame délimitée par des sites d'ancrage.|  
|[CDockingManager::AutoHidePane](../Topic/CDockingManager::AutoHidePane.md)|Crée une barre d'outils de masquer automatiquement.|  
|[CDockingManager::BringBarsToTop](../Topic/CDockingManager::BringBarsToTop.md)|Apporte les barres ancrées qui ont l'alignement spécifié en haut.|  
|[CDockingManager::BuildPanesMenu](../Topic/CDockingManager::BuildPanesMenu.md)|Ajoute des noms des volets d'ancrage et des barres d'outils à un menu.|  
|[CDockingManager::CalcExpectedDockedRect](../Topic/CDockingManager::CalcExpectedDockedRect.md)|Calcule le rectangle attendu d'une fenêtre ancrée.|  
|[CDockingManager::Create](../Topic/CDockingManager::Create.md)|Crée un gestionnaire d'ancrage.|  
|[CDockingManager::DeterminePaneAndStatus](../Topic/CDockingManager::DeterminePaneAndStatus.md)|Détermine le volet qui contient un point donné et son mode d'ancrage.|  
|[CDockingManager::DisableRestoreDockState](../Topic/CDockingManager::DisableRestoreDockState.md)|Active ou désactive le chargement de la disposition d'ancrage du Registre.|  
|[CDockingManager::DockPane](../Topic/CDockingManager::DockPane.md)|Ancre un volet à un autre volet ou à une fenêtre frame.|  
|[CDockingManager::DockPaneLeftOf](../Topic/CDockingManager::DockPaneLeftOf.md)|Ancre un volet gauche d'un autre volet.|  
|[CDockingManager::EnableAutoHidePanes](../Topic/CDockingManager::EnableAutoHidePanes.md)|Active l'ancrage du volet au frame principal, crée un volet d'ancrage, et l'ajoute à la liste des barres de contrôles.|  
|[CDockingManager::EnableDocking](../Topic/CDockingManager::EnableDocking.md)|Crée un volet d'ancrage et permet l'ancrage du volet au frame principal.|  
|[CDockingManager::EnableDockSiteMenu](../Topic/CDockingManager::EnableDockSiteMenu.md)|Affiche un bouton supplémentaire qui ouvre un menu contextuel sur les légendes de tous les volets d'ancrage.|  
|[CDockingManager::EnablePaneContextMenu](../Topic/CDockingManager::EnablePaneContextMenu.md)|Indique la bibliothèque pour afficher un menu contextuel spécial qui a une liste des barres d'outils et de volets d'ancrage d'application lorsque l'utilisateur clique sur le bouton droit de la souris et la bibliothèque traite le message de WM\_CONTEXTMENU.|  
|[CDockingManager::FindDockSite](../Topic/CDockingManager::FindDockSite.md)|Récupère le volet de barre qui est à la position spécifiée et qui a l'alignement spécifié.|  
|[CDockingManager::FindDockSiteByPane](../Topic/CDockingManager::FindDockSiteByPane.md)|Retourne le volet de barre qui a l'identificateur du volet cible de barre.|  
|[CDockingManager::FindPaneByID](../Topic/CDockingManager::FindPaneByID.md)|Recherche un volet spécifiée par l'ID de contrôle|  
|[CDockingManager::FixupVirtualRects](../Topic/CDockingManager::FixupVirtualRects.md)|Investit toutes les positions actuelles de barre d'outils à des rectangles virtuels.|  
|[CDockingManager::FrameFromPoint](../Topic/CDockingManager::FrameFromPoint.md)|Retourne le frame qui contient le point donné.|  
|[CDockingManager::GetClientAreaBounds](../Topic/CDockingManager::GetClientAreaBounds.md)|Obtient le rectangle qui contient les limites de la zone cliente.|  
|[CDockingManager::GetDockingMode](../Topic/CDockingManager::GetDockingMode.md)|Retourne l'état actuel d'ancrage.|  
|[CDockingManager::GetDockSiteFrameWnd](../Topic/CDockingManager::GetDockSiteFrameWnd.md)|Obtient un pointeur vers le frame de fenêtre parent.|  
|[CDockingManager::GetEnabledAutoHideAlignment](../Topic/CDockingManager::GetEnabledAutoHideAlignment.md)|Retourne l'alignement activé les volets.|  
|[CDockingManager::GetMiniFrames](../Topic/CDockingManager::GetMiniFrames.md)|Obtient une liste de miniframes.|  
|[CDockingManager::GetOuterEdgeBounds](../Topic/CDockingManager::GetOuterEdgeBounds.md)|Obtient un rectangle qui contient les bords externes du frame.|  
|[CDockingManager::GetPaneList](../Topic/CDockingManager::GetPaneList.md)|Retourne une liste des volets qui appartiennent au gestionnaire d'ancrage.  Cela inclut tous les volets flottants.|  
|[CDockingManager::GetSmartDockingManager](../Topic/CDockingManager::GetSmartDockingManager.md)|Extrait un pointeur intelligent au gestionnaire d'ancrage.|  
|[CDockingManager::GetSmartDockingManagerPermanent](../Topic/CDockingManager::GetSmartDockingManagerPermanent.md)|Extrait un pointeur intelligent au gestionnaire d'ancrage.|  
|[CDockingManager::GetSmartDockingParams](../Topic/CDockingManager::GetSmartDockingParams.md)|Retourne les paramètres intelligents d'ancrage de le gestionnaire d'ancrage.|  
|[CDockingManager::GetSmartDockingTheme](../Topic/CDockingManager::GetSmartDockingTheme.md)|Une méthode statique qui retourne un thème utilisé pour afficher le intelligentes d'ancrage.|  
|[CDockingManager::HideAutoHidePanes](../Topic/CDockingManager::HideAutoHidePanes.md)|Masque un volet qui est masquer automatiquement dans la vue.|  
|[CDockingManager::InsertDockSite](../Topic/CDockingManager::InsertDockSite.md)|Crée un volet d'ancrage et l'insère dans la liste des barres de contrôles.|  
|[CDockingManager::InsertPane](../Topic/CDockingManager::InsertPane.md)|Insère un volet de contrôle dans la liste des barres de contrôles.|  
|[CDockingManager::IsDockSiteMenu](../Topic/CDockingManager::IsDockSiteMenu.md)|Spécifie si un menu contextuel s'affiche sur les légendes de tous les volets.|  
|[CDockingManager::IsInAdjustLayout](../Topic/CDockingManager::IsInAdjustLayout.md)|Détermine si les dispositions de tous les volets sont définies.|  
|[CDockingManager::IsOLEContainerMode](../Topic/CDockingManager::IsOLEContainerMode.md)|Spécifie si le gestionnaire d'ancrage est en mode de conteneur OLE.|  
|[CDockingManager::IsPointNearDockSite](../Topic/CDockingManager::IsPointNearDockSite.md)|Détermine si un point spécifié est vers le site d'ancrage.|  
|[CDockingManager::IsPrintPreviewValid](../Topic/CDockingManager::IsPrintPreviewValid.md)|Détermine si le mode aperçu avant impression est défini.|  
|[CDockingManager::LoadState](../Topic/CDockingManager::LoadState.md)|Charge l'état du gestionnaire d'ancrage du Registre.|  
|[CDockingManager::LockUpdate](../Topic/CDockingManager::LockUpdate.md)|Verrouille la fenêtre donnée.|  
|[CDockingManager::OnActivateFrame](../Topic/CDockingManager::OnActivateFrame.md)|Appelé par l'infrastructure lorsque la fenêtre frame est rendue active ou est désactivée.|  
|[CDockingManager::OnClosePopupMenu](../Topic/CDockingManager::OnClosePopupMenu.md)|Appelé par l'infrastructure lorsqu'un menu contextuel actif traite un message de WM\_DESTROY.|  
|[CDockingManager::OnMoveMiniFrame](../Topic/CDockingManager::OnMoveMiniFrame.md)|Appelé par l'infrastructure pour déplacer une fenêtre mini\-frame.|  
|[CDockingManager::OnPaneContextMenu](../Topic/CDockingManager::OnPaneContextMenu.md)|Appelé par l'infrastructure lorsqu'il génère un menu qui contient une liste des volets.|  
|[CDockingManager::PaneFromPoint](../Topic/CDockingManager::PaneFromPoint.md)|Retourne le volet qui contient le point donné.|  
|[CDockingManager::ProcessPaneContextMenuCommand](../Topic/CDockingManager::ProcessPaneContextMenuCommand.md)|Appelé par l'infrastructure pour activer ou désactiver une case à cocher de la commande spécifiée et à recalculer la disposition d'un volet indiqué.|  
|[CDockingManager::RecalcLayout](../Topic/CDockingManager::RecalcLayout.md)|Recalcule la disposition interne des contrôles présents dans la liste de contrôles.|  
|[CDockingManager::ReleaseEmptyPaneContainers](../Topic/CDockingManager::ReleaseEmptyPaneContainers.md)|Libère les conteneurs vides de volet.|  
|[CDockingManager::RemoveHiddenMDITabbedBar](../Topic/CDockingManager::RemoveHiddenMDITabbedBar.md)|Supprime le volet masqué spécifié de barre.|  
|[CDockingManager::RemoveMiniFrame](../Topic/CDockingManager::RemoveMiniFrame.md)|Supprime un frame spécifié dans la liste de mini frames.|  
|[CDockingManager::RemovePaneFromDockManager](../Topic/CDockingManager::RemovePaneFromDockManager.md)|Annule l'inscription d'un volet et le supprimer de la liste dans le gestionnaire d'ancrage.|  
|[CDockingManager::ReplacePane](../Topic/CDockingManager::ReplacePane.md)|Remplace un volet par un autre.|  
|[CDockingManager::ResortMiniFramesForZOrder](../Topic/CDockingManager::ResortMiniFramesForZOrder.md)|Recourt les frames dans la liste de mini frames.|  
|[CDockingManager::SaveState](../Topic/CDockingManager::SaveState.md)|Enregistre l'état du gestionnaire d'ancrage au Registre.|  
|[CDockingManager::SendMessageToMiniFrames](../Topic/CDockingManager::SendMessageToMiniFrames.md)|Envoie le message spécifié à tous les frames mini.|  
|[CDockingManager::Serialize](../Topic/CDockingManager::Serialize.md)|Écrit le gestionnaire d'ancrage à une archive.  \(Substitutions [CObject::Serialize](../Topic/CObject::Serialize.md).\)|  
|[CDockingManager::SetAutohideZOrder](../Topic/CDockingManager::SetAutohideZOrder.md)|Définit la taille, la largeur, la hauteur des barres de contrôles et du volet spécifié.|  
|[CDockingManager::SetDockingMode](../Topic/CDockingManager::SetDockingMode.md)|Définit le mode d'ancrage.|  
|[CDockingManager::SetDockState](../Topic/CDockingManager::SetDockState.md)|Définit l'état d'ancrage les barres de contrôles, des mini frames, et les barres de masquer automatiquement.|  
|[CDockingManager::SetPrintPreviewMode](../Topic/CDockingManager::SetPrintPreviewMode.md)|Définit le mode aperçu avant impression des barres qui s'affichent dans l'aperçu avant impression.|  
|[CDockingManager::SetSmartDockingParams](../Topic/CDockingManager::SetSmartDockingParams.md)|Définit les paramètres qui définissent le comportement de l'ancrage intelligent.|  
|[CDockingManager::ShowDelayShowMiniFrames](../Topic/CDockingManager::ShowDelayShowMiniFrames.md)|Affiche ou masque les fenêtres des frames mini.|  
|[CDockingManager::ShowPanes](../Topic/CDockingManager::ShowPanes.md)|Affiche ou masque les volets du contrôle et masquer automatiquement des barres.|  
|[CDockingManager::StartSDocking](../Topic/CDockingManager::StartSDocking.md)|Démarre l'ancrage intelligent de la fenêtre spécifiée en fonction de l'alignement BITS du gestionnaire d'ancrage.|  
|[CDockingManager::StopSDocking](../Topic/CDockingManager::StopSDocking.md)|Arrête l'ancrage intelligent.|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CDockingManager::m\_bHideDockingBarsInContainerMode](../Topic/CDockingManager::m_bHideDockingBarsInContainerMode.md)|Spécifie si le gestionnaire d'ancrage masque les volets en mode de conteneur OLE.|  
|[CDockingManager::m\_dockModeGlobal](../Topic/CDockingManager::m_dockModeGlobal.md)|Spécifie le mode global d'ancrage.|  
|[CDockingManager::m\_nDockSensitivity](../Topic/CDockingManager::m_nDockSensitivity.md)|Spécifie le critère de distribution d'ancrage.|  
|[CDockingManager::m\_nTimeOutBeforeDockingBarDock](../Topic/CDockingManager::m_nTimeOutBeforeDockingBarDock.md)|Spécifie la durée, en millisecondes, avant qu'un volet d'ancrage est ancré en mode immédiat d'ancrage.|  
|[CDockingManager::m\_nTimeOutBeforeToolBarDock](../Topic/CDockingManager::m_nTimeOutBeforeToolBarDock.md)|Spécifie la durée, en millisecondes, avant qu'une barre d'outils est ancrée à la fenêtre frame principale.|  
  
## Notes  
 La fenêtre frame principale crée et initialise cette classe automatiquement.  
  
 L'objet de gestionnaire d'ancrage contient une liste de tous les volets qui sont dans la disposition d'ancrage, et également une liste de toutes les fenêtres de [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) qui appartiennent à la fenêtre frame principale.  
  
 La classe d' `CDockingManager` implémente des services que vous pouvez utiliser pour rechercher un volet ou une fenêtre d' `CPaneFrameWnd` .  Vous généralement n'appelez pas ces services directement car ils sont encapsulés dans l'objet de fenêtre frame principale.  Pour plus d'informations, consultez [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md).  
  
## Conseils de personnalisation  
 Les conseils suivants s'appliquent à `CDockingManager` des objets :  
  
-   [CDockingManager Class](../../mfc/reference/cdockingmanager-class.md) prend en charge ces modes d'ancrage :  
  
    -   `AFX_DOCK_TYPE::DT_IMMEDIATE`  
  
    -   `AFX_DOCK_TYPE::DT_STANDARD`  
  
    -   `AFX_DOCK_TYPE::DT_SMART`  
  
     Ces modes d'ancrage sont définis par [CDockingManager::m\_dockModeGlobal](../Topic/CDockingManager::m_dockModeGlobal.md) et sont définis en appelant [CDockingManager::SetDockingMode](../Topic/CDockingManager::SetDockingMode.md).  
  
-   Si vous souhaitez créer un volet flottant et non pas redimensionnable, appelez la méthode de [CDockingManager::AddPane](../Topic/CDockingManager::AddPane.md) .  Cette méthode signale le volet du gestionnaire d'ancrage, qui est responsable de la disposition du volet.  
  
## Exemple  
 L'exemple suivant montre comment utiliser différentes méthodes dans la classe d' `CDockingManager` pour configurer un objet d' `CDockingManager` .  L'exemple indique comment afficher un bouton supplémentaire qui ouvre un menu contextuel sur les légendes de tous les volets d'ancrage et comment définir le mode d'ancrage de l'objet.  Cet extrait de code fait partie d' [Exemple de démonstration de Visual Studio](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#24](../../mfc/codesnippet/CPP/cdockingmanager-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDockingManager](../../mfc/reference/cdockingmanager-class.md)  
  
## Configuration requise  
 **en\-tête :** afxDockingManager.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [CFrameWndEx Class](../../mfc/reference/cframewndex-class.md)   
 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)   
 [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md)