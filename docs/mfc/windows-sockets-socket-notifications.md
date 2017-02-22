---
title: "Windows Sockets&#160;: notifications de socket | Microsoft Docs"
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
  - "notifications, socket"
  - "sockets (C++), notifications"
  - "Windows Sockets (C++), notifications"
ms.assetid: 87d5bf70-6e77-49a9-9a64-aaadee2ad018
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Windows Sockets&#160;: notifications de socket
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article décrit les fonctions de notification dans les classes de chiffrement.  Ces méthodes sont des fonctions de rappel que l'infrastructure appelle pour notifier l'objet socket d'événements importants.  Les fonctions de notification sont :  
  
-   [OnReceive](../Topic/CAsyncSocket::OnReceive.md): Notifie le socket qu'il y a des données dans la mémoire tampon pour qu'elle les extraie en appelant [Recevoir](../Topic/CAsyncSocket::Receive.md).  
  
-   [OnSend](../Topic/CAsyncSocket::OnSend.md): Notifie le socket que vous pouvez maintenant envoyer des données en appelant [Envoyer](../Topic/CAsyncSocket::Send.md).  
  
-   [OnAccept](../Topic/CAsyncSocket::OnAccept.md): Notifie le socket qui écoute qu'il peut accepter des demandes de connections en attente en appelant [Accepter](../Topic/CAsyncSocket::Accept.md).  
  
-   [OnConnect](../Topic/CAsyncSocket::OnConnect.md): Notifie le socket de la connexion que sa tentative de connection est terminée : soit correctement soit de manière erronée.  
  
-   [OnClose](../Topic/CAsyncSocket::OnClose.md): Notifie le socket que le socket auquel il est connecté a fermé.  
  
    > [!NOTE]
    >  Une fonction de notification supplémentaire est [OnOutOfBandData](../Topic/CAsyncSocket::OnOutOfBandData.md).  Cette notification indique au socket récepteur que le socket d'émission détient des données « hors plage » à envoyer.  Les données hors plage sont des canaux indépendants d'un point de vue logique et associés à chaque paire de flux de sockets connectés.  Le caractère hors plage est généralement utilisé pour envoyer des données « urgentes ».  MFC prend en charge les données hors bande.  Les utilisateurs expérimentés qui utilisent la classe [CAsyncSocket](../mfc/reference/casyncsocket-class.md) pourraient avoir besoin d'utiliser le canal hors plage, mais il est déconseillé aux utilisateurs de la classe [CSocket](../mfc/reference/csocket-class.md) de l'utiliser.  Le moyen le plus simple consiste à créer un deuxième socket pour passer de telles données.  Pour plus d'informations sur les données hors bande, consultez la spécification de protocole Windows, disponible dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 Si vous dérivez de la classe `CAsyncSocket`, vous devez substituer les fonctions de notification pour les événements de réseau qui intéressent l'application.  Si vous dérivez une classe de la classe `CSocket`, c'est à vous de décider si vous voulez ou non remplacer les fonctions de notification d'intérêt.  Vous pouvez également utiliser `CSocket` lui\-même, auquel cas les fonctions de notification sont règlées par défaut sur "ne rien faire".  
  
 Ces fonctions sont des fonctions de rappel substituables.  `CAsyncSocket` et `CSocket` convertissent les messages de notification, mais vous devez implémenter la façon dont les fonctions de notification répondent si vous souhaitez les utiliser.  Les fonctions de notification sont appelées au moment où le socket est notifié d'un événement d'intérêt, tel que la présence de données à lire.  
  
 MFC appelle les fonctions de notification pour vous permettre de personnaliser le comportement de votre socket lorsqu'il est notifié.  Par exemple, vous pouvez appeler **Recevoir** depuis votre fonction de notification `OnReceive`, c. \- à\-d., lorsqu'on vous signale qu'il existe des données à lire, vous appelez **Recevoir** pour les lire.  Cette méthode n'est pas nécessaire, mais il s'agit d'un scénario valide.  Ou bien, vous pouvez utiliser la fonction de notification pour suivre la progression, imprimer les messages de **TRACE**, et ainsi de suite.  
  
 Vous pouvez tirer parti de ces notifications en remplaçant les fonctions de notification dans une classe dérivée de sockets et en fournissant une implémentation.  
  
 Pendant une opération telle que recevoir ou envoyer des données, un objet `CSocket` devient synchrone.  Pendant l'état synchrone, toutes les notifications destinées à d'autres sokets sont mises en file d'attente lorsque le socket actuel attend la notification qu'il requiert. \(Par exemple, pendant un appel de **Recevoir**, le socket requiert une notification pour lire.\) Une fois que le socket termine son opération synchrone et devient à nouveau asynchrone, d'autres sockets peuvent recevoir les notifications en file d'attente.  
  
> [!NOTE]
>  Dans `CSocket`, la fonction de notification `OnConnect` n'est jamais appelée.  Pour les connections, vous appelez **Connecter**, qui retourne lorsque la connection s'est terminée \(correctement ou de manière erronée\).  La façon dont les notifications de connection sont traitées est un ensemble d'implémentation MFC.  
  
 Pour plus d'informations sur chaque fonction de notification, consultez la fonction sous la classe `CAsyncSocket` dans *le guide de MFC*.  Pour le code source et des informations sur les exemples de MFC, consultez les [Exemples MFC](../top/visual-cpp-samples.md).  
  
 Pour plus d'informations, consultez :  
  
-   [Windows Sockets : utilisation de la classe CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Sockets : dérivation à partir des classes de sockets](../mfc/windows-sockets-deriving-from-socket-classes.md)  
  
-   [Windows Sockets : fonctionnement des sockets avec des archives](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows Sockets : blocage](../mfc/windows-sockets-blocking.md)  
  
-   [Windows Sockets : classement des octets](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows Sockets : conversion de chaînes](../mfc/windows-sockets-converting-strings.md)  
  
## Voir aussi  
 [Windows Sockets dans MFC](../mfc/windows-sockets-in-mfc.md)