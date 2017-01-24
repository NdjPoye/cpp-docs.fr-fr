---
title: "Styles de bo&#238;te de message | Microsoft Docs"
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
  - "MB_ICONQUESTION"
  - "MB_ICONINFORMATION"
  - "MB_DEFBUTTON2"
  - "MB_YESNO"
  - "MB_OKCANCEL"
  - "MB_TASKMODAL"
  - "MB_ICONEXCLAMATION"
  - "MB_OK"
  - "MB_DEFBUTTON3"
  - "MB_YESNOCANCEL"
  - "MB_APPLMODAL"
  - "MB_RETRYCANCEL"
  - "MB_DEFBUTTON1"
  - "MB_ABORTRETRYIGNORE"
  - "MB_SYSTEMMODAL"
  - "MB_ICONSTOP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MB_ABORTRETRYIGNORE (constante)"
  - "MB_APPLMODAL (constante)"
  - "MB_DEFBUTTON1 (constante)"
  - "MB_DEFBUTTON2 (constante)"
  - "MB_DEFBUTTON3 (constante)"
  - "MB_ICONEXCLAMATION (constante)"
  - "MB_ICONINFORMATION (constante)"
  - "MB_ICONQUESTION (constante)"
  - "MB_ICONSTOP (constante)"
  - "MB_OK (constante)"
  - "MB_OKCANCEL (constante)"
  - "MB_RETRYCANCEL (constante)"
  - "MB_SYSTEMMODAL (constante)"
  - "MB_TASKMODAL (constante)"
  - "MB_YESNO (constante)"
  - "MB_YESNOCANCEL (constante)"
  - "styles de boîte de message"
ms.assetid: d87014c5-4ea4-4950-a27e-7bcdda67be7d
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Styles de bo&#238;te de message
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The following message\-box styles are available.  
  
## Message\_Box Types  
  
-   **MB\_ABORTRETRYIGNORE** The message box contains three pushbuttons: Abort, Retry, and Ignore.  
  
-   **MB\_OK** The message box contains one pushbutton: OK.  
  
-   **MB\_OKCANCEL** The message box contains two pushbuttons: OK and Cancel.  
  
-   **MB\_RETRYCANCEL** The message box contains two pushbuttons: Retry and Cancel.  
  
-   **MB\_YESNO** The message box contains two pushbuttons: Yes and No.  
  
-   **MB\_YESNOCANCEL** The message box contains three pushbuttons: Yes, No, and Cancel.  
  
## Message\-Box Modality  
  
-   **MB\_APPLMODAL** The user must respond to the message box before continuing work in the current window.  However, the user can move to the windows of other applications and work in those windows.  The default is **MB\_APPLMODAL** if neither **MB\_SYSTEMMODAL** nor **MB\_TASKMODAL** is specified.  
  
-   **MB\_SYSTEMMODAL** All applications are suspended until the user responds to the message box.  System\-modal message boxes are used to notify the user of serious, potentially damaging errors that require immediate attention and should be used sparingly.  
  
-   **MB\_TASKMODAL** Similar to **MB\_APPLMODAL**, but not useful within a Microsoft Foundation class application.  This flag is reserved for a calling application or library that does not have a window handle available.  
  
## Message\-Box Icons  
  
-   **MB\_ICONEXCLAMATION** An exclamation\-point icon appears in the message box.  
  
-   **MB\_ICONINFORMATION** An icon consisting of an "I" in a circle appears in the message box.  
  
-   **MB\_ICONQUESTION** A question\-mark icon appears in the message box.  
  
-   **MB\_ICONSTOP** A stop\-sign icon appears in the message box.  
  
## Message\-Box Default Buttons  
  
-   **MB\_DEFBUTTON1** The first button is the default.  Note that the first button is always the default unless **MB\_DEFBUTTON2** or **MB\_DEFBUTTON3** is specified.  
  
-   **MB\_DEFBUTTON2** The second button is the default.  
  
-   **MB\_DEFBUTTON3** The third button is the default.  
  
## Voir aussi  
 [Styles utilisés par MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [AfxMessageBox](../Topic/AfxMessageBox.md)