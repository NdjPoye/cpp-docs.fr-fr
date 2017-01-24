---
title: "CMFCPopupMenuBar, classe | Microsoft Docs"
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
  - "CMFCPopupMenuBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPopupMenuBar, classe"
ms.assetid: 4c93c459-7f70-4240-8c63-280bb811e374
caps.latest.revision: 32
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCPopupMenuBar, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une barre de menus incorporée dans un menu contextuel.  
  
## Syntaxe  
  
```  
class CMFCPopupMenuBar : public CMFCToolBar  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCPopupMenuBar::AdjustSizeImmediate](../Topic/CMFCPopupMenuBar::AdjustSizeImmediate.md)|Recalcule immédiatement la disposition d'un volet.  \(Substitutions [CPane::AdjustSizeImmediate](../Topic/CPane::AdjustSizeImmediate.md).\)|  
|[CMFCPopupMenuBar::BuildOrigItems](../Topic/CMFCPopupMenuBar::BuildOrigItems.md)|Charge les éléments de menu contextuel d'une ressource menu spécifiée.|  
|[CMFCPopupMenuBar::CloseDelayedSubMenu](../Topic/CMFCPopupMenuBar::CloseDelayedSubMenu.md)|Ferme un bouton de menu popup différé.|  
|[CMFCPopupMenuBar::ExportToMenu](../Topic/CMFCPopupMenuBar::ExportToMenu.md)|Génère un menu de boutons d'instantané\- menu.|  
|[CMFCPopupMenuBar::FindDestintationToolBar](../Topic/CMFCPopupMenuBar::FindDestintationToolBar.md)|Recherche la barre d'outils où un point spécifié est affichée.|  
|[CMFCPopupMenuBar::GetCurrentMenuImageSize](../Topic/CMFCPopupMenuBar::GetCurrentMenuImageSize.md)|Indique la taille des images de bouton de menu.|  
|[CMFCPopupMenuBar::GetDefaultMenuId](../Topic/CMFCPopupMenuBar::GetDefaultMenuId.md)|Retourne l'identificateur de l'élément de menu par défaut.|  
|[CMFCPopupMenuBar::GetLastCommandIndex](../Topic/CMFCPopupMenuBar::GetLastCommandIndex.md)|Obtient l'index de la commande de menu récemment appelée.|  
|[CMFCPopupMenuBar::GetOffset](../Topic/CMFCPopupMenuBar::GetOffset.md)|Obtient l'offset de ligne de la barre de menus instantanée.|  
|[CMFCPopupMenuBar::ImportFromMenu](../Topic/CMFCPopupMenuBar::ImportFromMenu.md)|Tous les boutons de menu contextuel d'un menu spécifié.|  
|[CMFCPopupMenuBar::IsDropDownListMode](../Topic/CMFCPopupMenuBar::IsDropDownListMode.md)|Indique si la barre de menus instantanée est en mode de liste déroulante.|  
|[CMFCPopupMenuBar::IsPaletteMode](../Topic/CMFCPopupMenuBar::IsPaletteMode.md)|Indique si la barre de menus instantanée est en mode de la palette.|  
|[CMFCPopupMenuBar::IsRibbonPanel](../Topic/CMFCPopupMenuBar::IsRibbonPanel.md)|Indique s'il s'agit d'un panneau de ruban \(`FALSE` par défaut\).|  
|[CMFCPopupMenuBar::IsRibbonPanelInRegularMode](../Topic/CMFCPopupMenuBar::IsRibbonPanelInRegularMode.md)|Indique s'il s'agit d'un panneau de ruban en mode normal \(`FALSE` par défaut\).|  
|[CMFCPopupMenuBar::LoadFromHash](../Topic/CMFCPopupMenuBar::LoadFromHash.md)|Charge un menu archivé.|  
|[CMFCPopupMenuBar::RestoreDelayedSubMenu](../Topic/CMFCPopupMenuBar::RestoreDelayedSubMenu.md)|Restaure un bouton de menu différée pour fermer la barre de menus instantanée.|  
|[CMFCPopupMenuBar::SetButtonStyle](../Topic/CMFCPopupMenuBar::SetButtonStyle.md)|Définit le style du bouton de barre d'outils à l'index donné.  \(Substitutions [CMFCToolBar::SetButtonStyle](../Topic/CMFCToolBar::SetButtonStyle.md).\)|  
|[CMFCPopupMenuBar::SetOffset](../Topic/CMFCPopupMenuBar::SetOffset.md)|Définit le décalage de ligne de la barre de menus instantanée.|  
|[CMFCPopupMenuBar::StartPopupMenuTimer](../Topic/CMFCPopupMenuBar::StartPopupMenuTimer.md)|Démarre la minuterie d'un bouton de menu popup différé spécifié.|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCPopupMenuBar::m\_bDisableSideBarInXPMode](../Topic/CMFCPopupMenuBar::m_bDisableSideBarInXPMode.md)|Spécifie si l'encadré gris s'affiche lorsque l'application a une apparence Windows XP.|  
  
## Notes  
 `CMFCPopupMenuBar` est créé en même temps que [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md) et incorporé à l'intérieur de lui.  `CMFCPopupMenuBar` couvre la zone cliente entière de l'objet d' `CMFCPopupMenu` .  Il prend en charge le clavier et l'entrée de la souris.  Il communique également cette entrée à `CMFCPopupMenu` et à la fenêtre frame de niveau supérieur.  
  
## Exemple  
 L'exemple suivant montre comment initialiser un objet d' `CMFCPopupMenuBar` d'un objet d' `CMFCPopupMenu` .  Cet extrait de code fait partie d' [Exemple de client de dessin](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#7](../../mfc/reference/codesnippet/CPP/cmfcpopupmenubar-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)  
  
## Configuration requise  
 **En\-tête :** afxpopupmenubar.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md)