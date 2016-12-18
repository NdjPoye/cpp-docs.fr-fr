---
title: "CMFCTabToolTipInfo Structure | Microsoft Docs"
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
  - "CMFCTabToolTipInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCTabToolTipInfo struct"
ms.assetid: 9c3b3fb9-1497-4d59-932b-0da9348dd5e2
caps.latest.revision: 27
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCTabToolTipInfo Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette structure fournit des informations sur l'onglet MDI sur lequel l'utilisateur pointe.  
  
## Syntaxe  
  
```  
struct CMFCTabToolTipInfo  
```  
  
## Membres  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCTabToolTipInfo::m\_nTabIndex](../Topic/CMFCTabToolTipInfo::m_nTabIndex.md)|Spécifie l'index du contrôle onglet.|  
|[CMFCTabToolTipInfo::m\_pTabWnd](../Topic/CMFCTabToolTipInfo::m_pTabWnd.md)|Pointeur vers le contrôle onglet.|  
|[CMFCTabToolTipInfo::m\_strText](../Topic/CMFCTabToolTipInfo::m_strText.md)|Texte info\-bulle.|  
  
## Notes  
 Un pointeur vers une structure d' `CMFCTabToolTipInfo` passé comme paramètre du message d' `AFX_WM_ON_GET_TAB_TOOLTIP` .  Ce message est généré lorsque des onglets MDI est activé et les vols planés d'utilisateur sur un contrôle onglet.  
  
## Exemple  
 l'exemple suivant montre comment `CMFCTabToolTipInfo` est utilisé dans [Exemple MDITabsDemo : MFC est tabulé l'application MDI](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/CPP/cmfctabtooltipinfo-structure_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CMFCTabToolTipInfo](../../mfc/reference/cmfctabtooltipinfo-structure.md)  
  
## Configuration requise  
 **en\-tête :** afxbasetabctrl.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMDIFrameWndEx::EnableMDITabs](../Topic/CMDIFrameWndEx::EnableMDITabs.md)   
 [CMDITabInfo::m\_bTabCustomTooltips](../Topic/CMDITabInfo::m_bTabCustomTooltips.md)