---
title: "CMFCWindowsManagerDialog Class | Microsoft Docs"
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
  - "CMFCWindowsManagerDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCWindowsManagerDialog class"
ms.assetid: 35b4b0db-33c4-4b22-94d8-5e3396341340
caps.latest.revision: 25
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCWindowsManagerDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'objet d' `CMFCWindowsManagerDialog` permet à un utilisateur de gérer des fenêtres MDI enfants dans une application MDI.  
  
## Syntaxe  
  
```  
class CMFCWindowsManagerDialog : public CDialog  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCWindowsManagerDialog::CMFCWindowsManagerDialog](../Topic/CMFCWindowsManagerDialog::CMFCWindowsManagerDialog.md)|Construit un objet `CMFCWindowsManagerDialog`.|  
  
## Notes  
 `CMFCWindowsManagerDialog` contient une liste de fenêtres MDI enfants qui sont actuellement ouverts dans l'application.  L'utilisateur peut manuellement vérifier l'état des fenêtres MDI enfants à l'aide de cette boîte de dialogue.  
  
 `CMFCWindowsManagerDialog` est incorporé à l'intérieur de [Classe CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md).  `CMFCWindowsManagerDialog` n'est pas une classe que vous devez créer manuellement.  À la place, appelez la fonction [CMDIFrameWndEx::ShowWindowsDialog](../Topic/CMDIFrameWndEx::ShowWindowsDialog.md), et elle crée et affiche un objet d' `CMFCWindowsManagerDialog` .  
  
## Exemple  
 L'exemple suivant montre comment construire un objet d' `CMFCWindowsManagerDialog` en appelant `CMDIFrameWndEx::ShowWindowsDialog`.  Cet extrait de code fait partie d' [Exemple de démonstration de Visual Studio](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#18](../../mfc/codesnippet/CPP/cmfcwindowsmanagerdialog-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)  
  
## Configuration requise  
 **en\-tête :** afxWindowsManagerDialog.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [Classe CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)   
 [CMDIFrameWndEx::ShowWindowsDialog](../Topic/CMDIFrameWndEx::ShowWindowsDialog.md)