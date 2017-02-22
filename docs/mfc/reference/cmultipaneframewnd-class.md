---
title: "CMultiPaneFrameWnd Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMultiPaneFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMultiPaneFrameWnd class"
ms.assetid: 989a548e-0d70-46b7-a513-8cf740e1be3e
caps.latest.revision: 36
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 38
---
# CMultiPaneFrameWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMultiPaneFrameWnd` étend [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md).  Elle peut prendre en charge plusieurs volets.  Au lieu d'un handle incorporé à une barre de contrôles, `CMultiPaneFrameWnd` contient un objet de [CPaneContainerManager Class](../../mfc/reference/cpanecontainermanager-class.md) qui permet à l'utilisateur d'ancrer un `CMultiPaneFrameWnd` à une autre et de créer dynamiquement plusieurs flottant, fenêtres à onglet.  
  
## Syntaxe  
  
```  
class CMultiPaneFrameWnd : public CPaneFrameWnd  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMultiPaneFrameWnd::AddPane](../Topic/CMultiPaneFrameWnd::AddPane.md)|Ajoute un volet.  \(Substitutions [CPaneFrameWnd::AddPane](../Topic/CPaneFrameWnd::AddPane.md).\)|  
|[CMultiPaneFrameWnd::AddRecentPane](../Topic/CMultiPaneFrameWnd::AddRecentPane.md)||  
|[CMultiPaneFrameWnd::AdjustLayout](../Topic/CMultiPaneFrameWnd::AdjustLayout.md)|Règle la disposition de la fenêtre mini\-frame.  \(Substitutions [CPaneFrameWnd::AdjustLayout](../Topic/CPaneFrameWnd::AdjustLayout.md).\)|  
|[CMultiPaneFrameWnd::AdjustPaneFrames](../Topic/CMultiPaneFrameWnd::AdjustPaneFrames.md)|\(Substitutions [CPaneFrameWnd::AdjustPaneFrames](../Topic/CPaneFrameWnd::AdjustPaneFrames.md).\)|  
|[CMultiPaneFrameWnd::CalcExpectedDockedRect](../Topic/CMultiPaneFrameWnd::CalcExpectedDockedRect.md)|Calcule le rectangle attendu d'une fenêtre ancrée.  \(Substitutions [CPaneFrameWnd::CalcExpectedDockedRect](../Topic/CPaneFrameWnd::CalcExpectedDockedRect.md).\)|  
|[CMultiPaneFrameWnd::CanBeAttached](../Topic/CMultiPaneFrameWnd::CanBeAttached.md)|Détermine si le volet actuel peut l'ancrer à un volet ou une fenêtre frame différent.  \(Substitutions [CPaneFrameWnd::CanBeAttached](../Topic/CPaneFrameWnd::CanBeAttached.md).\)|  
|[CMultiPaneFrameWnd::CanBeDockedToPane](../Topic/CMultiPaneFrameWnd::CanBeDockedToPane.md)|Détermine si la fenêtre mini\-frame peut l'ancrer à un volet.  \(Substitutions [CPaneFrameWnd::CanBeDockedToPane](../Topic/CPaneFrameWnd::CanBeDockedToPane.md).\)|  
|[CMultiPaneFrameWnd::CheckGripperVisibility](../Topic/CMultiPaneFrameWnd::CheckGripperVisibility.md)|\(Substitutions [CPaneFrameWnd::CheckGripperVisibility](../Topic/CPaneFrameWnd::CheckGripperVisibility.md).\)|  
|[CMultiPaneFrameWnd::CloseMiniFrame](../Topic/CMultiPaneFrameWnd::CloseMiniFrame.md)|\(Substitutions `CPaneFrameWnd::CloseMiniFrame`.\)|  
|[CMultiPaneFrameWnd::ConvertToTabbedDocument](../Topic/CMultiPaneFrameWnd::ConvertToTabbedDocument.md)|Convertit le volet à un document avec onglets.  \(Substitutions [CPaneFrameWnd::ConvertToTabbedDocument](../Topic/CPaneFrameWnd::ConvertToTabbedDocument.md).\)|  
|[CMultiPaneFrameWnd::DockFrame](../Topic/CMultiPaneFrameWnd::DockFrame.md)||  
|[CMultiPaneFrameWnd::DockPane](../Topic/CMultiPaneFrameWnd::DockPane.md)|Ancre le volet.  \(Substitutions [CPaneFrameWnd::DockPane](../Topic/CPaneFrameWnd::DockPane.md).\)|  
|[CMultiPaneFrameWnd::DockRecentPaneToMainFrame](../Topic/CMultiPaneFrameWnd::DockRecentPaneToMainFrame.md)||  
|[CMultiPaneFrameWnd::GetCaptionText](../Topic/CMultiPaneFrameWnd::GetCaptionText.md)|Retourne le texte de légende.  \(Substitutions [CPaneFrameWnd::GetCaptionText](../Topic/CPaneFrameWnd::GetCaptionText.md).\)|  
|[CMultiPaneFrameWnd::GetPaneContainerManager](../Topic/CMultiPaneFrameWnd::GetPaneContainerManager.md)|Retourne une référence à l'objet interne du gestionnaire de conteneur.|  
|[CMultiPaneFrameWnd::GetFirstVisiblePane](../Topic/CMultiPaneFrameWnd::GetFirstVisiblePane.md)|Retourne le premier volet visible contenu dans une fenêtre mini\-frame.  \(Substitutions [CPaneFrameWnd::GetFirstVisiblePane](../Topic/CPaneFrameWnd::GetFirstVisiblePane.md).\)|  
|[CMultiPaneFrameWnd::GetPane](../Topic/CMultiPaneFrameWnd::GetPane.md)|Retourne un volet qui est contenu dans la fenêtre mini\-frame.  \(Substitutions [CPaneFrameWnd::GetPane](../Topic/CPaneFrameWnd::GetPane.md).\)|  
|[CMultiPaneFrameWnd::GetPaneCount](../Topic/CMultiPaneFrameWnd::GetPaneCount.md)|Retourne le nombre de volets qui sont contenus dans une fenêtre mini\-frame.  \(Substitutions [CPaneFrameWnd::GetPaneCount](../Topic/CPaneFrameWnd::GetPaneCount.md).\)|  
|[CMultiPaneFrameWnd::GetVisiblePaneCount](../Topic/CMultiPaneFrameWnd::GetVisiblePaneCount.md)|Retourne le nombre de volets visibles contenus dans une fenêtre mini\-frame.  \(Substitutions [CPaneFrameWnd::GetVisiblePaneCount](../Topic/CPaneFrameWnd::GetVisiblePaneCount.md).\)|  
|[CMultiPaneFrameWnd::InsertPane](../Topic/CMultiPaneFrameWnd::InsertPane.md)||  
|[CMultiPaneFrameWnd::LoadState](../Topic/CMultiPaneFrameWnd::LoadState.md)|Charge l'état du volet du Registre.  \(Substitutions [CPaneFrameWnd::LoadState](../Topic/CPaneFrameWnd::LoadState.md).\)|  
|[CMultiPaneFrameWnd::OnDockToRecentPos](../Topic/CMultiPaneFrameWnd::OnDockToRecentPos.md)|Ancre la fenêtre mini\-frame à sa position plus récente.  \(Substitutions [CPaneFrameWnd::OnDockToRecentPos](../Topic/CPaneFrameWnd::OnDockToRecentPos.md).\)|  
|[CMultiPaneFrameWnd::OnKillRollUpTimer](../Topic/CMultiPaneFrameWnd::OnKillRollUpTimer.md)|Arrête la minuterie de cumul.  \(Substitutions [CPaneFrameWnd::OnKillRollUpTimer](../Topic/CPaneFrameWnd::OnKillRollUpTimer.md).\)|  
|[CMultiPaneFrameWnd::OnPaneRecalcLayout](../Topic/CMultiPaneFrameWnd::OnPaneRecalcLayout.md)|Règle la disposition d'un volet dans une fenêtre mini\-frame.  \(Substitutions [CPaneFrameWnd::OnPaneRecalcLayout](../Topic/CPaneFrameWnd::OnPaneRecalcLayout.md).\)|  
|[CMultiPaneFrameWnd::OnSetRollUpTimer](../Topic/CMultiPaneFrameWnd::OnSetRollUpTimer.md)|Définit le délai de cumul.  \(Substitutions [CPaneFrameWnd::OnSetRollUpTimer](../Topic/CPaneFrameWnd::OnSetRollUpTimer.md).\)|  
|[CMultiPaneFrameWnd::OnShowPane](../Topic/CMultiPaneFrameWnd::OnShowPane.md)|Appelé par l'infrastructure lorsqu'un volet de la fenêtre mini\-frame est masqué ou affiche.  \(Substitutions [CPaneFrameWnd::OnShowPane](../Topic/CPaneFrameWnd::OnShowPane.md).\)|  
|[CMultiPaneFrameWnd::PaneFromPoint](../Topic/CMultiPaneFrameWnd::PaneFromPoint.md)|Retourne un volet s'il contient un point entré par l'utilisateur dans une fenêtre mini\-frame.  \(Substitutions [CPaneFrameWnd::PaneFromPoint](../Topic/CPaneFrameWnd::PaneFromPoint.md).\)|  
|[CMultiPaneFrameWnd::RemoveNonValidPanes](../Topic/CMultiPaneFrameWnd::RemoveNonValidPanes.md)|Appelé par l'infrastructure pour supprimer les volets non valides.  \(Substitutions [CPaneFrameWnd::RemoveNonValidPanes](../Topic/CPaneFrameWnd::RemoveNonValidPanes.md).\)|  
|[CMultiPaneFrameWnd::RemovePane](../Topic/CMultiPaneFrameWnd::RemovePane.md)|Supprime un volet de la fenêtre mini\-frame.  \(Substitutions [CPaneFrameWnd::RemovePane](../Topic/CPaneFrameWnd::RemovePane.md).\)|  
|[CMultiPaneFrameWnd::ReplacePane](../Topic/CMultiPaneFrameWnd::ReplacePane.md)|Remplace un volet par un autre.  \(Substitutions [CPaneFrameWnd::ReplacePane](../Topic/CPaneFrameWnd::ReplacePane.md).\)|  
|[CMultiPaneFrameWnd::SaveState](../Topic/CMultiPaneFrameWnd::SaveState.md)|Enregistre l'état du volet au Registre.  \(Substitutions [CPaneFrameWnd::SaveState](../Topic/CPaneFrameWnd::SaveState.md).\)|  
|[CMultiPaneFrameWnd::Serialize](../Topic/CMultiPaneFrameWnd::Serialize.md)|\(Substitutions `CPaneFrameWnd::Serialize`.\)|  
|[CMultiPaneFrameWnd::SetDockState](../Topic/CMultiPaneFrameWnd::SetDockState.md)|Définit l'état d'ancrage.  \(Substitutions [CPaneFrameWnd::SetDockState](../Topic/CPaneFrameWnd::SetDockState.md).\)|  
|[CMultiPaneFrameWnd::SetLastFocusedPane](../Topic/CMultiPaneFrameWnd::SetLastFocusedPane.md)||  
|[CMultiPaneFrameWnd::SetPreDockState](../Topic/CMultiPaneFrameWnd::SetPreDockState.md)|Définit l'état predocking.  \(Substitutions [CPaneFrameWnd::SetPreDockState](../Topic/CPaneFrameWnd::SetPreDockState.md).\)|  
|[CMultiPaneFrameWnd::StoreRecentDockSiteInfo](../Topic/CMultiPaneFrameWnd::StoreRecentDockSiteInfo.md)|\(Substitutions [CPaneFrameWnd::StoreRecentDockSiteInfo](../Topic/CPaneFrameWnd::StoreRecentDockSiteInfo.md).\)|  
|[CMultiPaneFrameWnd::StoreRecentTabRelatedInfo](../Topic/CMultiPaneFrameWnd::StoreRecentTabRelatedInfo.md)|\(Substitutions [CPaneFrameWnd::StoreRecentTabRelatedInfo](../Topic/CPaneFrameWnd::StoreRecentTabRelatedInfo.md).\)|  
  
## Notes  
 La plupart des méthodes dans substituez les méthodes de cette classe dans la classe de [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md) .  
  
 Si un volet utilise le style d' `AFX_CBRS_AUTO_ROLLUP` et les s'ancre d'utilisateur que le volet à une fenêtre frame de plusieurs volet, l'utilisateur peut enrouler la fenêtre quels que soient les paramètres de style les autres volets ancrés.  
  
 L'infrastructure crée automatiquement un objet d' `CMultiPaneFrameWnd` lorsque l'utilisateur flotte un volet qui utilise le style d' `CBRS_FLOAT_MULTI` .  
  
 Pour plus d'informations sur dériver une classe de la classe d' `CPaneFrameWnd` et la créer dynamiquement, consultez [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md).  
  
## Exemple  
 L'exemple suivant montre comment récupérer un pointeur vers un objet d' `CMultiPaneFrameWnd` .  Cet extrait de code fait partie de [Définissez l'exemple de taille du volet](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_SetPaneSize#4](../../mfc/reference/codesnippet/CPP/cmultipaneframewnd-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)  
  
 [CMultiPaneFrameWnd](../../mfc/reference/cmultipaneframewnd-class.md)  
  
## Configuration requise  
 **en\-tête :** afxMultiPaneFrameWnd.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md)