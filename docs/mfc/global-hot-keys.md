---
title: "Touches globales d&#39;acc&#232;s rapide | Microsoft Docs"
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
  - "touches d'accès rapide (C++), touches d'accès rapide"
  - "CHotKeyCtrl (classe), touches globales d'accès rapide"
  - "touches globales d'accès rapide"
  - "raccourcis clavier (C++), touches d'accès rapide"
ms.assetid: e0b95d14-c571-4c9a-9cd1-e7fc1f0e278d
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Touches globales d&#39;acc&#232;s rapide
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une touche d'accès rapide d'agrégation est associée à une fenêtre non enfant particulière.  Cela permet à l'utilisateur d'activer la fenêtre à partir de n'importe quelle partie du système.  Une application définit une touche d'accès rapide d'agrégation pour une fenêtre particulière lors de l'envoi du message de [WM\_SETHOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646284) à cette fenêtre.  Par exemple, si `m_HotKeyCtrl` est l'objet [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) et `pMainWnd` est un pointeur vers la fenêtre à activer lorsque la touche d'accès rapide est appuyée, vous pouvez utiliser le code suivant pour associer la touche d'accès rapide spécifié dans le contrôle à la fenêtre désignée par `pMainWnd`.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#18](../mfc/codesnippet/CPP/global-hot-keys_1.cpp)]  
  
 Chaque fois que l'utilisateur presse une touche d'accès rapide d'agrégation, la fenêtre spécifiée reçoit un message de [WM\_SYSCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646360) qui spécifie **SC\_HOTKEY** comme type de la commande.  Ce message permet aussi d'activer la fenêtre qui le reçoit.  Parce que ce ce message n'inclut pas d'informations sur la clé spécifique qui a été pressée, cette méthode ne permet pas la distinction entre les différentes touches d'accès rapide qui peuvent être jointes dans la même fenêtre.  La touche d'accès rapide reste valide jusqu'à ce que l'application qui a envoyé les sorties **WM\_SETHOTKEY**.  
  
## Voir aussi  
 [Utilisation de CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)