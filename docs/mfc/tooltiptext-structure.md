---
title: "TOOLTIPTEXT, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TOOLTIPTEXT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "info-bulles (C++), notifications"
  - "TOOLTIPTEXT (structure)"
ms.assetid: 547591bf-80f5-400e-a2a7-0708cfffbb5d
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# TOOLTIPTEXT, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lors de l'écriture votre [gestionnaire de notification d'info\-bulle](../mfc/handling-ttn-needtext-notification-for-tool-tips.md), vous devez utiliser la structure `TOOLTIPTEXT`.  Les membres de la structure `TOOLTIPTEXT` sont :  
  
 `typedef struct {`  
  
 `NMHDR     hdr;        // required for all WM_NOTIFY messages`  
  
 `LPTSTR    lpszText;   // see below`  
  
 `TCHAR     szText[80]; // buffer for tool tip text`  
  
 `HINSTANCE hinst;      // see below`  
  
 `UINT      uflags;     // flag indicating how to interpret the`  
  
 `// idFrom member of the NMHDR structure`  
  
 `// that is included in the structure`  
  
 `} TOOLTIPTEXT, FAR *LPTOOLTIPTEXT;`  
  
 `hdr`  
 Identifie l'outil qui a besoin de texte.  Le seul membre de la structure dont vous pouvez avoir besoin est l'ID de contrôle.  L'ID de commande du contrôle sera du membre `idFrom` de la structure `NMHDR`, accessible avec la syntaxe `hdr.idFrom`.  Consultez le [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) pour obtenir des membres de la structure `NMHDR`.  
  
 `lpszText`  
 Adresse de chaîne qui recevra le texte pour un outil.  
  
 `szText`  
 Mise en mémoire tampon qui obtient le texte info\-bulle.  Une application peut copier le texte à cette mémoire tampon comme alternative à spécifier une adresse de chaîne.  
  
 `hinst`  
 Gestion de l'instance qui contient une chaîne à utiliser comme texte d'info\-bulle.  Si `lpszText` est l'adresse du texte info\-bulle, ce membre est NULL.  
  
 Lors de le traitement du message de notification `TTN_NEEDTEXT`, spécifiez la chaîne à afficher dans l'une des manières suivantes :  
  
-   Copiez le texte figurant dans la mémoire tampon spécifiée par le membre `szText`.  
  
-   Copiez l'adresse de la mémoire tampon qui contient le texte du membre `lpszText`.  
  
-   Copiez l'ID de ressource de type chaîne au membre `lpszText`, puis copiez le descripteur de l'instance qui contient la ressource au membre `hinst`.  
  
## Voir aussi  
 [Info\-bulles dans les fenêtres non dérivées de CFrameWnd](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)