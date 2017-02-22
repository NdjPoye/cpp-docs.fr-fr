---
title: "NotifyHandler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "NotifyHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NotifyHandler function"
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# NotifyHandler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le nom de la fonction marquée par le troisième paramètre de la macro d' `NOTIFY_HANDLER` dans votre table des messages.  
  
## Syntaxe  
  
```  
  
      LRESULT   
      NotifyHandler  
      (  
   int idCtrl,  
   LPNMHDR pnmh,  
   BOOL& bHandled   
);  
```  
  
#### Paramètres  
 `idCtrl`  
 L'identificateur de l'émission de contrôle le message.  
  
 *pnmh*  
 Adresse d'une structure de [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) qui contient le code de notifications et des informations supplémentaires.  Pour certains messages de notification, points de ce paramètre à une plus grande structure dans laquelle la structure de **NMHDR** comme premier membre.  
  
 `bHandled`  
 La table des messages définit `bHandled` à **TRUE** avant *NotifyHandler* soit appelé.  Si *NotifyHandler* ne gère pas complètement le message, il doit définir `bHandled` à **FALSE** pour indiquer le message nécessite un traitement davantage.  
  
## Valeur de retour  
 Le résultat du traitement des messages.  0 si l'opération a réussi.  
  
## Notes  
 Pour obtenir un exemple d'utiliser ce gestionnaire de messages dans une table des messages, consultez [NOTIFY\_HANDLER](../Topic/NOTIFY_HANDLER.md).  
  
## Voir aussi  
 [Implementing a Window](../atl/implementing-a-window.md)   
 [Message Maps](../atl/message-maps-atl.md)   
 [WM\_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)