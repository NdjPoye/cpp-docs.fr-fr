---
title: "CMFCAutoHideBar Class | Microsoft Docs"
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
  - "CMFCAutoHideBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCAutoHideToolBar class"
ms.assetid: 54c8d84f-de64-4efd-8a47-3ea0ade40a70
caps.latest.revision: 35
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCAutoHideBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCAutoHideBar` est une classe de barre d'outils spéciale qui implémente la fonctionnalité de masquage automatique.  
  
## Syntaxe  
  
```  
class CMFCAutoHideBar : public CPane  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCAutoHideBar::CMFCAutoHideBar](../Topic/CMFCAutoHideBar::CMFCAutoHideBar.md)||  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCAutoHideBar::AddAutoHideWindow](../Topic/CMFCAutoHideBar::AddAutoHideWindow.md)||  
|[CMFCAutoHideBar::AllowShowOnPaneMenu](../Topic/CMFCAutoHideBar::AllowShowOnPaneMenu.md)|\(Substitue `CPane::AllowShowOnPaneMenu`.\)|  
|[CMFCAutoHideBar::CalcFixedLayout](../Topic/CMFCAutoHideBar::CalcFixedLayout.md)|\(Substitue [CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md).\)|  
|[CMFCAutoHideBar::Create](../Topic/CMFCAutoHideBar::Create.md)|Crée une barre de contrôle et l'attache à l'objet [CPane](../../mfc/reference/cpane-class.md).  \(Substitue [CPane::Create](../Topic/CPane::Create.md).\)|  
|[CMFCAutoHideBar::GetFirstAHWindow](../Topic/CMFCAutoHideBar::GetFirstAHWindow.md)||  
|[CMFCAutoHideBar::GetVisibleCount](../Topic/CMFCAutoHideBar::GetVisibleCount.md)||  
|[CMFCAutoHideBar::OnShowControlBarMenu](../Topic/CMFCAutoHideBar::OnShowControlBarMenu.md)|Appelé par l'infrastructure quand un menu de volet spécial va être affiché.  \(Substitue [CPane::OnShowControlBarMenu](../Topic/CPane::OnShowControlBarMenu.md).\)|  
|[CMFCAutoHideBar::RemoveAutoHideWindow](../Topic/CMFCAutoHideBar::RemoveAutoHideWindow.md)||  
|[CMFCAutoHideBar::SetActiveInGroup](../Topic/CMFCAutoHideBar::SetActiveInGroup.md)|\(Substitue [CPane::SetActiveInGroup](../Topic/CPane::SetActiveInGroup.md).\)|  
|[CMFCAutoHideBar::SetRecentVisibleState](../Topic/CMFCAutoHideBar::SetRecentVisibleState.md)||  
|[CMFCAutoHideBar::ShowAutoHideWindow](../Topic/CMFCAutoHideBar::ShowAutoHideWindow.md)||  
|[CMFCAutoHideBar::StretchPane](../Topic/CMFCAutoHideBar::StretchPane.md)|Étire un volet sur le plan vertical ou horizontal.  \(Substitue [CBasePane::StretchPane](../Topic/CBasePane::StretchPane.md).\)|  
|[CMFCAutoHideBar::UnSetAutoHideMode](../Topic/CMFCAutoHideBar::UnSetAutoHideMode.md)||  
|[CMFCAutoHideBar::UpdateVisibleState](../Topic/CMFCAutoHideBar::UpdateVisibleState.md)||  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCAutoHideBar::m\_nShowAHWndDelay](../Topic/CMFCAutoHideBar::m_nShowAHWndDelay.md)|Délai entre le moment où l'utilisateur place le curseur de la souris sur une [CMFCAutoHideButton Class](../../mfc/reference/cmfcautohidebutton-class.md) et le moment où l'infrastructure affiche la fenêtre associée.|  
  
## Notes  
 Quand l'utilisateur passe d'un volet d'ancrage à un mode de masquage automatique, l'infrastructure crée automatiquement un objet `CMFCAutoHideBar`.  Elle crée aussi les objets [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) et [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) nécessaires.  Chaque objet `CAutoHideDockSite` est associé à un `CMFCAutoHideButton` individuel.  
  
 La classe `CMFCAutoHideBar` implémente l'affichage d'un `CAutoHideDockSite` quand l'utilisateur pointe la souris sur un `CMFCAutoHideButton`.  Quand la barre d'outils reçoit un message WM\_MOUSEMOVE, `CMFCAutoHideBar` démarre un minuteur.  Celui\-ci envoie une notification d'événement WM\_TIMER à la barre d'outils à la fin du processus.  La barre d'outils traite cet événement en vérifiant si le pointeur de la souris est positionné sur le même bouton de masquage automatique qu'au moment où le minuteur a démarré.  Si c'est le cas, le `CAutoHideDockSite` attaché s'affiche.  
  
 Vous pouvez contrôler le délai du minuteur en définissant `m_nShowAHWndDelay`.  La valeur par défaut est de 400 ms.  
  
## Exemple  
 L'exemple suivant montre comment construire un objet `CMFCAutoHideBar` et utiliser sa méthode `GetDockSiteRow`.  
  
 [!code-cpp[NVC_MFC_RibbonApp#26](../../mfc/reference/codesnippet/CPP/cmfcautohidebar-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)  
  
## Configuration requise  
 **En\-tête :** afxautohidebar.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CPane Class](../../mfc/reference/cpane-class.md)   
 [CAutoHideDockSite Class](../../mfc/reference/cautohidedocksite-class.md)   
 [CMFCAutoHideButton Class](../../mfc/reference/cmfcautohidebutton-class.md)