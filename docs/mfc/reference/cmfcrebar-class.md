---
title: "CMFCReBar Class | Microsoft Docs"
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
  - "CMFCReBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCReBar class"
ms.assetid: 02a60e29-6224-49c1-9e74-e0a7d9f8d023
caps.latest.revision: 27
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCReBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un objet d' `CMFCReBar` est une barre de contrôles qui fournit la disposition, la persistance, et les informations d'état pour les rebar contrôles.  
  
## Syntaxe  
  
```  
class CMFCReBar : public CPane  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCReBar::AddBar](../Topic/CMFCReBar::AddBar.md)|Ajoute une bande à un rebar.|  
|[CMFCReBar::CalcFixedLayout](../Topic/CMFCReBar::CalcFixedLayout.md)|\(Substitutions [CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md).\)|  
|[CMFCReBar::CanFloat](../Topic/CMFCReBar::CanFloat.md)|\(Substitutions [CBasePane::CanFloat](../Topic/CBasePane::CanFloat.md).\)|  
|[CMFCReBar::Create](../Topic/CMFCReBar::Create.md)|Crée le contrôle rebar et l'attache à l'objet d' `CMFCReBar` .|  
|[CMFCReBar::EnableDocking](../Topic/CMFCReBar::EnableDocking.md)|\(Substitutions [CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md).\)|  
|[CMFCReBar::GetReBarBandInfoSize](../Topic/CMFCReBar::GetReBarBandInfoSize.md)||  
|[CMFCReBar::GetReBarCtrl](../Topic/CMFCReBar::GetReBarCtrl.md)|Fournit l'accès direct au contrôle commun sous\-jacent de [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) .|  
|[CMFCReBar::OnShowControlBarMenu](../Topic/CMFCReBar::OnShowControlBarMenu.md)|\(Substitutions [CPane::OnShowControlBarMenu](../Topic/CPane::OnShowControlBarMenu.md).\)|  
|[CMFCReBar::OnToolHitTest](../Topic/CMFCReBar::OnToolHitTest.md)|\(Substitutions [CWnd::OnToolHitTest](../Topic/CWnd::OnToolHitTest.md).\)|  
|[CMFCReBar::OnUpdateCmdUI](../Topic/CMFCReBar::OnUpdateCmdUI.md)|\(Substitutions [CBasePane::OnUpdateCmdUI](http://msdn.microsoft.com/fr-fr/e139f06a-9793-4ee2-bc3d-517389368c77).\)|  
|[CMFCReBar::SetPaneAlignment](../Topic/CMFCReBar::SetPaneAlignment.md)|\(Substitutions [CBasePane::SetPaneAlignment](../Topic/CBasePane::SetPaneAlignment.md).\)|  
  
## Notes  
 Un objet d' `CMFCReBar` peut contenir plusieurs fenêtres enfants.  Cela inclut les zones d'édition, des barres d'outils, les zones de liste.  Vous pouvez redimensionner par programme le rebar, ou l'utilisateur peut redimensionner manuellement le rebar en faisant glisser sa barre de pinces.  Vous pouvez également définir l'arrière\-plan d'un objet rebar une bitmap de votre choix.  
  
 Un objet rebar se comporte de la même façon à un objet barre d'outils.  Un contrôle rebar peut contenir un ou plusieurs bandes, et chaque bande peut contenir une barre de pinces, une bitmap, une étiquette de texte, et une fenêtre enfant.  
  
## Exemple  
 L'exemple suivant montre comment utiliser différentes méthodes dans la classe d' `CMFCReBar` .  L'exemple montre comment créer un contrôle rebar et ajouter une bande lui.  Les fonctions de bandes comme une barre d'outils intégrée.  Cet extrait de code fait partie d' [Exemple rebar de test](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_RebarTest#1](../../mfc/reference/codesnippet/CPP/cmfcrebar-class_1.h)]  
[!code-cpp[NVC_MFC_RebarTest#2](../../mfc/reference/codesnippet/CPP/cmfcrebar-class_2.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CMFCReBar](../../mfc/reference/cmfcrebar-class.md)  
  
## Configuration requise  
 **en\-tête :** afxRebar.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CReBarCtrl Class](../../mfc/reference/crebarctrl-class.md)   
 [CPane Class](../../mfc/reference/cpane-class.md)