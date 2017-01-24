---
title: "Touches d&#39;acc&#232;s rapide sp&#233;cifiques aux threads | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "touches d'accès rapide (C++), touches d'accès rapide"
  - "CHotKeyCtrl (classe), touches d'accès rapide spécifiques aux threads"
  - "raccourcis clavier (C++), touches d'accès rapide"
  - "threads (C++), touches d'accès rapide dans CHotKeyCtrl"
ms.assetid: b6021274-1498-483f-bcbf-ba5723547cc8
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Touches d&#39;acc&#232;s rapide sp&#233;cifiques aux threads
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une application définit une touche d'accès rapide spécifique au thread \([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)\) à l'aide de la fonction de **RegisterHotKey** windows.  Lorsque l'utilisateur appuie sur la touche d'accès rapide spécifique au thread, windows génère un message de [WM\_HOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646279) au début de la file d'attente de messages d'un thread donné.  Le message de **WM\_HOTKEY** contient le code de clé virtuelle, l'état de l'équipe, et l'identificateur défini par l'utilisateur de la touche d'accès rapide spécifique sur laquelle on a appuyé.  Pour obtenir la liste de codes touche virtuelle standard, consultez Winuser.h.  Pour plus d'informations sur cette méthode, consultez [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309).  
  
 Notez que les indicateurs d'état de décalage utilisée dans l'appel à **RegisterHotKey** ne sont pas les mêmes que celles retournées par la fonction membre de [GetHotKey](../Topic/CHotKeyCtrl::GetHotKey.md) ; vous devez convertir ces indicateurs avant d'appeler **RegisterHotKey**.  
  
## Voir aussi  
 [Utilisation de CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)