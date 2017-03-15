---
title: "Windows Sockets&#160;: d&#233;rivation &#224; partir des classes de sockets | Microsoft Docs"
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
  - "classes dérivées, de classes de sockets"
  - "sockets (C++), dériver de classes de sockets"
  - "Windows Sockets (C++), dériver de classes de sockets"
ms.assetid: 3a26e67a-e323-433b-9b05-eca018799801
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Sockets&#160;: d&#233;rivation &#224; partir des classes de sockets
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article décrit certaines fonctionnalités que vous pouvez gagner en dérivant votre propre classe de l'une des classes de chiffrement.  
  
 Vous pouvez dériver vos propres classes de chiffrement de [CAsyncSocket](../mfc/reference/casyncsocket-class.md) ou de [CSocket](../mfc/reference/csocket-class.md) pour ajouter votre propre fonctionnalité.  En particulier, ces classes fournissent plusieurs méthodes virtuelles que vous pouvez remplacer.  Ces fonctions sont [OnReceive](../Topic/CAsyncSocket::OnReceive.md), [OnSend](../Topic/CAsyncSocket::OnSend.md), [OnAccept](../Topic/CAsyncSocket::OnAccept.md), [OnConnect](../Topic/CAsyncSocket::OnConnect.md), et [OnClose](../Topic/CAsyncSocket::OnClose.md).  Vous pouvez remplacer les fonctions dans la classe de sockets dérivée pour tirer parti des notifications qu'elles indiquent si les événements de réseau se produisent.  L'infrastructure appelle les fonctions de rappel de notification pour vous informer des événements importants de socket, tels que la réception des données que vous pouvez commencer à lire.  Pour plus d'informations sur les fonctions de notification, consultez [Protocole Windows : Notifications de socket](../mfc/windows-sockets-socket-notifications.md).  
  
 En outre, la classe `CSocket` fournit une méthode [OnMessagePending](../Topic/CSocket::OnMessagePending.md) \(substituable avancé\).  MFC appelle cette fonction lorsque le socket pompe les messages Windows.  Vous pouvez remplacer `OnMessagePending` pour rechercher des messages particuliers de Windows et répondre à ceux\-ci.  
  
 La version par défaut de `OnMessagePending` fourni dans la classe `CSocket` examine la file d'attente de messages pour les messages `WM_PAINT` en attendant la complétion d'un appel de blocage.  Elle distribue les messages de peinture pour améliorer la qualité d'affichage.  A part effectuer une opération utile, il illustre une façon de remplacer la fonction vous\-même.  À titre d'autre exemple, envisagez d'utiliser `OnMessagePending` pour la tâche suivante.  Supposons que vous affichez une boîte de dialogue non modale pendant l'attente d'une transaction de réseau.  La boîte de dialogue contient un bouton Annuler que l'utilisateur peut utiliser pour annuler les transactions bloquantes qui prennent trop de temps.  La substitution de `OnMessagePending` peut pomper des messages liés à cette boîte de dialogue non modale.  
  
 Dans votre substituion de `OnMessagePending`, retournez **TRUE** ou le retour d'un appel à la version de la classe de base de `OnMessagePending`.  Appelez la version de la classe de base si elle exécute le travail que vous souhaitez effectué.  
  
 Pour plus d'informations, consultez :  
  
-   [Windows Sockets : utilisation de sockets avec des archives](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Sockets : utilisation de la classe CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Sockets : blocage](../mfc/windows-sockets-blocking.md)  
  
-   [Windows Sockets : classement des octets](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows Sockets : conversion de chaînes](../mfc/windows-sockets-converting-strings.md)  
  
## Voir aussi  
 [Windows Sockets dans MFC](../mfc/windows-sockets-in-mfc.md)