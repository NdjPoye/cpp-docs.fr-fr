---
title: "Windows Sockets&#160;: utilisation de sockets avec des archives | Microsoft Docs"
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
  - "archives (C++), et Windows Sockets"
  - "CSocket (classe), modèle de programmation"
  - "sockets (C++), avec archives"
  - "Windows Sockets (C++), archives"
ms.assetid: 17e71a99-a09e-4e1a-9fda-13d62805c824
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Sockets&#160;: utilisation de sockets avec des archives
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique le [Modèle de programmation CSocket](#_core_the_csocket_programming_model).  La classe [CSocket](../mfc/reference/csocket-class.md) fournit la prise en charge de socket à un niveau supérieur d'abstraction que celui de la classe [CAsyncSocket](../mfc/reference/casyncsocket-class.md).  `CSocket` utilise une version du protocole de sérialisation MFC pour passer des données vers et à partir d'un objet socket via un objet MFC [CArchive](../mfc/reference/carchive-class.md).  `CSocket` fournit un blocage \(lors de la gestion du traitement en arrière\-plan des messages windows\) et vous donne accès à `CArchive`, qui gère de nombreux aspects de la communication que vous devriez faire en utilisant l'API brute ou la classe `CAsyncSocket`.  
  
> [!TIP]
>  Vous pouvez utiliser la classe `CSocket` seule, en tant que version plus pratique de`CAsyncSocket`, mais le modèle de programmation le plus simple consiste à utiliser `CSocket` avec un objet `CArchive`.  
  
 Pour plus d'informations sur la façon dont l'implémentation des sockets avec archives fonctionne, consultez [Windows Sockets : fonctionnement des sockets avec des archives](../mfc/windows-sockets-how-sockets-with-archives-work.md).  Pour obtenir un exemple de code, consultez [Windows Sockets : ordre des opérations](../mfc/windows-sockets-sequence-of-operations.md) and [Windows Sockets : exemple de sockets utilisant des archives](../mfc/windows-sockets-example-of-sockets-using-archives.md).  Pour plus d'informations sur certaines fonctionnalités que vous pouvez gagner en en faisant dériver vos propres classes de classes de sockets, consultez [Windows Sockets : dérivation à partir des classes de sockets](../mfc/windows-sockets-deriving-from-socket-classes.md).  
  
> [!NOTE]
>  Si vous écrivez un programme client MFC pour communiquer avec des serveurs \(non\-MFC\) établis, n'envoyez pas les objets C\+\+ à l'archive.  Sauf si le serveur est une application de MFC qui comprend les types d'objets que vous souhaitez envoyer des, il ne peut pas recevoir et désérialiser vos objets.  Pour le matériel relatif au sujet de communication avec les applications non\-MFC, consultez également l'article [Windows Sockets : classement des octets](../mfc/windows-sockets-byte-ordering.md).  
  
##  <a name="_core_the_csocket_programming_model"></a> Le modèle de programmation de CSocket  
 L'utilisation d'un objet `CSocket` implique la création et l'association de plusieurs objets de classe de MFC.  Dans la procédure générale ci\-dessous, chaque action est effectuée par le socket de serveur et le socket client, sauf à l'étape 3, dans laquelle chaque type de socket requiert une action différente.  
  
> [!TIP]
>  Au moment de l'exécution, l'application serveur démarre généralement en premier pour être prête et « à l'écoute » lorsque l'application cliente recherche une connexion.  Si le serveur n'est pas prêt lorsque le client tente de se connecter, vous aurez généralement besoin que l'application utilisateur essaye de se connecter de nouveau ultérieurement.  
  
#### Pour installer la communication entre un socket de serveur et un socket client  
  
1.  Construisez un objet [CSocket](../mfc/reference/csocket-class.md).  
  
2.  Utilisez l'objet pour créer le handle sous\-jacent de **SOCKET**.  
  
     Pour un objet client `CSocket`, vous devez généralement utiliser les paramètres par défaut pour [Créer](../Topic/CAsyncSocket::Create.md), sauf si vous avez besoin d'un socket datagramme.  Pour un objet serveur `CSocket`, vous devez spécifier un port dans l'appel **Créer**.  
  
    > [!NOTE]
    >  `CArchive` ne fonctionne pas avec les sockets datagramme.  Si vous souhaitez utiliser `CSocket` pour un socket datagramme, vous devez utiliser la classe comme vous utiliseriez `CAsyncSocket`, c'est à dire, sans archive.  Les datagrammes sont peu fiables \(pas garanti d'arrivée et peuvent être répétés, ou hors de la séquence\), ils ne sont pas compatibles avec la sérialisation par le biais d'une archive.  Vous vous attendez à ce qu'une opération de sérialisation se termine de manière fiable et dans l'ordre.  Si vous essayez d'utiliser `CSocket` avec un objet `CArchive` pour un datagramme, une assertion de MFC échoue.  
  
3.  Si le socket est un client, appelez [CAsyncSocket::Connect](../Topic/CAsyncSocket::Connect.md) pour connecter l'objet socket à un socket de serveur.  
  
     ou  
  
     Si le socket est un serveur, appelez [CAsyncSocket::Listen](../Topic/CAsyncSocket::Listen.md) pour démarrer l'écoute sur les tentatives de connexion d'un client.  Lors de la réception d'une demande de connexion, recevez\-la en appelant [CAsyncSocket::Accept](../Topic/CAsyncSocket::Accept.md).  
  
    > [!NOTE]
    >  La fonction membre **Accepter** prend une référence à un nouvel objet vide `CSocket` comme paramètre.  Vous devez créer cet objet avant d'appeler **Accepter**.  Si cet objet socket est hors de portée, la connexion se ferme.  N'appelez pas **Créer** pour ce nouvel objet socket.  
  
4.  Créez un objet de [CSocketFile](../mfc/reference/csocketfile-class.md), lui associant l'objet `CSocket`.  
  
5.  Créez un objet de [CArchive](../mfc/reference/carchive-class.md) pour le chargement \(recevoir\) ou pour stocker des données \(d'émission\).  L'archive est associée avec l'objet `CSocketFile`.  
  
     N'oubliez pas que `CArchive` ne fonctionne pas avec les sockets datagramme.  
  
6.  Utilisez l'objet `CArchive` pour passer des données de test entre les sockets client et serveur.  
  
     Gardez à l'esprit qu'un objet donné `CArchive` déplace les données dans une seule direction : pour charger \(recevoir\) ou enregistrer \(émission\).  Dans certains cas, vous utiliserez deux objets `CArchive` : un pour envoyer des données, l'autre pour recevoir les accusés de réception.  
  
     Après la réception d'une installation de archive, vous pouvez effectuer des tâches telles que la validation des mots de passe.  
  
7.  Détruisez archive, le fichier de sockets, les objets socket.  
  
    > [!NOTE]
    >  La class `CArchive` fournit la fonction membre `IsBufferEmpty` spécifiquement pour une utilisation avec la classe `CSocket`.  Si la mémoire tampon contient plusieurs messages de données, par exemple, vous devez boucler jusqu'à ce qu'ils aient tous e\=été lus et que le tampon est vidé.  Sinon, la notification suivante selon laquelle il y a des données à recevoir peut être retardée indéfiniment.  Utilisez `IsBufferEmpty` pour vérifier que vous récupérez toutes les données.  
  
 L'article [Windows Sockets : ordre des opérations](../mfc/windows-sockets-sequence-of-operations.md) illustre les deux côtés de ce processus avec un exemple de code.  
  
 Pour plus d'informations, consultez :  
  
-   [Windows Sockets : sockets flux](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Sockets : sockets datagramme](../mfc/windows-sockets-datagram-sockets.md)  
  
## Voir aussi  
 [Windows Sockets dans MFC](../mfc/windows-sockets-in-mfc.md)   
 [CSocket::Create](../Topic/CSocket::Create.md)