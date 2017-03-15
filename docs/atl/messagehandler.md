---
title: "MessageHandler | Microsoft Docs"
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
  - "MessageHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MessageHandler function"
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MessageHandler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**MessageHandler** est le nom de la fonction marquée par le second paramètre de la macro d' `MESSAGE_HANDLER` dans votre table des messages.  
  
## Syntaxe  
  
```  
  
      LRESULT   
      MessageHandler  
      (  
   UINT uMsg,  
   WPARAM wParam,  
   LPARAM lParam,  
   BOOL& bHandled  
);  
```  
  
#### Paramètres  
 `uMsg`  
 Spécifie le message.  
  
 `wParam`  
 Informations supplémentaires spécifiques au message.  
  
 `lParam`  
 Informations supplémentaires spécifiques au message.  
  
 `bHandled`  
 Définit `bHandled` de table des messages à **TRUE** avant `MessageHandler` est appelée.  Si `MessageHandler` ne gère pas complètement le message, il doit définir `bHandled` à **FALSE** pour indiquer le message nécessite un traitement davantage.  
  
## Valeur de retour  
 Le résultat du traitement des messages.  0 si l'opération a réussi.  
  
## Notes  
 Pour obtenir un exemple d'utiliser ce gestionnaire de messages dans une table des messages, consultez [MESSAGE\_HANDLER](../Topic/MESSAGE_HANDLER.md).  
  
## Voir aussi  
 [Implementing a Window](../atl/implementing-a-window.md)   
 [Message Maps](../atl/message-maps-atl.md)   
 [WM\_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)