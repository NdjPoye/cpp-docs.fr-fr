---
title: "Windows Sockets&#160;: arri&#232;re-plan | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "communications (C++), de domaine"
  - "types de données (C++), socket"
  - "sockets datagramme (C++)"
  - "messagerie électronique (C++)"
  - "messagerie électronique (C++), programmer pour"
  - "protocoles Internet (suite)"
  - "messagerie (C++)"
  - "messagerie (C++), programmer pour"
  - "données orientées par enregistrement (C++)"
  - "flux de données séquencées"
  - "SOCKET (handle)"
  - "sockets (C++), sockets flux"
  - "sockets flux (C++)"
  - "Windows Sockets (C++), sockets flux"
  - "X Window (serveurs)"
ms.assetid: f60d4ed2-bf23-4a0e-98d2-fee77e8473dd
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Sockets&#160;: arri&#232;re-plan
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique la nature et la fonction de Windows Sockets.  Aussi, l'article :  
  
-   [Définit le terme « socket »](#_core_definition_of_a_socket).  
  
-   [Décrit le type de données de handle de SOCKET](#_core_the_socket_data_type).  
  
-   [Décrit les utilisations de sockets](#_core_uses_for_sockets).  
  
 La spécification Windows Sockets définit une interface de programmation de réseau binaire pour Microsoft Windows.  Windows Sockets est basé sur l'implémentation de sockets UNIX dans Berkeley Software Distribution \(schéma, version 4,3\) de l'Université de Californie à Berkeley.  La spécification inclut les deux routines et extensions de style du schéma de socket spécifiques à Windows.  L'utilisation de Windows Sockets permet à votre application de communiquer à travers tout réseau conforme à Windows Sockets API.  Dans Win32, Windows Sockets fournit une sécurité au niveau des threads.  
  
 De nombreux éditeurs logiciels réseau prennent en charge Windows Sockets sous des protocoles réseau dont le protocole TCP\/IP \(TCP\/IP\), le Xerox Network System \(XNS\), protocole du DECnet Equipment Corporation, en\-tête pack Internet de Novell Corporation's Exchange\/Exchange compressé séquencé \(IPX\/SPX\), et d'autres.  Bien que la spécification actuelle de Windows Sockets définit l'abstraction de sockets pour TCP\/IP, n'importe quel protocole réseau peut être conforme à Windows Sockets par sa propre version de la bibliothèque de liens dynamiques \(DLL\) qui implémente Windows Sockets.  Voici quelques exemples d'applications commerciales écrites avec Windows Sockets incluant des serveurs X Windows, les émulateurs terminaux, et les systèmes de messagerie.  
  
> [!NOTE]
>  Le but de Windows Sockets est d'abréger loin le réseau sous\-jacent afin que vous n'ayez pas à connaître parfaitement le réseau et que votre application puisse fonctionner sur tout réseau qui prend en charge des sockets.  Par conséquent, cette documentation ne traite pas les détails des protocoles réseau.  
  
 La bibliothèque MFC \(Microsoft Foundation Class\) prend en charge la programmation avec l'API Windows Sockets en fournissant deux classes.  L'une de ces classes, `CSocket`, fournit un niveau élevé d'abstraction pour simplifier la programmation de communication réseau.  
  
 La spécification Windows Sockets, Windows Sockets : Une interface ouverte pour Network Computing Under Microsoft Windows, maintenant à la version 1.1, a été développée comme un réseau ouvert standard par un grand groupe de personnes et des sociétés de la communauté de TCP\/IP et est librement disponible.  Le modèle de programmation de sockets prend actuellement en charge un « domaine de communication », à la suite de protocoles Internet.  La spécification est disponible dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
> [!TIP]
>  Les sockets utilisent la suite de protocoles Internet, ils sont l'itinéraire par défaut pour les applications qui prennent en charge les communications Internet sur « autoroute Information ».  
  
##  <a name="_core_definition_of_a_socket"></a> Définition d'un Socket  
 Un socket est un point de terminaison de communication \(un objet via lequel une application Windows Sockets envoie ou reçoit des paquets de données sur un réseau.  Un socket a un type et est associé à un processus en cours de exécution, et peut avoir un nom.  Actuellement, des sockets échangent généralement des données seulement avec les autres sockets dans le même "domaine de communication" qui utilise Internet Protocol Suite.  
  
 Les deux types de sockets sont bidirectionnelles ; leur flux de données peuvent être communiqués dans les deux directions simultanément \(bidirectionnel simultané\).  
  
 Deux types de socket sont disponibles :  
  
-   Sockets flux  
  
     Les sockets flux prévoient un flux de données sans limites d'enregistrement : un flux d'octets.  Les flux sont nécessairement délivré et correctement séquencés et non\-dupliqués.  
  
-   Sockets datagramme  
  
     Les sockets datagramme prennent en charge un flux de données destiné à l'enregistrement qui se retrouvera remis et qui ne peut pas être séquencé comme un flux enregistré ou non\-dupliqué.  
  
 « Ordonnancé » signifie que des paquets sont remis dans l'ordre envoyé. « Unduplicated » signifie que vous obtenez un paquet particulier une seule fois.  
  
> [!NOTE]
>  Sous certains protocoles réseau, tels que le XNS, les flux peuvent être destinés à l'enregistrement, en tant que flux d'enregistrements plutôt que des flux d'octets.  Sous le protocole TCP\/IP plus courant, toutefois, les flux sont des flux d'octets.  Windows Sockets fournit un niveau d'abstraction indépendant du protocole sous\-jacent.  
  
 Pour plus d'informations sur ces types et le type de socket à utiliser dans les situations, consultez [Windows Sockets : Sockets flux](../mfc/windows-sockets-stream-sockets.md) et [Windows Sockets : Sockets datagramme](../mfc/windows-sockets-datagram-sockets.md).  
  
##  <a name="_core_the_socket_data_type"></a> Type de données SOCKET  
 Chaque objet socket MFC encapsule un handle vers un objet Windows Sockets.  Le type de données de ce handle est **SOCKET**.  Un handle **SOCKET** est analogue à `HWND` pour une fenêtre.  Les classes de sockets MFC fournissent des opérations sur le handle encapsulé.  
  
 Le type de données **SOCKET** est décrit en détail dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  Consultez « type de données et valeurs d'erreur de socket » sous Windows Sockets.  
  
##  <a name="_core_uses_for_sockets"></a> Utilisations des sockets  
 Les sockets sont très utiles dans au moins trois contextes de communication :  
  
-   Modèles client\/serveur.  
  
-   Scénarios peer\-to\-peer, comme les applications de messagerie.  
  
-   Effectuer des appels de procédure distants \(RPC\) en quittant l'application de réception intereprete un message comme un appel de fonction.  
  
> [!TIP]
>  Le cas idéal pour utiliser MFC sockets est lorsque vous écrivez les deux extrémités de la communication : utilisant MFC aux deux extrémités.  Pour plus d'informations sur cette rubrique, notamment sur comment gérer le cas lorsque vous communiquez avec les applications non\-MFC, consultez [Windows Sockets : Commande d'octet](../mfc/windows-sockets-byte-ordering.md).  
  
 Pour plus d'informations, consultez la spécification Windows Sockets : **ntohs**, **ntohl**, **htons**, **htonl**.  Aussi, consultez les rubriques suivantes :  
  
-   [Windows Sockets : utilisation de sockets avec des archives](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Sockets : exemple de sockets utilisant des archives](../mfc/windows-sockets-example-of-sockets-using-archives.md)  
  
-   [Windows Sockets : utilisation de la classe CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
## Voir aussi  
 [Windows Sockets dans MFC](../mfc/windows-sockets-in-mfc.md)