---
title: "CommandHandler | Microsoft Docs"
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
  - "CommandHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CommandHandler function"
ms.assetid: 662bc7bf-4a10-42b3-986d-d8bae4f63551
caps.latest.revision: 13
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CommandHandler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CommandHandler` est la fonction marquée par le troisième paramètre de la macro d' `COMMAND_HANDLER` dans votre table des messages.  
  
## Syntaxe  
  
```  
  
      LRESULT   
      CommandHandler  
      (  
   WORD wNotifyCode,  
   WORD wID,  
   HWND hWndCtl,  
   BOOL& bHandled   
);  
```  
  
#### Paramètres  
 `wNotifyCode`  
 Code de notification.  
  
 *wID*  
 L'identificateur de l'élément de menu, le contrôle, ou de l'accélérateur.  
  
 *hWndCtl*  
 Un handle d'un contrôle de fenêtre.  
  
 `bHandled`  
 Définit `bHandled` de table des messages à **TRUE** avant `CommandHandler` est appelée.  Si `CommandHandler` ne gère pas complètement le message, il doit définir `bHandled` à **FALSE** pour indiquer le message nécessite un traitement davantage.  
  
## Valeur de retour  
 Le résultat du traitement des messages.  0 si l'opération a réussi.  
  
## Notes  
 Pour obtenir un exemple d'utiliser ce gestionnaire de messages dans une table des messages, consultez [COMMAND\_HANDLER](../Topic/COMMAND_HANDLER.md).  
  
## Voir aussi  
 [Implementing a Window](../atl/implementing-a-window.md)   
 [Message Maps](../atl/message-maps-atl.md)   
 [WM\_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)