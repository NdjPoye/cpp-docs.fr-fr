---
title: "Messages de notification de contr&#244;le d&#39;arborescence | Microsoft Docs"
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
  - "CTreeCtrl (classe), notifications"
  - "messages, notification"
  - "notifications, CTreeCtrl"
  - "notifications, contrôles d'arborescence"
  - "contrôles d'arborescence, messages de notification"
ms.assetid: ac7013b4-91dd-4668-bd75-439ca0680ef9
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Messages de notification de contr&#244;le d&#39;arborescence
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A tree control \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) sends the following notification messages as **WM\_NOTIFY** messages:  
  
|Notification message|Description|  
|--------------------------|-----------------|  
|**TVN\_BEGINDRAG**|Signals the start of a drag\-and\-drop operation|  
|**TVN\_BEGINLABELEDIT**|Signals the start of in\-place label editing|  
|**TVN\_BEGINRDRAG**|Signals the start of a drag\-and\-drop operation, using the right mouse button|  
|**TVN\_DELETEITEM**|Signals the deletion of a specific item|  
|**TVN\_ENDLABELEDIT**|Signals the end of label editing|  
|**TVN\_GETDISPINFO**|Requests information that the tree control requires to display an item|  
|**TVN\_ITEMEXPANDED**|Signals that a parent item's list of child items was expanded or collapsed|  
|**TVN\_ITEMEXPANDING**|Signals that a parent item's list of child items is about to be expanded or collapsed|  
|**TVN\_KEYDOWN**|Signals a keyboard event|  
|**TVN\_SELCHANGED**|Signals that the selection has changed from one item to another|  
|**TVN\_SELCHANGING**|Signals that the selection is about to be changed from one item to another|  
|**TVN\_SETDISPINFO**|Notification to update the information maintained for an item|  
  
## Voir aussi  
 [Utilisation de CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Contrôles](../mfc/controls-mfc.md)