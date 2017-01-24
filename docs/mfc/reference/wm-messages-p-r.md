---
title: "WM_, messages&#160;: P - R | Microsoft Docs"
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
  - "ON_WM_RBUTTONUP"
  - "ON_WM_PALETTECHANGED"
  - "ON_WM_RBUTTONDBLCLK"
  - "ON_WM_QUERYENDSESSION"
  - "ON_WM_PARENTNOTIFY"
  - "ON_WM_PALETTEISCHANGING"
  - "ON_WM_QUERYOPEN"
  - "ON_WM_PAINT"
  - "ON_WM_QUERYNEWPALETTE"
  - "ON_WM_RBUTTONDOWN"
  - "ON_WM_RENDERALLFORMATS"
  - "ON_WM_PAINTCLIPBOARD"
  - "ON_WM_RENDERFORMAT"
  - "ON_WM_QUERYDRAGICON"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ON_WM_PAINT"
  - "ON_WM_PAINTCLIPBOARD"
  - "ON_WM_PALETTECHANGED"
  - "ON_WM_PALETTEISCHANGING"
  - "ON_WM_PARENTNOTIFY"
  - "ON_WM_QUERYDRAGICON"
  - "ON_WM_QUERYENDSESSION"
  - "ON_WM_QUERYNEWPALETTE"
  - "ON_WM_QUERYOPEN"
  - "ON_WM_RBUTTONDBLCLK"
  - "ON_WM_RBUTTONDOWN"
  - "ON_WM_RBUTTONUP"
  - "ON_WM_RENDERALLFORMATS"
  - "ON_WM_RENDERFORMAT"
  - "WM_ (messages)"
ms.assetid: f46962e5-8329-4f1f-9b4d-fdad2a5ce1f8
caps.latest.revision: 15
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WM_, messages&#160;: P - R
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les entrées de mappage suivantes correspondent aux prototypes de fonction :  
  
|Entrée de mappage|Prototype de fonction|  
|-----------------------|---------------------------|  
|ON\_WM\_PAINT|afx\_msg [OnPaint](../Topic/CWnd::OnPaint.md)void \(\) ;|  
|ON\_WM\_PAINTCLIPBOARD|afx\_msg [OnPaintClipboard](../Topic/CWnd::OnPaintClipboard.md)void \(CWnd\*, HANDLE\) ;|  
|ON\_WM\_PALETTECHANGED|afx\_msg [OnPaletteChanged](../Topic/CWnd::OnPaletteChanged.md)void \(CWnd\*\) ;|  
|ON\_WM\_PALETTEISCHANGING|afx\_msg [OnPaletteIsChanging](../Topic/CWnd::OnPaletteIsChanging.md)void \(CWnd\*\) ;|  
|ON\_WM\_PARENTNOTIFY|afx\_msg [OnParentNotify](../Topic/CWnd::OnParentNotify.md)void \(UINT, LONGS\) ;|  
|ON\_WM\_POWERBROADCAST\(\)|afx\_msg UINT [OnPowerBroadcast](../Topic/CWnd::OnPowerBroadcast.md)\(UINT, UINT\) ;|  
|ON\_WM\_QUERYDRAGICON|afx\_msg HCURSOR [OnQueryDragIcon](../Topic/CWnd::OnQueryDragIcon.md)\(\)\(\);|  
|ON\_WM\_QUERYENDSESSION|BOOL [OnQueryEndSession](../Topic/CWnd::OnQueryEndSession.md)\(\)\(\)d'afx\_msg ;|  
|ON\_WM\_QUERYNEWPALETTE|BOOL [OnQueryNewPalette](../Topic/CWnd::OnQueryNewPalette.md)\(\)\(\)d'afx\_msg ;|  
|ON\_WM\_QUERYOPEN|BOOL [OnQueryOpen](../Topic/CWnd::OnQueryOpen.md)\(\)\(\)d'afx\_msg ;|  
|\+ON\_WM\_RBUTTONDBLCLK|afx\_msg void [OnMLButtonDblClk](../Topic/CWnd::OnRButtonDblClk.md)void \(UINT, CPoint\) ;|  
|ON\_WM\_RBUTTONDOWN|afx\_msg void [OnMLButtonDown](../Topic/CWnd::OnRButtonDown.md)void \(UINT, CPoint\) ;|  
|ON\_WM\_RBUTTONUP|afx\_msg void [OnMLButtonUp](../Topic/CWnd::OnRButtonUp.md)void \(UINT, CPoint\) ;|  
|ON\_WM\_RENDERALLFORMATS|afx\_msg [OnRenderAllFormats](../Topic/CWnd::OnRenderAllFormats.md)void \(\) ;|  
|ON\_WM\_RENDERFORMAT|afx\_msg [OnRenderFormat](../Topic/CWnd::OnRenderFormat.md)void \(UINT\) ;|  
  
## Voir aussi  
 [Tables des messages](../../mfc/reference/message-maps-mfc.md)   
 [Gestionnaires de messages WM\_](../../mfc/reference/handlers-for-wm-messages.md)