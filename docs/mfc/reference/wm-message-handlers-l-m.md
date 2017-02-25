---
title: "WM_, gestionnaires de messages&#160;: L - M | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ON_WM_MENUSELECT"
  - "ON_WM_MBUTTONDBLCLK"
  - "ON_WM_MOUSEACTIVATE"
  - "ON_WM_MOUSEMOVE"
  - "ON_WM_MOVING"
  - "ON_WM_LBUTTONUP"
  - "ON_WM_LBUTTONDBLCLK"
  - "ON_WM_MEASUREITEM"
  - "ON_WM_MDIACTIVATE"
  - "ON_WM_MOVE"
  - "ON_WM_LBUTTONDOWN"
  - "ON_WM_MBUTTONDOWN"
  - "ON_WM_MENUCHAR"
  - "ON_WM_MBUTTONUP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ON_WM_LBUTTONDBLCLK"
  - "ON_WM_LBUTTONDOWN"
  - "ON_WM_LBUTTONUP"
  - "ON_WM_MBUTTONDBLCLK"
  - "ON_WM_MBUTTONDOWN"
  - "ON_WM_MBUTTONUP"
  - "ON_WM_MDIACTIVATE"
  - "ON_WM_MEASUREITEM"
  - "ON_WM_MENUCHAR"
  - "ON_WM_MENUSELECT"
  - "ON_WM_MOUSEACTIVATE"
  - "ON_WM_MOUSEMOVE"
  - "ON_WM_MOVE"
  - "ON_WM_MOVING"
  - "WM_ (messages)"
ms.assetid: 96ecaaf1-6d13-4e12-a454-535635967489
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# WM_, gestionnaires de messages&#160;: L - M
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les entrées de mappage suivantes à gauche correspondent aux prototypes de fonctions à droite :  
  
|Entrée de carte|Prototype de fonction|  
|---------------------|---------------------------|  
|ON\_WM\_LBUTTONDBLCLK\(\)|afx\_msg [OnLButtonDblClk](../Topic/CWnd::OnLButtonDblClk.md)void \(UINT, CPoint\) ;|  
|ON\_WM\_LBUTTONDOWN\(\)|afx\_msg [OnLButtonDown](../Topic/CWnd::OnLButtonDown.md)void \(UINT, CPoint\) ;|  
|ON\_WM\_LBUTTONUP\(\)|afx\_msg [OnLButtonUp](../Topic/CWnd::OnLButtonUp.md)void \(UINT, CPoint\) ;|  
|ON\_WM\_MBUTTONDBLCLK\(\)|afx\_msg void [OnMLButtonDblClk](../Topic/CWnd::OnMButtonDblClk.md)void \(UINT, CPoint\) ;|  
|ON\_WM\_MBUTTONDOWN\(\)|afx\_msg void [OnMLButtonDown](../Topic/CWnd::OnMButtonDown.md)void \(UINT, CPoint\) ;|  
|ON\_WM\_MBUTTONUP\(\)|afx\_msg void [OnMLButtonUp](../Topic/CWnd::OnMButtonUp.md)void \(UINT, CPoint\) ;|  
|ON\_WM\_MDIACTIVATE\(\)|afx\_msg void [OnMDIActivate](../Topic/CWnd::OnMDIActivate.md)\(BOOL, CWnd\*, CWnd\*\) ;|  
|ON\_WM\_MEASUREITEM\(\)|afx\_msg void [OnMeasureItem](../Topic/CWnd::OnMeasureItem.md)\(LPMEASUREITEMSTRUCT\) ;|  
|ON\_WM\_MENUCHAR\(\)|afx\_msg LONG [OnMenuChar](../Topic/CWnd::OnMenuChar.md)\(UINT, UINT, CMenu\*\) ;|  
|ON\_WM\_MENUDRAG\(\)|afx\_msg UINT [OnMenuDrag](../Topic/CWnd::OnMenuDrag.md)\(UINT, CMenu\*\) ;|  
|ON\_WM\_MENUGETOBJECT\(\)|afx\_msg UINT [OnMenuGetObject](../Topic/CWnd::OnMenuGetObject.md)\(MENUGETOBJECTINFO\*\) ;|  
|ON\_WM\_MENURBUTTONUP\(\)|afx\_msg void [OnMenuRButtonUp](../Topic/CWnd::OnMenuRButtonUp.md)\(UINT, CMenu\*\) ;|  
|ON\_WM\_MENUSELECT\(\)|afx\_msg void [OnMenuSelect](../Topic/CWnd::OnMenuSelect.md)\(UINT, UINT, HMENU\) ;|  
|ON\_WM\_MOUSEACTIVATE\(\)|afx\_msg int [OnMouseActivate](../Topic/CWnd::OnMouseActivate.md)\(CWnd\*, UINT, UINT\) ;|  
|ON\_WM\_MOUSEHOVER\(\)|afx\_msg void [OnMouseHover](../Topic/CWnd::OnMouseHover.md)\(UINT, CPoint\) ;|  
|ON\_WM\_MOUSEHWHEEL\(\)|afx\_msg void [OnMouseHWheel](../Topic/CWnd::OnMouseHWheel.md)\(UINT, short, CPoint\) ;|  
|ON\_WM\_MOUSELEAVE\(\)|afx\_msg void [OnMouseLeave](../Topic/CWnd::OnMouseLeave.md)\(\);|  
|ON\_WM\_MOUSEMOVE\(\)|afx\_msg void [OnMouseMove](../Topic/CWnd::OnMouseMove.md)\( UINT, CPoint\);|  
|ON\_WM\_MOUSEWHEEL\(\)|afx\_msg BOOL [SurLaRoueDelaSourie](../Topic/CWnd::OnMouseWheel.md)\(UINT, short, CPoint\) d'afx\_msg ;|  
|ON\_WM\_MOVE\(\)|afx\_msg void [EnMouvement](../Topic/CWnd::OnMove.md)\(int, int\) ;|  
|ON\_WM\_MOVING\(\)|afx\_msg void [EnMouvement](../Topic/CWnd::OnMoving.md)\(UINT, LPRECT\) ;|  
  
## Voir aussi  
 [Tables des messages](../../mfc/reference/message-maps-mfc.md)   
 [Gestionnaires de messages WM\_](../../mfc/reference/handlers-for-wm-messages.md)