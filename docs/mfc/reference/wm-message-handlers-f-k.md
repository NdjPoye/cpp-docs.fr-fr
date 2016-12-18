---
title: "WM_, gestionnaires de messages : F - K | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ON_WM_FONTCHANGE"
  - "ON_WM_ICONERASEBKGND"
  - "ON_WM_KEYDOWN"
  - "ON_WM_GETMINMAXINFO"
  - "ON_WM_KEYUP"
  - "ON_WM_HSCROLL"
  - "ON_WM_KILLFOCUS"
  - "ON_WM_HSCROLLCLIPBOARD"
  - "ON_WM_GETDLGCODE"
  - "ON_WM_HELPINFO"
  - "ON_WM_INITMENUPOPUP"
  - "ON_WM_INITMENU"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ON_WM_FONTCHANGE"
  - "ON_WM_GETDLGCODE"
  - "ON_WM_GETMINMAXINFO"
  - "ON_WM_HELPINFO"
  - "ON_WM_HSCROLL"
  - "ON_WM_HSCROLLCLIPBOARD"
  - "ON_WM_ICONERASEBKGND"
  - "ON_WM_INITMENU"
  - "ON_WM_INITMENUPOPUP"
  - "ON_WM_KEYDOWN"
  - "ON_WM_KEYUP"
  - "ON_WM_KILLFOCUS"
  - "WM_ (messages)"
ms.assetid: 0e7de191-1499-499f-859c-62742797808e
caps.latest.revision: 15
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WM_, gestionnaires de messages : F - K
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les entrées de mappage suivantes à gauche correspondent aux prototypes de fonctions à droite :  
  
|Entrée de carte|Prototype de fonction|  
|---------------------|---------------------------|  
|ON\_WM\_FONTCHANGE\(\)|afx\_msg void [OnFontChange](../Topic/CWnd::OnFontChange.md)\(\);|  
|ON\_WM\_GETDLGCODE\(\)|afx\_msg UINT [OnGetDlgCode](../Topic/CWnd::OnGetDlgCode.md)\(\) ;|  
|ON\_WM\_GETMINMAXINFO\(\)|afx\_msg [OnGetMinMaxInfo](../Topic/CWnd::OnGetMinMaxInfo.md)void \(LPPOINT\) ;|  
|ON\_WM\_HELPINFO\(\)|[OnHelpInfo](../Topic/CWnd::OnHelpInfo.md)\(BOOL\) HELPINFO\* d'afx\_msg ;|  
|ON\_WM\_HOTKEY\(\)|afx\_msg [OnHotKey](../Topic/CWnd::OnHotKey.md)void \(UINT, UINT, UINT\) ;|  
|ON\_WM\_HSCROLL\(\)|afx\_msg void [OnHScroll](../Topic/CWnd::OnHScroll.md)\(UINT, UINT, CWnd\*\);|  
|ON\_WM\_HSCROLLCLIPBOARD\(\)|afx\_msg void [OnHScrollClipboard](../Topic/CWnd::OnHScrollClipboard.md)\(CWnd\*, UINT, UINT\);|  
|ON\_WM\_ICONERASEBKGND\(\)|afx\_msg void [OnIconEraseBkgnd](../Topic/CWnd::OnIconEraseBkgnd.md)\(CDC\*\);|  
|ON\_WM\_INITMENU\(\)|afx\_msg [OnInitMenu](../Topic/CWnd::OnInitMenu.md)void \(CMenu\*\) ;|  
|ON\_WM\_INITMENUPOPUP\(\)|afx\_msg [OnInitMenuPopup](../Topic/CWnd::OnInitMenuPopup.md)void \(CMenu\*, UINT, BOOL\) ;|  
|ON\_WM\_INPUT\(\)|afx\_msg [OnRawInput](../Topic/CWnd::OnRawInput.md)void \(UINT, HRAWINPUT\) ;|  
|ON\_WM\_INPUT\_DEVICE\_CHANGE\(\)|afx\_msg [OnInputDeviceChange](../Topic/CWnd::OnInputDeviceChange.md)void \(court non signé\) ;|  
|ON\_WM\_INPUTLANGCHANGE\(\)|afx\_msg [OnInputLangChange](../Topic/CWnd::OnInputLangChange.md)void \(BYTE, UINT\) ;|  
|ON\_WM\_INPUTLANGCHANGEREQUEST\(\)|afx\_msg [OnInputLangChangeRequest](../Topic/CWnd::OnInputLangChangeRequest.md)void \(UINT, HKL\) ;|  
|ON\_WM\_KEYDOWN\(\)|afx\_msg [OnKeyDown](../Topic/CWnd::OnKeyDown.md)void \(UINT, UINT, UINT\) ;|  
|ON\_WM\_KEYUP\(\)|afx\_msg [OnKeyUp](../Topic/CWnd::OnKeyUp.md)void \(UINT, UINT, UINT\) ;|  
|ON\_WM\_KILLFOCUS\(\)|afx\_msg [OnKillFocus](../Topic/CWnd::OnKillFocus.md)void \(CWnd\*\) ;|  
  
## Voir aussi  
 [Tables des messages](../../mfc/reference/message-maps-mfc.md)   
 [Gestionnaires de messages WM\_](../../mfc/reference/handlers-for-wm-messages.md)