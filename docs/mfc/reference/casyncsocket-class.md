---
title: "CAsyncSocket Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAsyncSocket"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "asynchronous Windows Sockets"
  - "CAsyncSocket class"
  - "communications (C++), réseau"
  - "network communications"
  - "sockets [C++], Windows"
  - "Windows Sockets [C++], asynchrones"
ms.assetid: cca4d5a1-aa0f-48bd-843e-ef0e2d7fc00b
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CAsyncSocket Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente un Winsock — un point de terminaison de communication réseau.  
  
## Syntaxe  
  
```  
class CAsyncSocket : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAsyncSocket::CAsyncSocket](../Topic/CAsyncSocket::CAsyncSocket.md)|Construit un objet `CAsyncSocket`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAsyncSocket::Accept](../Topic/CAsyncSocket::Accept.md)|Accepte une connexion du socket.|  
|[CAsyncSocket::AsyncSelect](../Topic/CAsyncSocket::AsyncSelect.md)|Demande la notification d'événements du socket.|  
|[CAsyncSocket::Attach](../Topic/CAsyncSocket::Attach.md)|Joint un handle de socket à un objet d' `CAsyncSocket` .|  
|[CAsyncSocket::Bind](../Topic/CAsyncSocket::Bind.md)|Associe une adresse locale du socket.|  
|[CAsyncSocket::Close](../Topic/CAsyncSocket::Close.md)|Ferme le socket.|  
|[CAsyncSocket::Connect](../Topic/CAsyncSocket::Connect.md)|Établit une connexion à un socket homologue.|  
|[CAsyncSocket::Create](../Topic/CAsyncSocket::Create.md)|Crée un socket.|  
|[CAsyncSocket::Detach](../Topic/CAsyncSocket::Detach.md)|Détache un handle de socket d'un objet d' `CAsyncSocket` .|  
|[CAsyncSocket::FromHandle](../Topic/CAsyncSocket::FromHandle.md)|Retourne un pointeur vers un objet d' `CAsyncSocket` , étant donné un handle de socket.|  
|[CAsyncSocket::GetLastError](../Topic/CAsyncSocket::GetLastError.md)|Obtient l'état d'erreur pour la dernière opération qui a échoué.|  
|[CAsyncSocket::GetPeerName](../Topic/CAsyncSocket::GetPeerName.md)|Obtient l'adresse du socket homologue auquel le socket est connecté.|  
|[CAsyncSocket::GetPeerNameEx](../Topic/CAsyncSocket::GetPeerNameEx.md)|Obtient l'adresse du socket homologue auquel le socket est connecté \(les adresses de IPv6 de handles\).|  
|[CAsyncSocket::GetSockName](../Topic/CAsyncSocket::GetSockName.md)|Obtient le nom local pour un socket.|  
|[CAsyncSocket::GetSockNameEx](../Topic/CAsyncSocket::GetSockNameEx.md)|Obtient le nom local pour un socket \(adresses de IPv6 de handles\).|  
|[CAsyncSocket::GetSockOpt](../Topic/CAsyncSocket::GetSockOpt.md)|Extrait une option de socket.|  
|[CAsyncSocket::IOCtl](../Topic/CAsyncSocket::IOCtl.md)|Contrôle le mode de socket.|  
|[CAsyncSocket::Listen](../Topic/CAsyncSocket::Listen.md)|Génère un socket pour écouter les demandes de connexion entrante.|  
|[CAsyncSocket::Receive](../Topic/CAsyncSocket::Receive.md)|Reçoit les données du socket.|  
|[CAsyncSocket::ReceiveFrom](../Topic/CAsyncSocket::ReceiveFrom.md)|Accepte un datagramme et stocke l'adresse source.|  
|[CAsyncSocket::ReceiveFromEx](../Topic/CAsyncSocket::ReceiveFromEx.md)|Accepte un datagramme et stocke l'adresse source \(adresses de IPv6 de handles\).|  
|[CAsyncSocket::Send](../Topic/CAsyncSocket::Send.md)|Envoie des données à un socket connecté.|  
|[CAsyncSocket::SendTo](../Topic/CAsyncSocket::SendTo.md)|Envoie des données à une destination spécifique.|  
|[CAsyncSocket::SendToEx](../Topic/CAsyncSocket::SendToEx.md)|Envoie des données à une destination spécifique \(adresses de IPv6 de handles\).|  
|[CAsyncSocket::SetSockOpt](../Topic/CAsyncSocket::SetSockOpt.md)|Définit une option de socket.|  
|[CAsyncSocket::ShutDown](../Topic/CAsyncSocket::ShutDown.md)|Désactive **Envoyer** et\/ou appel de **Recevoir** de socket.|  
|[CASyncSocket::Socket](../Topic/CASyncSocket::Socket.md)|Alloue un handle de socket.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAsyncSocket::OnAccept](../Topic/CAsyncSocket::OnAccept.md)|Avertit un socket écoutant qu'elle peut recevoir en attente des demandes de connexion en appelant **Accepter**.|  
|[CAsyncSocket::OnClose](../Topic/CAsyncSocket::OnClose.md)|Avertit un socket que le socket connecté à ce dernier est fermé.|  
|[CAsyncSocket::OnConnect](../Topic/CAsyncSocket::OnConnect.md)|Avertit un socket la connexion que la tentative de connexion est terminée, si avec succès ou dans l'erreur.|  
|[CAsyncSocket::OnOutOfBandData](../Topic/CAsyncSocket::OnOutOfBandData.md)|Avertit un socket de réception qu'il existe des données hors bande à lire du socket, généralement un message urgent.|  
|[CAsyncSocket::OnReceive](../Topic/CAsyncSocket::OnReceive.md)|Avertit un socket écoutant qu'il existe des données à récupérer en appelant **Recevoir**.|  
|[CAsyncSocket::OnSend](../Topic/CAsyncSocket::OnSend.md)|Avertit un socket qu'il peut envoyer des données en appelant **Envoyer**.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAsyncSocket::operator \=](../Topic/CAsyncSocket::operator%20=.md)|Assigne une valeur à un objet d' `CAsyncSocket` .|  
|[CAsyncSocket::operator SOCKET](../Topic/CAsyncSocket::operator%20SOCKET.md)|Utilisez cet opérateur pour récupérer le handle de **tête creuse** de l'objet d' `CAsyncSocket` .|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAsyncSocket::m\_hSocket](../Topic/CAsyncSocket::m_hSocket.md)|Indique le handle de **tête creuse** associé à cet objet d' `CAsyncSocket` .|  
  
## Notes  
 La classe `CAsyncSocket` encapsule l'API de fonctions Winsock, en fournissant une abstraction orientée objet pour les programmeurs qui souhaitent utiliser Windows Sockets avec MFC.  
  
 Cette classe est basé sur l'hypothèse que vous comprenez les communications réseau.  Vous êtes chargé de bloquer de gérer, de différences de marque d'ordre d'octet, et de conversions entre Unicode et les chaînes du jeu de caractères multioctets \(MBCS\).  Si vous souhaitez une interface plus pratique qui gère ces problèmes pour vous, consultez la classe [CSocket](../../mfc/reference/csocket-class.md).  
  
 Pour utiliser un objet d' `CAsyncSocket` , appelez son constructeur, puis appelez la fonction de création pour créer le handle sous\-jacent de socket \(type `SOCKET`\), sauf sur les sockets acceptés.  Pour un socket de serveur appelez la fonction membre d' [écoutez](../Topic/CAsyncSocket::Listen.md) , et un socket client appelez la fonction membre de [connectez](../Topic/CAsyncSocket::Connect.md) .  Le socket de serveur doit appeler la fonction d' [Acceptez](../Topic/CAsyncSocket::Accept.md) à accepter une demande de connexion.  Utilisez les fonctions restantes d' `CAsyncSocket` pour effectuer des communications entre les sockets.  Une fois l'opération terminée, détruisez l'objet d' `CAsyncSocket` s'il a été créé sur le tas ; le destructeur appelle automatiquement la fonction de [Fermez](../Topic/CAsyncSocket::Close.md) .  Le type de données d' `SOCKET` est décrite dans l'article [Windows Sockets : Arrière\-plan](../../mfc/windows-sockets-background.md).  
  
> [!NOTE]
>  À l'aide de sockets MFC dans les threads secondaires dans une application liée statiquement MFC, vous devez appeler `AfxSocketInit` dans chaque thread qui utilise des sockets pour initialiser les bibliothèques de socket.  Par défaut, `AfxSocketInit` est appelé uniquement dans le thread principal.  
  
 Pour plus d'informations, consultez [Windows Sockets : À l'aide de la classe CAsyncSocket](../../mfc/windows-sockets-using-class-casyncsocket.md) et les éléments connexes., ainsi que l' [API Windows Sockets 2](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CAsyncSocket`  
  
## Configuration requise  
 **en\-tête :** afxsock.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CSocket Class](../../mfc/reference/csocket-class.md)   
 [CSocketFile Class](../../mfc/reference/csocketfile-class.md)