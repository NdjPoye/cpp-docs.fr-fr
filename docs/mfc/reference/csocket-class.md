---
title: "CSocket Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSocket"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSocket class"
  - "SOCKET handle"
  - "sockets classes"
  - "WinSock CSocket class"
ms.assetid: 7f23c081-d24d-42e3-b511-8053ca53d729
caps.latest.revision: 30
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSocket Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dérive d' `CAsyncSocket`, hérite l'encapsulation de l'API Windows Sockets, et représente un niveau d'abstraction que celui d'un objet d' `CAsyncSocket` .  
  
## Syntaxe  
  
```  
class CSocket : public CAsyncSocket  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSocket::CSocket](../Topic/CSocket::CSocket.md)|Construit un objet `CSocket`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSocket::Attach](../Topic/CSocket::Attach.md)|Joint un handle de **SOCKET** à un objet d' `CSocket` .|  
|[CSocket::CancelBlockingCall](../Topic/CSocket::CancelBlockingCall.md)|Annule un appel bloquant qui est actuellement en cours.|  
|[CSocket::Create](../Topic/CSocket::Create.md)|Crée un socket.|  
|[CSocket::FromHandle](../Topic/CSocket::FromHandle.md)|Retourne un pointeur vers un objet d' `CSocket` , étant donné un handle de **SOCKET** .|  
|[CSocket::IsBlocking](../Topic/CSocket::IsBlocking.md)|Détermine si un appel bloquant est en cours.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CSocket::OnMessagePending](../Topic/CSocket::OnMessagePending.md)|Appelé pour traiter en attente des messages en attendant qu'un appel bloquant se termine.|  
  
## Notes  
 `CSocket` fonctionne avec les classes `CSocketFile` et `CArchive` pour gérer l'envoi et la réception de données.  
  
 Un objet d' `CSocket` fournit également le blocage, qui est essentiel pour déboguer synchrone d' `CArchive`.  Bloquant s'exécute, telles que `Receive`, `Send`, `ReceiveFrom`, `SendTo`, et `Accept` \(tout hérité d' `CAsyncSocket`\), ne retournent pas une erreur d' `WSAEWOULDBLOCK` dans `CSocket`.  À la place, ces fonctions attendent jusqu'à ce que l'opération se termine.  En outre, l'appel d'origine se terminera à l'erreur `WSAEINTR` si `CancelBlockingCall` est appelé pendant qu'un de ces fonctions bloque.  
  
 Pour utiliser un objet d' `CSocket` , appelez le constructeur, l'appel `Create` pour créer le handle sous\-jacent d' `SOCKET` \(type `SOCKET`\).  Les paramètres par défaut d' `Create` créent un socket flux, mais si vous n'utilisez pas de socket avec un objet d' `CArchive` , vous pouvez spécifier un paramètre pour créer un socket datagramme à la place, ou le lier à un port spécifique pour créer un socket de serveur.  Connectez \-vous à un socket client à l'aide de `Connect` côté client et `Accept` côté serveur.  Créez ensuite un objet d' `CSocketFile` et associez \-le à l'objet d' `CSocket` dans le constructeur d' `CSocketFile` .  Ensuite, créez un objet d' `CArchive` pour envoyer et un pour recevoir les données \(si nécessaire\), puis associez des avec l'objet d' `CSocketFile` dans le constructeur d' `CArchive` .  Lorsque les communications sont terminées, détruisez `CArchive`, `CSocketFile`, et les objets d' `CSocket` .  Le type de données d' `SOCKET` est décrite dans l'article [Windows Sockets : Arrière\-plan](../../mfc/windows-sockets-background.md).  
  
 Lorsque vous utilisez `CArchive` avec `CSocketFile` et `CSocket`, vous pouvez rencontrer une situation où `CSocket::Receive` écrit une boucle \(par `PumpMessages(FD_READ)`\) attend la quantité demandée d'octets.  C'est parce que les Winsocks permettent un seul appel de recv par notification de FD\_READ, mais `CSocketFile` et `CSocket` permettent de plusieurs appels de recv par FD\_READ.  Si vous obtenez un FD\_READ lorsqu'il n'y a pas de données à lire, l'application s'arrête.  Si vous n'obtenez jamais un autre FD\_READ, l'application arrête de communiquer de socket.  
  
 Vous pouvez résoudre ce problème comme suit.  Dans la méthode d' `OnReceive` de votre classe de sockets, appelez `CAsyncSocket::IOCtl(FIONREAD, ...)` avant d'appeler la méthode d' `Serialize` de votre classe de message lorsque les données destinées à lire du socket dépassent la taille d'un à en\-tête pack TCP \(max communication Unit de la prise en charge de réseau, généralement au moins de 1096 octets\).  Si la taille des données disponibles est moins que nécessaire, attendez que les données à accepter puis démarrez que l'opération de lecture.  
  
 Dans l'exemple suivant, `m_dwExpected` est le nombre d'octets approximatif que l'utilisateur compte recevoir.  On suppose que vous le déclarez ailleurs dans votre code.  
  
 [!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/CPP/csocket-class_1.cpp)]  
  
> [!NOTE]
>  À l'aide de sockets MFC dans les threads secondaires dans une application liée statiquement MFC, vous devez appeler `AfxSocketInit` dans chaque thread qui utilise des sockets pour initialiser les bibliothèques de socket.  Par défaut, `AfxSocketInit` est appelé uniquement dans le thread principal.  
  
 Pour plus d'informations, consultez [Windows Sockets dans MFC](../../mfc/windows-sockets-in-mfc.md), [Windows Sockets : Utilisation des sockets avec des archives](../../mfc/windows-sockets-using-sockets-with-archives.md), [Windows Sockets : comment les sockets avec des archives fonctionnent](../../mfc/windows-sockets-how-sockets-with-archives-work.md), [Windows Sockets : Ordre des opérations](../../mfc/windows-sockets-sequence-of-operations.md), [Windows Sockets : Exemple de sockets utilisation des archives](../../mfc/windows-sockets-example-of-sockets-using-archives.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAsyncSocket](../../mfc/reference/casyncsocket-class.md)  
  
 `CSocket`  
  
## Configuration requise  
 **en\-tête :** afxsock.h  
  
## Voir aussi  
 [CAsyncSocket Class](../../mfc/reference/casyncsocket-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket Class](../../mfc/reference/casyncsocket-class.md)   
 [CSocketFile Class](../../mfc/reference/csocketfile-class.md)