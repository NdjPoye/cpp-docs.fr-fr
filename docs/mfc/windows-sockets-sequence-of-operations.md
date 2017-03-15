---
title: "Windows Sockets&#160;: ordre des op&#233;rations | Microsoft Docs"
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
  - "sockets (C++), opérations"
  - "sockets (C++), sockets flux"
  - "sockets flux (C++)"
  - "Windows Sockets (C++), opérations"
  - "Windows Sockets (C++), sockets flux"
ms.assetid: 43ce76f5-aad3-4247-b8a6-16cc7d012796
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Windows Sockets&#160;: ordre des op&#233;rations
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique, côte à côte, la séquence d'événements pour un socket serveur et un socket client.  Les sockets utilisent des objets `CArchive`, ils sont nécessairement des [sockets flux](../mfc/windows-sockets-stream-sockets.md).  
  
## Séquence d'événements pour une communication Stream Socket  
 Jusqu'à la création d'un objet `CSocketFile`, la suite est exacte \(avec quelques différences de paramètre\) pour `CAsyncSocket` et `CSocket`.  À partir de ce point, la séquence est strictement pour `CSocket`.  Le tableau suivant montre la séquence d'événements pour configurer la communication entre un client et un serveur.  
  
### Configuration des communications entre un serveur et un client  
  
|Serveur|Client|  
|-------------|------------|  
|`// construct a socket`<br /><br /> `CSocket sockSrvr;`|`// construct a socket`<br /><br /> `CSocket sockClient;`|  
|`// create the SOCKET`<br /><br /> `sockSrvr.Create(nPort);`1,2|`// create the SOCKET`<br /><br /> `sockClient.Create( );`2|  
|`// start listening`<br /><br /> `sockSrvr.Listen( );`||  
||`// seek a connection`<br /><br /> `sockClient.Connect(strAddr, nPort);`3,4|  
|`// construct a new, empty socket`<br /><br /> `CSocket sockRecv;`<br /><br /> `// accept connection`<br /><br /> `sockSrvr.Accept( sockRecv );` 5||  
|`// construct file object`<br /><br /> `CSocketFile file(&sockRecv);`|`// construct file object`<br /><br /> `CSocketFile file(&sockClient);`|  
|`// construct an archive`<br /><br /> `CArchive arIn(&file,`  `CArchive::load);`<br /><br /> ou<br /><br /> `CArchive arOut(&file,`  `CArchive::store);`<br /><br /> – ou les deux –|`// construct an archive`<br /><br /> `CArchive arIn(&file,`  `CArchive::load);`<br /><br /> ou<br /><br /> `CArchive arOut(&file,`  `CArchive::store);`<br /><br /> – ou les deux –|  
|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> ou<br /><br /> `arOut << dwValue;`6|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> ou<br /><br /> `arOut << dwValue;`6|  
  
 1.  Où `nPort` est un numéro de port.  Voir le [Protocole Windows : Ports et Adresses de Sockets](../mfc/windows-sockets-ports-and-socket-addresses.md) pour plus d'informations sur les ports.  
  
 2.  Le serveur doit toujours spécifier un port afin que les clients puissent se connecter.  L'appel à **Create** spécifie parfois également une adresse.  Côté client, utilisez les paramètres par défaut, qui demandent à MFC d'utiliser tout port disponible.  
  
 3.  Où `nPort` est un numéro de port et *un strAddr* est une adresse d'ordinateur ou une adresse Internet Protocol \(IP\).  
  
 4.  Les adresses d'ordinateur peut prendre plusieurs formes : « ftp.microsoft.com », « microsoft.com ».  Les adresses IP utilisent la forme en nombre pointés « 127.54.67.32 ».  La fonciton **Connect** vérifie si l'adresse est un nombre pointé \(bien qu'il ne vérifie pas si le nombre est un ordinateur valide sur le réseau\).  Sinon, **Connect** suppose un nom d'ordinateur de l'une des autres formes.  
  
 5.  Lorsque vous appelez **Accept** côté serveur, vous passez une référence à un objet socket.  Vous devez créer cet objet dans un premier temps, mais n'appelez pas **Create** pour celui\-ci.  N'oubliez pas que si cet objet socket sort de l'étendue, la connexion se ferme.  MFC connecte le nouvel objet à un descripteur de **SOCKET**.  Vous pouvez construire le socket dans la pile, tel qu'indiqué, ou sur le tas.  
  
 6.  L'archive et le fichier de socket sont fermés lorsqu'ils passent hors de portée.  Le destructeur de l'objet socket appelle également la méthode [Close](../Topic/CAsyncSocket::Close.md) de l'objet socket lorsque l'objet sort de l'étendue ou est supprimé.  
  
## Remarques supplémentaires sur la séquence  
 La séquence d'appels indiqués dans le tableau précédent concerne un socket flux.  Les sockets datagramme, qui sont sans connexion, ne nécessitent pas [CAsyncSocket::Connect](../Topic/CAsyncSocket::Connect.md), [Listen](../Topic/CAsyncSocket::Listen.md), et les appels à [Accept](../Topic/CAsyncSocket::Accept.md) \(bien que vous pouvez éventuellement utiliser **Connect**\).  En revanche, si vous utilisez la classe `CAsyncSocket`, les sockets datagramme utilisent les méthodes `CAsyncSocket::SendTo` et `ReceiveFrom`. \(Si vous utilisez **Connect** avec un socket datagramme, vous utilisez **Send** et **Receive**.\) Comme `CArchive` ne fonctionne pas avec les datagrammes, n'utilisez pas `CSocket` avec une archive si le socket est un datagramme.  
  
 [CSocketFile](../mfc/reference/csocketfile-class.md) ne prend pas en charge toutes les fonctionnalités de `CFile`; les membres de `CFile` comme `Seek`, qui n'ont pas de sens pour une communication de socket, ne sont pas disponibles.  Par conséquent, certaines fonctions de MFC par défault `Serialize` ne sont pas compatibles avec `CSocketFile`.  Cela est particulièrement vrai de la classe `CEditView`.  Vous ne devez pas essayer de sérialiser des données de `CEditView` via un objet `CArchive` associé à un objet `CSocketFile` en utilisant `CEditView::SerializeRaw`; utilisez **CEditView::Serialize** à la place \(non documenté\).  La fonction [SerializeRaw](../Topic/CEditView::SerializeRaw.md) attend que le fichier objet ait des fonctions, telles que `Seek`, que `CSocketFile` ne prend pas en charge.  
  
 Pour plus d'informations, consultez :  
  
-   [Windows Sockets : utilisation de sockets avec des archives](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Sockets : utilisation de la classe CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Sockets : ports et adresses de socket](../mfc/windows-sockets-ports-and-socket-addresses.md)  
  
-   [Windows Sockets : sockets flux](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Sockets : sockets datagramme](../mfc/windows-sockets-datagram-sockets.md)  
  
## Voir aussi  
 [Windows Sockets dans MFC](../mfc/windows-sockets-in-mfc.md)   
 [CSocket Class](../mfc/reference/csocket-class.md)   
 [CAsyncSocket::Create](../Topic/CAsyncSocket::Create.md)   
 [CAsyncSocket::Close](../Topic/CAsyncSocket::Close.md)