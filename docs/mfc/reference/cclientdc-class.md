---
title: "CClientDC Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CClientDC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CClientDC class"
  - "CDC (classe), device contexts for client areas"
  - "client-area device context"
  - "device contexts, zone cliente"
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CClientDC Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Se charge d'appeler les fonctions Windows [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871) au moment de la construction et [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920) au temps de destruction.  
  
## Syntaxe  
  
```  
  
class CClientDC : public CDC  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CClientDC::CClientDC](../Topic/CClientDC::CClientDC.md)|Construit un objet d' `CClientDC` connecté à `CWnd`.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CClientDC::m\_hWnd](../Topic/CClientDC::m_hWnd.md)|`HWND` de la fenêtre pour laquelle cet `CClientDC` est valide.|  
  
## Notes  
 Cela signifie que le contexte de périphérique associé à un objet d' `CClientDC` est la zone cliente d'une fenêtre.  
  
 Pour plus d'informations sur `CClientDC`, consultez [contextes de périphérique](../../mfc/device-contexts.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CClientDC`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [Exemple MDI MFC](../../top/visual-cpp-samples.md)   
 [CDC, classe](../../mfc/reference/cdc-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CDC, classe](../../mfc/reference/cdc-class.md)