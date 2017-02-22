---
title: "D&#233;sactivation de l&#39;option Actif quand il est visible | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Contrôles ActiveX MFC [C++], options d’activation"
  - "option Actif quand il est visible"
ms.assetid: 8f7ddc5a-a7a6-4da8-bcb9-1b569f0ecb48
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# D&#233;sactivation de l&#39;option Actif quand il est visible
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un contrôle possède deux états de base : actif et inactif.  Traditionnellement, ces états ont été distingués par la possession ou non d'une fenêtre par le contrôle.  Un contrôle actif avait une fenêtre ; un contrôle inactif n'en avait pas.  Avec l'introduction de l'activation sans fenêtre, cette distinction n'est plus universelle, mais toujours applicable à de nombreux contrôles.  
  
 Compared with the rest of the initialization typically performed by an ActiveX control, the creation of a window is an extremely expensive operation.  Ideally, a control would defer creating its window until absolutely necessary.  
  
 Many controls do not need to be active the entire time they are visible in a container.  Often, a control can remain in the inactive state until the user performs an operation that requires it to become active \(for example, clicking with the mouse or pressing the TAB key\).  To cause a control to remain inactive until the container needs to activate it, remove the **OLEMISC\_ACTIVATEWHENVISIBLE** flag from the control's miscellaneous flags:  
  
 [!code-cpp[NVC_MFC_AxOpt#9](../mfc/codesnippet/CPP/turning-off-the-activate-when-visible-option_1.cpp)]  
  
 The **OLEMISC\_ACTIVATEWHENVISIBLE** flag is automatically omitted if you turn off the **Activate When Visible** option in the [Control Settings](../mfc/reference/control-settings-mfc-activex-control-wizard.md) page of the MFC ActiveX Control Wizard when you create your control.  
  
## Voir aussi  
 [Contrôles ActiveX MFC : optimisation](../mfc/mfc-activex-controls-optimization.md)