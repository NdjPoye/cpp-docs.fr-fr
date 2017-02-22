---
title: "CPaneFrameWnd Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPaneFrameWnd.Serialize"
  - "CPaneFrameWnd.PreTranslateMessage"
  - "CPaneFrameWnd"
  - "CPaneFrameWnd::Serialize"
  - "PreTranslateMessage"
  - "CPaneFrameWnd::PreTranslateMessage"
  - "Serialize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPaneFrameWnd class"
  - "PreTranslateMessage method"
  - "Serialize method"
ms.assetid: ea3423a3-2763-482e-b763-817036ded10d
caps.latest.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# CPaneFrameWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Implémente une fenêtre mini\-frame qui contient un volet.  Le volet remplit la zone cliente de la fenêtre.  
  
## Syntaxe  
  
```  
class CPaneFrameWnd : public CWnd  
```  
  
## Membres  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPaneFrameWnd::AddPane](../Topic/CPaneFrameWnd::AddPane.md)|Ajoute un volet.|  
|[CPaneFrameWnd::AddRemovePaneFromGlobalList](../Topic/CPaneFrameWnd::AddRemovePaneFromGlobalList.md)|Ajoute ou supprime un volet de la liste globale.|  
|[CPaneFrameWnd::AdjustLayout](../Topic/CPaneFrameWnd::AdjustLayout.md)|Ajuste la disposition de la fenêtre mini\-frame.|  
|[CPaneFrameWnd::AdjustPaneFrames](../Topic/CPaneFrameWnd::AdjustPaneFrames.md)||  
|[CPaneFrameWnd::CalcBorderSize](../Topic/CPaneFrameWnd::CalcBorderSize.md)|Calcule la taille des bordures d'une fenêtre mini\-frame.|  
|[CPaneFrameWnd::CalcExpectedDockedRect](../Topic/CPaneFrameWnd::CalcExpectedDockedRect.md)|Calcule le rectangle attendu d'une fenêtre ancrée.|  
|[CPaneFrameWnd::CanBeAttached](../Topic/CPaneFrameWnd::CanBeAttached.md)|Détermine si le volet actif peut être ancré à un autre volet ou à une fenêtre frame.|  
|[CPaneFrameWnd::CanBeDockedToPane](../Topic/CPaneFrameWnd::CanBeDockedToPane.md)|Détermine si la fenêtre mini\-frame peut être ancrée à un volet.|  
|[CPaneFrameWnd::CheckGripperVisibility](../Topic/CPaneFrameWnd::CheckGripperVisibility.md)||  
|[CPaneFrameWnd::ConvertToTabbedDocument](../Topic/CPaneFrameWnd::ConvertToTabbedDocument.md)|Convertit le volet en document à onglets.|  
|[CPaneFrameWnd::Create](../Topic/CPaneFrameWnd::Create.md)|Crée une fenêtre mini\-frame et l'attache à l'objet `CPaneFrameWnd`.|  
|[CPaneFrameWnd::CreateEx](../Topic/CPaneFrameWnd::CreateEx.md)|Crée une fenêtre mini\-frame et l'attache à l'objet `CPaneFrameWnd`.|  
|[CPaneFrameWnd::DockPane](../Topic/CPaneFrameWnd::DockPane.md)|Ancre le volet.|  
|[CPaneFrameWnd::FindFloatingPaneByID](../Topic/CPaneFrameWnd::FindFloatingPaneByID.md)|Recherche un volet à partir de l'ID de contrôle spécifié dans la liste globale des volets flottants.|  
|[CPaneFrameWnd::FrameFromPoint](../Topic/CPaneFrameWnd::FrameFromPoint.md)|Recherche la fenêtre mini\-frame contenant un point fourni par l'utilisateur.|  
|[CPaneFrameWnd::GetCaptionHeight](../Topic/CPaneFrameWnd::GetCaptionHeight.md)|Retourne la hauteur de la légende de fenêtre mini\-frame.|  
|[CPaneFrameWnd::GetCaptionRect](../Topic/CPaneFrameWnd::GetCaptionRect.md)|Calcule le rectangle englobant d'une légende de fenêtre mini\-frame.|  
|[CPaneFrameWnd::GetCaptionText](../Topic/CPaneFrameWnd::GetCaptionText.md)|Retourne le texte de légende.|  
|[CPaneFrameWnd::GetDockingManager](../Topic/CPaneFrameWnd::GetDockingManager.md)||  
|[CPaneFrameWnd::GetDockingMode](../Topic/CPaneFrameWnd::GetDockingMode.md)|Retourne le mode d'ancrage.|  
|[CPaneFrameWnd::GetFirstVisiblePane](../Topic/CPaneFrameWnd::GetFirstVisiblePane.md)|Retourne le premier volet visible contenu dans une fenêtre mini\-frame.|  
|[CPaneFrameWnd::GetHotPoint](../Topic/CPaneFrameWnd::GetHotPoint.md)||  
|[CPaneFrameWnd::GetPane](../Topic/CPaneFrameWnd::GetPane.md)|Retourne un volet contenu dans la fenêtre mini\-frame.|  
|[CPaneFrameWnd::GetPaneCount](../Topic/CPaneFrameWnd::GetPaneCount.md)|Retourne le nombre de volets contenus dans une fenêtre mini\-frame.|  
|[CPaneFrameWnd::GetParent](../Topic/CPaneFrameWnd::GetParent.md)||  
|[CPaneFrameWnd::GetPinState](../Topic/CPaneFrameWnd::GetPinState.md)||  
|[CPaneFrameWnd::GetRecentFloatingRect](../Topic/CPaneFrameWnd::GetRecentFloatingRect.md)||  
|[CPaneFrameWnd::GetVisiblePaneCount](../Topic/CPaneFrameWnd::GetVisiblePaneCount.md)|Retourne le nombre de volets visibles contenus dans une fenêtre mini\-frame.|  
|[CPaneFrameWnd::HitTest](../Topic/CPaneFrameWnd::HitTest.md)|Détermine la partie d'une fenêtre mini\-frame qui se trouve à un point donné.|  
|[CPaneFrameWnd::IsCaptured](../Topic/CPaneFrameWnd::IsCaptured.md)||  
|[CPaneFrameWnd::IsDelayShow](../Topic/CPaneFrameWnd::IsDelayShow.md)||  
|[CPaneFrameWnd::IsRollDown](../Topic/CPaneFrameWnd::IsRollDown.md)|Détermine si une fenêtre mini\-frame doit être masquée.|  
|[CPaneFrameWnd::IsRollUp](../Topic/CPaneFrameWnd::IsRollUp.md)|Détermine si une fenêtre mini\-frame doit être affichée.|  
|[CPaneFrameWnd::KillDockingTimer](../Topic/CPaneFrameWnd::KillDockingTimer.md)|Arrête le minuteur d'ancrage.|  
|[CPaneFrameWnd::LoadState](../Topic/CPaneFrameWnd::LoadState.md)|Charge l'état du volet à partir du Registre.|  
|[CPaneFrameWnd::OnBeforeDock](../Topic/CPaneFrameWnd::OnBeforeDock.md)|Détermine si l'ancrage est possible.|  
|[CPaneFrameWnd::OnDockToRecentPos](../Topic/CPaneFrameWnd::OnDockToRecentPos.md)|Ancre la fenêtre mini\-frame à sa dernière position.|  
|[CPaneFrameWnd::OnKillRollUpTimer](../Topic/CPaneFrameWnd::OnKillRollUpTimer.md)|Arrête le minuteur d'affichage.|  
|[CPaneFrameWnd::OnMovePane](../Topic/CPaneFrameWnd::OnMovePane.md)|Déplace la fenêtre mini\-frame selon un décalage spécifié.|  
|[CPaneFrameWnd::OnPaneRecalcLayout](../Topic/CPaneFrameWnd::OnPaneRecalcLayout.md)|Ajuste la disposition d'un volet contenu.|  
|[CPaneFrameWnd::OnSetRollUpTimer](../Topic/CPaneFrameWnd::OnSetRollUpTimer.md)|Définit le minuteur d'affichage.|  
|[CPaneFrameWnd::OnShowPane](../Topic/CPaneFrameWnd::OnShowPane.md)|Appelé par l'infrastructure quand un volet de la fenêtre mini\-frame est masqué ou affiché.|  
|[CPaneFrameWnd::PaneFromPoint](../Topic/CPaneFrameWnd::PaneFromPoint.md)|Retourne un volet s'il contient un point fourni par l'utilisateur à l'intérieur d'une fenêtre mini\-frame.|  
|[CPaneFrameWnd::Pin](../Topic/CPaneFrameWnd::Pin.md)||  
|`CPaneFrameWnd::PreTranslateMessage`|Utilisé par la classe [CWinApp](../../mfc/reference/cwinapp-class.md) pour traduire les messages de fenêtre avant d'être distribués aux fonctions Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).|  
|[CPaneFrameWnd::RedrawAll](../Topic/CPaneFrameWnd::RedrawAll.md)|Redessine toutes les fenêtres mini\-frame.|  
|[CPaneFrameWnd::RemoveNonValidPanes](../Topic/CPaneFrameWnd::RemoveNonValidPanes.md)|Appelé par l'infrastructure pour supprimer les volets non valides.|  
|[CPaneFrameWnd::RemovePane](../Topic/CPaneFrameWnd::RemovePane.md)|Supprime un volet de la fenêtre mini\-frame.|  
|[CPaneFrameWnd::ReplacePane](../Topic/CPaneFrameWnd::ReplacePane.md)|Remplace un volet par un autre.|  
|[CPaneFrameWnd::SaveState](../Topic/CPaneFrameWnd::SaveState.md)|Enregistre l'état du volet dans le Registre.|  
|`CPaneFrameWnd::Serialize`|Lit ou écrit cet objet dans une archive|  
|[CPaneFrameWnd::SetCaptionButtons](../Topic/CPaneFrameWnd::SetCaptionButtons.md)|Définit les boutons de légende.|  
|[CPaneFrameWnd::SetDelayShow](../Topic/CPaneFrameWnd::SetDelayShow.md)||  
|[CPaneFrameWnd::SetDockingManager](../Topic/CPaneFrameWnd::SetDockingManager.md)||  
|[CPaneFrameWnd::SetDockingTimer](../Topic/CPaneFrameWnd::SetDockingTimer.md)|Définit le minuteur d'ancrage.|  
|[CPaneFrameWnd::SetDockState](../Topic/CPaneFrameWnd::SetDockState.md)|Définit l'état d'ancrage.|  
|[CPaneFrameWnd::SetHotPoint](../Topic/CPaneFrameWnd::SetHotPoint.md)||  
|[CPaneFrameWnd::SetPreDockState](../Topic/CPaneFrameWnd::SetPreDockState.md)|Appelé par l'infrastructure pour définir l'état de pré\-ancrage.|  
|[CPaneFrameWnd::SizeToContent](../Topic/CPaneFrameWnd::SizeToContent.md)|Ajuste une fenêtre mini\-frame de sorte qu'elle ait une taille équivalente à celle d'un volet contenu.|  
|[CPaneFrameWnd::StartTearOff](../Topic/CPaneFrameWnd::StartTearOff.md)|Détache un menu.|  
|[CPaneFrameWnd::StoreRecentDockSiteInfo](../Topic/CPaneFrameWnd::StoreRecentDockSiteInfo.md)||  
|[CPaneFrameWnd::StoreRecentTabRelatedInfo](../Topic/CPaneFrameWnd::StoreRecentTabRelatedInfo.md)||  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CPaneFrameWnd::OnCheckRollState](../Topic/CPaneFrameWnd::OnCheckRollState.md)|Détermine si une fenêtre mini\-frame doit être masquée ou affichée.|  
|[CPaneFrameWnd::OnDrawBorder](../Topic/CPaneFrameWnd::OnDrawBorder.md)|Dessine les bordures d'une fenêtre mini\-frame.|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CPaneFrameWnd::m\_bUseSaveBits](../Topic/CPaneFrameWnd::m_bUseSaveBits.md)|Spécifie si la classe de fenêtre doit être inscrite avec le style de classe `CS_SAVEBITS`.|  
  
## Notes  
 L'infrastructure crée automatiquement un objet `CPaneFrameWnd` quand un volet passe de l'état ancré à l'état flottant.  
  
 Vous pouvez faire glisser une fenêtre mini\-frame avec son contenu visible \(ancrage immédiat\) ou en utilisant un rectangle de glissement \(ancrage standard\).  Le mode d'ancrage du volet conteneur du mini\-frame détermine le comportement de glissement du mini\-frame.  Pour plus d'informations, consultez [CBasePane::GetDockingMode](../Topic/CBasePane::GetDockingMode.md).  
  
 Une fenêtre mini\-frame présente des boutons sur la légende en fonction du style du volet contenu.  Si le volet peut être fermé \([CBasePane::CanBeClosed](../Topic/CBasePane::CanBeClosed.md)\), il présente un bouton Fermer.  Si le volet a la style `AFX_CBRS_AUTO_ROLLUP`, il affiche une épingle.  
  
 Si vous faites dériver une classe de `CPaneFrameWnd`, vous devez indiquer à l'infrastructure comment la créer.  Créez la classe en substituant [CPane::CreateDefaultMiniframe](../Topic/CPane::CreateDefaultMiniframe.md) ou définissez le membre `CPane::m_pMiniFrameRTC` de telle sorte qu'il pointe vers les informations de classe runtime correspondant à votre classe.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)  
  
## Configuration requise  
 **En\-tête :** afxPaneFrameWnd.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)