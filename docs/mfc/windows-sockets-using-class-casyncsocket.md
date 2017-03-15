---
title: "Windows Sockets&#160;: utilisation de la classe CAsyncSocket | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CAsyncSocket"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAsyncSocket (classe), modèle de programmation"
  - "SOCKET (handle)"
  - "sockets (C++), opération asynchrone"
  - "sockets (C++), convertir entre chaînes Unicode et MBCS"
  - "Windows Sockets (C++), asynchrones"
  - "Windows Sockets (C++), convertir des chaînes Unicode et MBCS"
ms.assetid: 825dae17-7c1b-4b86-8d6c-da7f1afb5d8d
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Windows Sockets&#160;: utilisation de la classe CAsyncSocket
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment utiliser la classe [CAsyncSocket](../mfc/reference/casyncsocket-class.md).  Notez que cette classe encapsule l'API Windows Sockets à très à un niveau.  `CAsyncSocket` est destinée aux programmeurs qui connaissent les communications réseau en détail mais souhaitent simplifier les rappels pour la notification d'événements réseau.  Selon cette hypothèse, cet article prédit que des instructions de base.  Pensez à utiliser `CAsyncSocket` si vous souhaitez bénéficier de la facilité de Windows Sockets de traiter plusieurs protocoles réseau dans une application MFC mais ne souhaitez pas sacrifier la souplesse.  Vous pourriez également estimer pouvoir obtenir une meilleure efficacité en programmant les communications plus directement vous\-même qu'en utilisant l'autre modèle plus général de classe `CSocket`.  
  
 `CAsyncSocket` est documentée dans la *référence MFC*.  Visual C\+\+ fournit également la spécification de Windows Sockets, située dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  Les détails ne sont pas traités ici.  Visual C\+\+ ne fournit pas un exemple d'application pour `CAsyncSocket`.  
  
 Si vous n'êtes pas très bien informé sur les communications réseau et souhaitez une solution simple, utilises la classe [CSocket](../mfc/reference/csocket-class.md) avec un objet `CArchive`.  Pour plus d'informations, consultez [Windows Sockets : Utilisation de sockets d'archive](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
 Cet article explique:  
  
-   Création et utilisation d'un objet `CAsyncSocket`.  
  
-   [Vos responsabilités avec CAsyncSocket](#_core_your_responsibilities_with_casyncsocket).  
  
##  <a name="_core_creating_and_using_a_casyncsocket_object"></a> Création et utilisation un objet CAsyncSocket  
  
#### Pour utiliser CAsyncSocket  
  
1.  Construisez un objet [CAsyncSocket](../mfc/reference/casyncsocket-class.md) et utilisez l'objet pour créer le handle sous\-jacent de **SOCKET**.  
  
     La création d'un socket suit le modèle MFC de construction à deux niveaux.  
  
     Par exemple :  
  
     [!code-cpp[NVC_MFCSimpleSocket#3](../mfc/codesnippet/CPP/windows-sockets-using-class-casyncsocket_1.cpp)]  
  
     ou  
  
     [!code-cpp[NVC_MFCSimpleSocket#4](../mfc/codesnippet/CPP/windows-sockets-using-class-casyncsocket_2.cpp)]  
  
     Le premier constructeur ci\-dessus crée un objet `CAsyncSocket` dans la pile.  Le deuxième constructeur crée `CAsyncSocket` sur le tas.  Le premier appel à [Créer](../Topic/CAsyncSocket::Create.md) utilise les paramètres par défaut pour créer un socket flux.  Le deuxième appel à **Créer** crée un socket datagramme avec un port TCP\/IP et une adresse spécifiés. \(Vous pouvez utiliser l'une ou l'autre des version de **Créer** avec l'une ou l'autre des méthodes de construction.\)  
  
     Les paramètres à **Créer** sont :  
  
    -   Un "port" : un entier court.  
  
         Pour un socket de serveur, vous devez spécifier un port.  Pour un socket client, vous obtenez généralement la valeur par défaut de ce paramètre, ce qui permet à Windows Sockets de sélectionner un port.  
  
    -   Un type de socket : **SOCK\_STREAM** \(par défaut\) ou **SOCK\_DGRAM**.  
  
    -   Un socket "adresse", comme « ftp.microsoft.com » ou « 128.56.22.8 ».  
  
         Il s'agit de votre adresse IP sur le réseau.  Vous compterez probablement toujours sur la valeur par défaut de ce paramètre.  
  
     Les termes « port » et « adresse de socket » sont décrits dans [Windows Sockets : Ports et adresse de socket](../mfc/windows-sockets-ports-and-socket-addresses.md).  
  
2.  Si le socket est un client, connectez l'objet socket à un socket de serveur, en utilisant [CAsyncSocket::Connect](../Topic/CAsyncSocket::Connect.md).  
  
     ou  
  
     Si le socket est un serveur, définissez le socket pour démarrer l'écoute \(avec [CAsyncSocket::Listen](../Topic/CAsyncSocket::Listen.md)\) pour des tentatives de connexion d'un client.  Lors de la réception d'une demande de connexion, recevez\-la avec [CAsyncSocket::Accept](../Topic/CAsyncSocket::Accept.md).  
  
     Après avoir reçu une connexion, vous pouvez effectuer des tâches telles que la validation des mots de passe.  
  
    > [!NOTE]
    >  La fonction membre **Accepter** prend une référence à un nouvel objet vide `CSocket` comme paramètre.  Vous devez créer cet objet avant d'appeler **Accepter**.  Si cet objet socket est hors de portée, la connexion se ferme.  N'appelez pas **Créer** pour ce nouvel objet socket.  Pour obtenir un exemple, consultez l'article [Windows Sockets : Séquence d'événements](../mfc/windows-sockets-sequence-of-operations.md).  
  
3.  Effectuez les communications avec d'autres sockets en appelant les fonctions membres de l'objet `CAsyncSocket` qui encapsulent les fonctions de l'API Windows Sockets.  
  
     Consultez la spécification et la classe de Windows Sockets et [CAsyncSocket](../mfc/reference/casyncsocket-class.md) dans *le guide de MFC*.  
  
4.  Détruisez l'objet `CAsyncSocket`.  
  
     Si vous avez créé l'objet socket dans la pile, le destructeur est appelé lorsque la fonction conteneur devient hors de portée.  Si vous avez créé l'objet socket sur le segment, en utilisant l'opérateur **new**, vous êtes chargé d'utiliser l'opérateur de **supprimer** pour détruire l'objet.  
  
     Le destructeur appelle la fonction membre [Fermer](../Topic/CAsyncSocket::Close.md) de l'objet avant de détruire l'objet.  
  
 Pour obtenir un exemple de cette séquence du code \(pour un objet de `CSocket` \), consultez [Windows Sockets : Séquence d'événements](../mfc/windows-sockets-sequence-of-operations.md).  
  
##  <a name="_core_your_responsibilities_with_casyncsocket"></a> Vos responsabilités avec CAsyncSocket.  
 Lorsque vous créez un objet de la classe [CAsyncSocket](../mfc/reference/casyncsocket-class.md), l'objet encapsule un handle Windows **SOCKET** et fournit des opérations sur ce handle.  Lorsque vous utilisez `CAsyncSocket`, vous devez traiter tous les problèmes susceptibles d'être rencontrés si vous utilisez l'API.  Par exemple :  
  
-   « Sélection en bloc » des scénarios.  
  
-   Différences dans l'ordre des octets entre la machine émettrice et réceptrice.  
  
-   Conversion de chaînes Unicode et de jeu de caractères multioctets \(MBCS\).  
  
 Pour les définitions des termes et des informations supplémentaires, consultez [Windows Sockets : Blocage](../mfc/windows-sockets-blocking.md), [Windows Sockets : Ordre d'octets](../mfc/windows-sockets-byte-ordering.md), [Windows Sockets : La conversion de chaînes](../mfc/windows-sockets-converting-strings.md).  
  
 En dépit de ces problèmes, la classe **CAsycnSocket** peut être le bon choix pour vous si votre application nécessite une souplesse et le contrôle qu'on peut obtenir.  Sinon, vous devez envisager d'utiliser la classe `CSocket` à la place.  `CSocket` vous cahce de nombreux détails : cela pompe des messages Windows lors du blocage d'appels et vous donne accès à `CArchive`, qui gère les différences d'ordre d'octets et la conversion de chaînes pour vous.  
  
 Pour plus d'informations, consultez :  
  
-   [Windows Sockets : arrière\-plan](../mfc/windows-sockets-background.md)  
  
-   [Windows Sockets : sockets flux](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Sockets : sockets datagramme](../mfc/windows-sockets-datagram-sockets.md)  
  
## Voir aussi  
 [Windows Sockets dans MFC](../mfc/windows-sockets-in-mfc.md)