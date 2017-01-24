---
title: "CPaintDC Class | Microsoft Docs"
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
  - "CPaintDC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPaintDC class"
  - "OnPaint handler"
  - "WM_PAINT message"
ms.assetid: 7e245baa-bf9b-403e-a637-7218adf28fab
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPaintDC Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une classe de périphérique\-contexte dérivée de [CDC](../../mfc/reference/cdc-class.md).  
  
## Syntaxe  
  
```  
class CPaintDC : public CDC  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CPaintDC::CPaintDC](../Topic/CPaintDC::CPaintDC.md)|Construit `CPaintDC` connecté à [CWnd](../../mfc/reference/cwnd-class.md)spécifié.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPaintDC::m\_ps](../Topic/CPaintDC::m_ps.md)|Contient [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) utilisé pour peindre la zone cliente.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CPaintDC::m\_hWnd](../Topic/CPaintDC::m_hWnd.md)|`HWND` auquel cet objet d' `CPaintDC` est attaché.|  
  
## Notes  
 Il effectue [CWnd::BeginPaint](../Topic/CWnd::BeginPaint.md) au moment de la construction et [CWnd::EndPaint](../Topic/CWnd::EndPaint.md) au temps de destruction.  
  
 Un objet d' `CPaintDC` peut être utilisé en répondant à un message de [WM\_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) , généralement dans la fonction membre gestionnaire de messages d' `OnPaint` .  
  
 Pour plus d'informations sur l'utilisation `CPaintDC`, consultez [contextes de périphérique](../../mfc/device-contexts.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CPaintDC`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [Exemple MDI MFC](../../top/visual-cpp-samples.md)   
 [CDC, classe](../../mfc/reference/cdc-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)