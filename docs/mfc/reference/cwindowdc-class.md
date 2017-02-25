---
title: "CWindowDC Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWindowDC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWindowDC class"
  - "device contexts, fenêtres"
  - "screen output classes"
ms.assetid: 876a3641-4cde-471c-b0d1-fe58b32af79c
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CWindowDC Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dérivée de `CDC`.  
  
## Syntaxe  
  
```  
class CWindowDC : public CDC  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CWindowDC::CWindowDC](../Topic/CWindowDC::CWindowDC.md)|Construit un objet `CWindowDC`.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CWindowDC::m\_hWnd](../Topic/CWindowDC::m_hWnd.md)|`HWND` auquel `CWindowDC` est attaché.|  
  
## Notes  
 Appelle la fonction [GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947\(v=vs.85\).aspx) Windows au moment de la construction et [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920\(v=vs.85\).aspx) au moment de la destruction.  Cela signifie qu'un objet `CWindowDC` accède à la zone d'écran entière d'un [CWnd](../../mfc/reference/cwnd-class.md) \(zones clientes et non clientes\).  
  
 Pour plus d'informations sur l'utilisation de `CWindowDC`, consultez [Contextes de périphérique](../../mfc/device-contexts.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CWindowDC`  
  
## Configuration requise  
 En\-tête : afxwin.h  
  
## Voir aussi  
 [CDC, classe](../../mfc/reference/cdc-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CDC, classe](../../mfc/reference/cdc-class.md)