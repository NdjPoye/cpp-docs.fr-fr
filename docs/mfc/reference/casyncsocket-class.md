---
title: CAsyncSocket (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAsyncSocket
- AFXSOCK/CAsyncSocket
- AFXSOCK/CAsyncSocket::CAsyncSocket
- AFXSOCK/CAsyncSocket::Accept
- AFXSOCK/CAsyncSocket::AsyncSelect
- AFXSOCK/CAsyncSocket::Attach
- AFXSOCK/CAsyncSocket::Bind
- AFXSOCK/CAsyncSocket::Close
- AFXSOCK/CAsyncSocket::Connect
- AFXSOCK/CAsyncSocket::Create
- AFXSOCK/CAsyncSocket::Detach
- AFXSOCK/CAsyncSocket::FromHandle
- AFXSOCK/CAsyncSocket::GetLastError
- AFXSOCK/CAsyncSocket::GetPeerName
- AFXSOCK/CAsyncSocket::GetPeerNameEx
- AFXSOCK/CAsyncSocket::GetSockName
- AFXSOCK/CAsyncSocket::GetSockNameEx
- AFXSOCK/CAsyncSocket::GetSockOpt
- AFXSOCK/CAsyncSocket::IOCtl
- AFXSOCK/CAsyncSocket::Listen
- AFXSOCK/CAsyncSocket::Receive
- AFXSOCK/CAsyncSocket::ReceiveFrom
- AFXSOCK/CAsyncSocket::ReceiveFromEx
- AFXSOCK/CAsyncSocket::Send
- AFXSOCK/CAsyncSocket::SendTo
- AFXSOCK/CAsyncSocket::SendToEx
- AFXSOCK/CAsyncSocket::SetSockOpt
- AFXSOCK/CAsyncSocket::ShutDown
- AFXSOCK/CASyncSocket::Socket
- AFXSOCK/CAsyncSocket::OnAccept
- AFXSOCK/CAsyncSocket::OnClose
- AFXSOCK/CAsyncSocket::OnConnect
- AFXSOCK/CAsyncSocket::OnOutOfBandData
- AFXSOCK/CAsyncSocket::OnReceive
- AFXSOCK/CAsyncSocket::OnSend
- AFXSOCK/CAsyncSocket::m_hSocket
dev_langs:
- C++
helpviewer_keywords:
- network communications
- asynchronous Windows Sockets
- CAsyncSocket class
- Windows Sockets [C++], asynchronous
- communications [C++], network
- sockets [C++], Windows
ms.assetid: cca4d5a1-aa0f-48bd-843e-ef0e2d7fc00b
caps.latest.revision: 23
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c7a175fc12146d98becc5d06f80e975df5b5a008
ms.lasthandoff: 02/24/2017

---
# <a name="casyncsocket-class"></a>CAsyncSocket (classe)
Représente un Socket Windows, un point de terminaison de communication réseau.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CAsyncSocket : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAsyncSocket::CAsyncSocket](#casyncsocket)|Construit un objet `CAsyncSocket`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CAsyncSocket::Accept](#accept)|Accepte une connexion sur le socket.|  
|[CAsyncSocket::AsyncSelect](#asyncselect)|Notification d’événement de demandes pour le socket.|  
|[CAsyncSocket::Attach](#attach)|Attache un handle de socket à un `CAsyncSocket` objet.|  
|[CAsyncSocket::Bind](#bind)|Associe une adresse locale du socket.|  
|[CAsyncSocket::Close](#close)|Ferme le socket.|  
|[CAsyncSocket::Connect](#connect)|Établit une connexion à un socket d’homologue.|  
|[CAsyncSocket::Create](#create)|Crée un socket.|  
|[CAsyncSocket::Detach](#detach)|Détache un handle de socket dans un `CAsyncSocket` objet.|  
|[CAsyncSocket::FromHandle](#fromhandle)|Retourne un pointeur vers un `CAsyncSocket` objet, un handle de socket.|  
|[CAsyncSocket::GetLastError](#getlasterror)|Obtient l’état d’erreur de la dernière opération qui a échoué.|  
|[CAsyncSocket::GetPeerName](#getpeername)|Obtient l’adresse de socket homologue auquel le socket est connecté.|  
|[CAsyncSocket::GetPeerNameEx](#getpeernameex)|Obtient l’adresse de socket homologue auquel le socket est connecté (gère les adresses IPv6).|  
|[Fonction membre CAsyncSocket::GetSockName](#getsockname)|Obtient le nom local d’un socket.|  
|[CAsyncSocket::GetSockNameEx](#getsocknameex)|Obtient le nom local d’un socket (gère les adresses IPv6).|  
|[CAsyncSocket::GetSockOpt](#getsockopt)|Récupère une option de socket.|  
|[CAsyncSocket::IOCtl](#ioctl)|Contrôle le mode du socket.|  
|[CAsyncSocket::Listen](#listen)|Établit un socket pour écouter les demandes de connexion entrantes.|  
|[CAsyncSocket::Receive](#receive)|Reçoit les données à partir du socket.|  
|[CAsyncSocket::ReceiveFrom](#receivefrom)|Reçoit un datagramme et stocke l’adresse source.|  
|[CAsyncSocket::ReceiveFromEx](#receivefromex)|Reçoit un datagramme et stocke l’adresse source (gère les adresses IPv6).|  
|[CAsyncSocket::Send](#send)|Envoie des données à un socket connecté.|  
|[CAsyncSocket::SendTo](#sendto)|Envoie des données vers une destination spécifique.|  
|[CAsyncSocket::SendToEx](#sendtoex)|Envoie des données vers une destination spécifique (gère les adresses IPv6).|  
|[CAsyncSocket::SetSockOpt](#setsockopt)|Définit une option de socket.|  
|[CAsyncSocket::ShutDown](#shutdown)|Désactive **envoyer** et/ou **réception** appelle sur le socket.|  
|[CASyncSocket::Socket](#socket)|Alloue un handle de socket.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CAsyncSocket::OnAccept](#onaccept)|Avertit un socket d’écoute qu’il peut accepter les demandes de connexion en attente en appelant **accepter**.|  
|[CAsyncSocket::OnClose](#onclose)|Avertit un socket connecté le socket est fermé.|  
|[CAsyncSocket::OnConnect](#onconnect)|Avertit un socket de connexion que la tentative de connexion est terminée, si avec succès ou erreur.|  
|[CAsyncSocket::OnOutOfBandData](#onoutofbanddata)|Avertit un socket de réception s’out-of-band des données à lire sur le socket, généralement un message urgent.|  
|[CAsyncSocket::OnReceive](#onreceive)|Avertit un socket d’écoute qu’il y a des données à être récupéré en appelant **réception**.|  
|[CAsyncSocket::OnSend](#onsend)|Avertit un socket qu’il peut envoyer des données en appelant **envoyer**.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAsyncSocket::operator =](#operator_eq)|Affecte une nouvelle valeur à un `CAsyncSocket` objet.|  
|[CAsyncSocket::operator SOCKET](#operator_socket)|Utilisez cet opérateur pour récupérer le **SOCKET** gérer de la `CAsyncSocket` objet.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAsyncSocket::m_hSocket](#m_hsocket)|Indique le **SOCKET** descripteur associé à ce `CAsyncSocket` objet.|  
  
## <a name="remarks"></a>Remarques  
 Classe `CAsyncSocket` encapsule l’API Windows Socket fonctions, en fournissant une abstraction orientée objet pour les programmeurs qui utilisent Windows Sockets en conjonction avec MFC.  
  
 Cette classe est basée sur l’hypothèse que vous comprenez les communications réseau. Vous êtes chargé de gérer le blocage, les différences d’ordre d’octet, et les conversions entre des caractères Unicode et définir des chaînes (MBCS). Si vous souhaitez une interface plus pratique qui gère ces problèmes pour vous, consultez la classe [CSocket](../../mfc/reference/csocket-class.md).  
  
 Pour utiliser un `CAsyncSocket` d’objet, l’appel à son constructeur, puis appelez le [créer](#create) fonction pour créer le handle de socket sous-jacent (type `SOCKET`), sauf sur les sockets acceptées. Pour un appel de socket serveur le [écouter](#listen) fonction membre et pour un appel de socket client le [connexion](#connect) fonction membre. Le socket de serveur doit appeler le [accepter](#accept) fonction lors de la réception d’une demande de connexion. Utilisez les autres `CAsyncSocket` fonctions pour effectuer des communications entre les sockets. À l’achèvement, détruire le `CAsyncSocket` l’objet s’il a été créé sur le tas ; le destructeur appelle automatiquement la [fermer](#close) (fonction). Le `SOCKET` type de données est décrite dans l’article [Windows Sockets : arrière-plan](../../mfc/windows-sockets-background.md).  
  
> [!NOTE]
>  Lors de l’utilisation de sockets MFC dans des threads secondaires dans une application MFC liée statiquement, vous devez appeler `AfxSocketInit` dans chaque thread qui utilise des sockets pour initialiser les bibliothèques de socket. Par défaut, `AfxSocketInit` est appelée uniquement dans le thread principal.  
  
 Pour plus d’informations, consultez [Windows Sockets : à l’aide de classe CAsyncSocket](../../mfc/windows-sockets-using-class-casyncsocket.md) et articles liés., ainsi que [API Windows Sockets 2](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CAsyncSocket`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxsock.h  
  
##  <a name="accept"></a>CAsyncSocket::Accept  
 Appelez cette fonction membre pour accepter une connexion sur un socket.  
  
```  
virtual BOOL Accept(
    CAsyncSocket& rConnectedSocket,  
    SOCKADDR* lpSockAddr = NULL,  
    int* lpSockAddrLen = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `rConnectedSocket`  
 Référence identifiant un nouveau socket est disponible pour la connexion.  
  
 `lpSockAddr`  
 Un pointeur vers un [SOCKADDR](../../mfc/reference/sockaddr-structure.md) structure qui reçoit l’adresse de la connexion de socket, tel qu’identifié sur le réseau. Le format exact de la `lpSockAddr` argument est déterminé par la famille d’adresses établie lorsque le socket a été créé. Si `lpSockAddr` et/ou `lpSockAddrLen` sont égaux à **NULL**, aucune information sur l’adresse distante du socket accepté est retourné.  
  
 `lpSockAddrLen`  
 Un pointeur vers la longueur de l’adresse dans `lpSockAddr` en octets. Le `lpSockAddrLen` est un paramètre de valeur de résultat : elle doit contenir initialement la quantité d’espace vers lequel pointé `lpSockAddr`; il contient la longueur réelle (en octets) de l’adresse retournée au retour.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; Sinon, 0 et un code d’erreur spécifique peuvent être récupéré en appelant [GetLastError](#getlasterror). Les erreurs suivantes s’appliquent à cette fonction membre :  
  
- **WSANOTINITIALISED** un bon [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) doit se produire avant d’utiliser cette API.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
- **WSAEFAULT** le `lpSockAddrLen` argument est trop faible (inférieure à la taille d’un [SOCKADDR](../../mfc/reference/sockaddr-structure.md) structure).  
  
- **Winsock** un appel de blocage Windows Sockets est en cours.  
  
- **WSAEINVAL** `Listen` n’a pas appelé avant l’accepter.  
  
- **WSAEMFILE** la file d’attente est vide lors de l’entrée pour accepter et aucun descripteur ne sont disponibles.  
  
- `WSAENOBUFS`Aucun espace tampon n’est disponible.  
  
- **WSAENOTSOCK** le descripteur n’est pas un socket.  
  
- **WSAEOPNOTSUPP** le socket référencé n’est pas un type qui prend en charge le service orienté connexion.  
  
- **WSAEWOULDBLOCK** le socket est marqué comme non bloquant et aucune connexion n’est présente pour être acceptés.  
  
### <a name="remarks"></a>Remarques  
 Cette routine extrait la première connexion de la file d’attente des connexions en attente, crée un nouveau socket avec les mêmes propriétés que ce socket et l’attache à `rConnectedSocket`. Si aucune des connexions en attente ne sont présentes dans la file d’attente, **accepter** retourne zéro et `GetLastError` renvoie une erreur. Le socket accepté ( *rConnectedSocket)* ne peut pas être utilisé pour accepter plus de connexions. Le socket d’origine reste ouverte et à l’écoute.  
  
 L’argument `lpSockAddr` est un paramètre de résultat qui est rempli avec l’adresse de connexion de socket, connues de la couche des communications. **Accepter** utilisé avec les types de sockets orientés connexion tels que **SOCK_STREAM**.  
  
##  <a name="asyncselect"></a>CAsyncSocket::AsyncSelect  
 Appelez cette fonction membre pour demander une notification d’événement pour un socket.  
  
```  
BOOL AsyncSelect(long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```  
  
### <a name="parameters"></a>Paramètres  
 `lEvent`  
 Masque de bits qui spécifie une combinaison d’événements réseau qui intéressent l’application.  
  
- **FD_READ** pour recevoir la notification de préparation pour la lecture.  
  
- **FD_WRITE** pour recevoir des notifications lorsque les données sont disponibles pour la lecture.  
  
- **FD_OOB** pour recevoir la notification de l’arrivée des données hors bande.  
  
- **FD_ACCEPT** pour recevoir la notification de connexions entrantes.  
  
- **FD_CONNECT** pour recevoir la notification des résultats de la connexion.  
  
- **FD_CLOSE** souhaitez recevoir une notification lorsqu’un socket a été fermé par un homologue.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; Sinon, 0 et un code d’erreur spécifique peuvent être récupéré en appelant [GetLastError](#getlasterror). Les erreurs suivantes s’appliquent à cette fonction membre :  
  
- **WSANOTINITIALISED** un bon [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) doit se produire avant d’utiliser cette API.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
- **WSAEINVAL** indique qu’un des paramètres spécifiés n’est pas valide.  
  
- **Winsock** une opération de blocage Windows Sockets est en cours.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est utilisée pour spécifier les fonctions de notification de rappel MFC seront appelées pour le socket. `AsyncSelect`définit automatiquement ce socket en mode non bloquant. Pour plus d’informations, consultez l’article [Windows Sockets : Notifications de sockets](../../mfc/windows-sockets-socket-notifications.md).  
  
##  <a name="attach"></a>CAsyncSocket::Attach  
 Appelez cette fonction membre pour attacher le `hSocket` handle vers un `CAsyncSocket` objet.  
  
```  
BOOL Attach(
    SOCKET hSocket, long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```  
  
### <a name="parameters"></a>Paramètres  
 `hSocket`  
 Contient un handle à un socket.  
  
 `lEvent`  
 Masque de bits qui spécifie une combinaison d’événements réseau qui intéressent l’application.  
  
- **FD_READ** pour recevoir la notification de préparation pour la lecture.  
  
- **FD_WRITE** pour recevoir des notifications lorsque les données sont disponibles pour la lecture.  
  
- **FD_OOB** pour recevoir la notification de l’arrivée des données hors bande.  
  
- **FD_ACCEPT** pour recevoir la notification de connexions entrantes.  
  
- **FD_CONNECT** pour recevoir la notification des résultats de la connexion.  
  
- **FD_CLOSE** souhaitez recevoir une notification lorsqu’un socket a été fermé par un homologue.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro si la fonction aboutit.  
  
### <a name="remarks"></a>Remarques  
 Le **SOCKET** handle est stocké dans l’objet [m_hSocket](#m_hsocket) membre de données.  
  
##  <a name="bind"></a>CAsyncSocket::Bind  
 Appelez cette fonction membre pour associer une adresse locale du socket.  
  
```  
BOOL Bind(
    UINT nSocketPort,  
    LPCTSTR lpszSocketAddress = NULL);

 
BOOL Bind (
    const SOCKADDR* lpSockAddr,  
    int nSockAddrLen);
```  
  
### <a name="parameters"></a>Paramètres  
 `nSocketPort`  
 Le port identifiant l’application de socket.  
  
 `lpszSocketAddress`  
 L’adresse réseau, un nombre en pointillés comme « 128.56.22.8 ». En passant le **NULL** de chaîne de ce paramètre indique le **CAsyncSocket** instance doit écouter les activités des clients sur toutes les interfaces réseau.  
  
 `lpSockAddr`  
 Un pointeur vers un [SOCKADDR](../../mfc/reference/sockaddr-structure.md) structure qui contient l’adresse à attribuer à ce socket.  
  
 `nSockAddrLen`  
 La longueur de l’adresse dans `lpSockAddr` en octets.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; Sinon, 0 et un code d’erreur spécifique peuvent être récupéré en appelant [GetLastError](#getlasterror). Les erreurs suivantes s’appliquent à cette fonction membre :  
  
- **WSANOTINITIALISED** un bon [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) doit se produire avant d’utiliser cette API.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
- **WSAEADDRINUSE** l’adresse spécifiée est déjà en cours d’utilisation. (Voir la **SO_REUSEADDR** option de socket [SetSockOpt](#setsockopt).)  
  
- **WSAEFAULT** le `nSockAddrLen` argument est trop faible (inférieure à la taille d’un [SOCKADDR](../../mfc/reference/sockaddr-structure.md) structure).  
  
- **Winsock** un appel de blocage Windows Sockets est en cours.  
  
- **WSAEAFNOSUPPORT** la famille d’adresses spécifiée n’est pas pris en charge par ce port.  
  
- **WSAEINVAL** le socket est déjà lié à une adresse.  
  
- `WSAENOBUFS`Pas assez tampons disponibles, trop de connexions.  
  
- **WSAENOTSOCK** le descripteur n’est pas un socket.  
  
### <a name="remarks"></a>Notes  
 Cette routine est utilisée sur un socket de flux de données, ou un datagramme non connecté avant ultérieures **connecter** ou `Listen` les appels. Avant d’accepter les demandes de connexion, un socket de serveur écoute doit sélectionner un numéro de port et faire connaître en Windows Sockets en appelant **lier**. **Lier** établit l’association locale (numéro de port/adresse d’hôte) du socket en attribuant un nom local à un socket sans nom.  
  
##  <a name="casyncsocket"></a>CAsyncSocket::CAsyncSocket  
 Construit un objet socket vide.  
  
```  
CAsyncSocket();
```  
  
### <a name="remarks"></a>Remarques  
 Après la construction de l’objet, vous devez appeler sa **créer** fonction membre pour créer le **SOCKET** de structure de données et lier son adresse. (Sur le côté serveur d’une communication de Windows Sockets, lorsque le socket d’écoute crée un socket à utiliser dans le **accepter** appel, vous n’appelez pas **créer** pour ce socket.)  
  
##  <a name="close"></a>CAsyncSocket::Close  
 Ferme le socket.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Remarques  
 Cette fonction libère le descripteur de socket afin que les autres références échoue avec l’erreur **WSAENOTSOCK**. S’il s’agit de la dernière référence du socket sous-jacent, les informations d’affectation de noms associées et les données en file d’attente sont ignorées. Appels de destructeur de l’objet socket **fermer** pour vous.  
  
 Pour `CAsyncSocket`, mais pas pour les `CSocket`, la sémantique de **fermer** sont affectées par les options de socket **SO_LINGER** et **SO_DONTLINGER**. Pour plus d’informations, consultez la fonction membre `GetSockOpt`.  
  
##  <a name="connect"></a>CAsyncSocket::Connect  
 Appelez cette fonction membre pour établir une connexion à un flux non connecté ou un socket datagramme.  
  
```  
BOOL Connect(
    LPCTSTR lpszHostAddress,  
    UINT nHostPort);

 
BOOL Connect(
    const SOCKADDR* lpSockAddr,  
    int nSockAddrLen);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszHostAddress`  
 L’adresse réseau du socket à laquelle cet objet est connecté : un nom d’ordinateur tel que « FTP.Microsoft.com », ou un nombre en pointillés comme « 128.56.22.8 ».  
  
 `nHostPort`  
 Le port identifiant l’application de socket.  
  
 `lpSockAddr`  
 Un pointeur vers un [SOCKADDR](../../mfc/reference/sockaddr-structure.md) structure qui contient l’adresse du socket connecté.  
  
 `nSockAddrLen`  
 La longueur de l’adresse dans `lpSockAddr` en octets.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; Sinon, 0 et un code d’erreur spécifique peuvent être récupéré en appelant [GetLastError](#getlasterror). Si cela indique le code d’erreur **WSAEWOULDBLOCK**et que votre application utilise les rappels substituables, votre application reçoit une `OnConnect` message affiché lorsque l’opération de connexion est terminée. Les erreurs suivantes s’appliquent à cette fonction membre :  
  
- **WSANOTINITIALISED** un bon [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) doit se produire avant d’utiliser cette API.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
- **WSAEADDRINUSE** l’adresse spécifiée est déjà en cours d’utilisation.  
  
- **Winsock** un appel de blocage Windows Sockets est en cours.  
  
- **WSAEADDRNOTAVAIL** l’adresse spécifiée n’est pas disponible à partir de l’ordinateur local.  
  
- **WSAEAFNOSUPPORT** adresses dans la famille spécifiée ne peut pas être utilisées avec ce socket.  
  
- **WSAECONNREFUSED** tentative de connexion a été rejetée.  
  
- **WSAEDESTADDRREQ** une adresse de destination est requise.  
  
- **WSAEFAULT** le `nSockAddrLen` argument est incorrect.  
  
- **WSAEINVAL** adresse d’hôte non valide.  
  
- **WSAEISCONN** le socket est déjà connecté.  
  
- **WSAEMFILE** plus aucun descripteur de fichier est disponible.  
  
- **WSAENETUNREACH** le réseau ne peut pas être atteint à partir de cet hôte en ce moment.  
  
- `WSAENOBUFS`Aucun espace tampon n’est disponible. Le socket n’est pas accessible.  
  
- **WSAENOTSOCK** le descripteur n’est pas un socket.  
  
- **WSAETIMEDOUT** tentative de connexion dépassé sans avoir à établir une connexion.  
  
- **WSAEWOULDBLOCK** le socket est marqué comme non bloquant et la connexion ne peut pas être effectuée immédiatement.  
  
### <a name="remarks"></a>Remarques  
 Si le socket n’est pas lié, des valeurs uniques sont affectés à l’association locale par le système et le socket est marqué comme étant liés. Notez que si le champ adresse de la structure de nom est zéros, **connecter** retourne la valeur zéro. Pour obtenir des informations de l’erreur est étendues, appelez le `GetLastError` fonction membre.  
  
 Pour les sockets flux (type **SOCK_STREAM**), une connexion active est lancée à l’hôte externe. Lors de l’appel de socket se termine avec succès, le socket est prêt à envoyer/recevoir des données.  
  
 Pour un socket datagramme (type **SOCK_DGRAM**), une destination par défaut est définie, qui sera utilisée sur ultérieures **envoyer** et **réception** appels.  
  
##  <a name="create"></a>CAsyncSocket::Create  
 Appelez le **créer** fonction membre après avoir construit un objet socket pour créer le socket de Windows et l’attacher.  
  
```  
BOOL Create(
    UINT nSocketPort = 0,  
    int nSocketType = SOCK_STREAM,  
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,  
    LPCTSTR lpszSocketAddress = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `nSocketPort`  
 Un port connu pour être utilisé avec les sockets, ou 0 si vous souhaitez que Windows Sockets sélectionner un port.  
  
 `nSocketType`  
 **SOCK_STREAM** ou **SOCK_DGRAM**.  
  
 `lEvent`  
 Masque de bits qui spécifie une combinaison d’événements réseau qui intéressent l’application.  
  
- **FD_READ** pour recevoir la notification de préparation pour la lecture.  
  
- **FD_WRITE** pour recevoir la notification de préparation pour l’écriture.  
  
- **FD_OOB** pour recevoir la notification de l’arrivée des données hors bande.  
  
- **FD_ACCEPT** pour recevoir la notification de connexions entrantes.  
  
- **FD_CONNECT** à recevoir des notifications de connexion terminée.  
  
- **FD_CLOSE** pour recevoir la notification de la fermeture du socket.  
  
 *lpszSockAddress*  
 Pointeur vers une chaîne contenant l’adresse réseau du socket connecté, un nombre en pointillés comme « 128.56.22.8 ». En passant le **NULL** de chaîne de ce paramètre indique le **CAsyncSocket** instance doit écouter les activités des clients sur toutes les interfaces réseau.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; Sinon, 0 et un code d’erreur spécifique peuvent être récupéré en appelant [GetLastError](#getlasterror). Les erreurs suivantes s’appliquent à cette fonction membre :  
  
- **WSANOTINITIALISED** un bon [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) doit se produire avant d’utiliser cette API.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
- **WSAEAFNOSUPPORT** la famille d’adresses spécifiée n’est pas pris en charge.  
  
- **Winsock** une opération de blocage Windows Sockets est en cours.  
  
- **WSAEMFILE** plus aucun descripteur de fichier est disponible.  
  
- `WSAENOBUFS`Aucun espace tampon n’est disponible. Impossible de créer le socket.  
  
- **WSAEPROTONOSUPPORT** le port spécifié n’est pas pris en charge.  
  
- **WSAEPROTOTYPE** le port spécifié est de type incorrect pour le socket.  
  
- **WSAESOCKTNOSUPPORT** le type de socket spécifié n’est pas pris en charge dans cette famille d’adresses.  
  
### <a name="remarks"></a>Remarques  
 **Créer** appelle [Socket](#socket) en cas de réussite, il appelle [lier](#bind) pour lier le socket à l’adresse spécifiée. Les types de support suivants sont pris en charge :  
  
- **SOCK_STREAM** fournit le séquencement, flux d’octets fiables, en mode duplex intégral, basée sur une connexion. Utilise le protocole TCP (Transmission Control) pour la famille d’adresses Internet.  
  
- **SOCK_DGRAM** prend en charge des datagrammes, qui sont sans connexion, non fiables des paquets de longueur maximale fixe (généralement réduite). Utilise le protocole UDP (User Datagram) pour la famille d’adresses Internet.  
  
    > [!NOTE]
    >  Le **accepter** fonction membre se réfère à un vide `CSocket` objet comme paramètre. Vous devez créer cet objet avant d’appeler **accepter**. N’oubliez pas que si cet objet socket est hors de portée, la connexion se ferme. N’appelez pas **créer** pour ce nouvel objet socket.  
  
> [!IMPORTANT]
> **Créer** est **pas** thread-safe.  Si vous appelez cela dans un environnement multithread où il peut être appelé simultanément par plusieurs threads, veillez à protéger chaque appel avec un mutex ou autre verrou de synchronisation.  
  
 Pour plus d’informations sur les sockets de flux de données et de datagramme, consultez les articles [Windows Sockets : arrière-plan](../../mfc/windows-sockets-background.md) et [Windows Sockets : Ports et adresses de Socket](../../mfc/windows-sockets-ports-and-socket-addresses.md) et [API Windows Sockets 2](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
##  <a name="detach"></a>CAsyncSocket::Detach  
 Appelez cette fonction membre pour détacher le **SOCKET** gérer dans le `m_hSocket` membre de données à partir de la `CAsyncSocket` et définissez `m_hSocket` à **NULL**.  
  
```  
SOCKET Detach();
```  
  
##  <a name="fromhandle"></a>CAsyncSocket::FromHandle  
 Retourne un pointeur vers un `CAsyncSocket` objet.  
  
```  
static CAsyncSocket* PASCAL FromHandle(SOCKET hSocket);
```  
  
### <a name="parameters"></a>Paramètres  
 `hSocket`  
 Contient un handle à un socket.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un `CAsyncSocket` objet, ou **NULL** s’il existe aucune `CAsyncSocket` objet attaché à `hSocket`.  
  
### <a name="remarks"></a>Notes  
 En fonction d’un **SOCKET** gérer, si un `CAsyncSocket` objet n’est pas attaché au handle, la fonction membre retourne **NULL**.  
  
##  <a name="getlasterror"></a>CAsyncSocket::GetLastError  
 Appelez cette fonction membre pour obtenir l’état d’erreur de la dernière opération qui a échoué.  
  
```  
static int PASCAL GetLastError();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur de retour indique le code d’erreur de la dernière routine API Windows Sockets effectuée par ce thread.  
  
### <a name="remarks"></a>Remarques  
 Lorsqu’une fonction membre particulière indique qu’une erreur s’est produite, `GetLastError` doit être appelée pour récupérer le code d’erreur approprié. Consultez les descriptions de la fonction membre individuel pour obtenir la liste des codes d’erreur applicables.  
  
 Pour plus d’informations sur les codes d’erreur, consultez la page [API Windows Sockets 2](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
##  <a name="getpeername"></a>CAsyncSocket::GetPeerName  
 Appelez cette fonction membre pour obtenir l’adresse de socket homologue auquel le socket est connecté.  
  
```  
BOOL GetPeerName(
    CString& rPeerAddress,  
    UINT& rPeerPort);

 
BOOL GetPeerName(
    SOCKADDR* lpSockAddr,  
    int* lpSockAddrLen);
```  
  
### <a name="parameters"></a>Paramètres  
 `rPeerAddress`  
 Référence à un `CString` objet qui reçoit une adresse IP numérique en pointillé.  
  
 `rPeerPort`  
 Référence à un **UINT** qui stocke un port.  
  
 `lpSockAddr`  
 Un pointeur vers le [SOCKADDR](../../mfc/reference/sockaddr-structure.md) structure qui reçoit le nom du socket homologue.  
  
 `lpSockAddrLen`  
 Un pointeur vers la longueur de l’adresse dans `lpSockAddr` en octets. Au retour, le `lpSockAddrLen` argument contient la taille réelle de `lpSockAddr` retournée en octets.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; Sinon, 0 et un code d’erreur spécifique peuvent être récupéré en appelant [GetLastError](#getlasterror). Les erreurs suivantes s’appliquent à cette fonction membre :  
  
- **WSANOTINITIALISED** un bon [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) doit se produire avant d’utiliser cette API.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
- **WSAEFAULT** le `lpSockAddrLen` argument n’est pas assez grand.  
  
- **Winsock** un appel de blocage Windows Sockets est en cours.  
  
- **WSAENOTCONN** le socket n’est pas connecté.  
  
- **WSAENOTSOCK** le descripteur n’est pas un socket.  
  
### <a name="remarks"></a>Remarques  
 Pour gérer les adresses IPv6, utilisez [CAsyncSocket::GetPeerNameEx](#getpeernameex).  
  
##  <a name="getpeernameex"></a>CAsyncSocket::GetPeerNameEx  
 Appelez cette fonction membre pour obtenir l’adresse de socket homologue auquel le socket est connecté (gère les adresses IPv6).  
  
```  
BOOL GetPeerNameEx(
    CString& rPeerAddress,  
    UINT& rPeerPort);
```  
  
### <a name="parameters"></a>Paramètres  
 `rPeerAddress`  
 Référence à un `CString` objet qui reçoit une adresse IP numérique en pointillé.  
  
 `rPeerPort`  
 Référence à un **UINT** qui stocke un port.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; Sinon, 0 et un code d’erreur spécifique peuvent être récupéré en appelant [GetLastError](#getlasterror). Les erreurs suivantes s’appliquent à cette fonction membre :  
  
- **WSANOTINITIALISED** un bon [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) doit se produire avant d’utiliser cette API.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
- **WSAEFAULT** le `lpSockAddrLen` argument n’est pas assez grand.  
  
- **Winsock** un appel de blocage Windows Sockets est en cours.  
  
- **WSAENOTCONN** le socket n’est pas connecté.  
  
- **WSAENOTSOCK** le descripteur n’est pas un socket.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est identique à [CAsyncSocket::GetPeerName](#getpeername) , sauf qu’il gère IPv6 résout ainsi que les anciens protocoles.  
  
##  <a name="getsockname"></a>Fonction membre CAsyncSocket::GetSockName  
 Appelez cette fonction membre pour récupérer le nom local d’un socket.  
  
```  
BOOL GetSockName(
    CString& rSocketAddress,  
    UINT& rSocketPort);

 
BOOL GetSockName(
    SOCKADDR* lpSockAddr,  
    int* lpSockAddrLen);
```  
  
### <a name="parameters"></a>Paramètres  
 `rSocketAddress`  
 Référence à un `CString` objet qui reçoit une adresse IP numérique en pointillé.  
  
 `rSocketPort`  
 Référence à un **UINT** qui stocke un port.  
  
 `lpSockAddr`  
 Un pointeur vers un [SOCKADDR](../../mfc/reference/sockaddr-structure.md) structure qui reçoit l’adresse de socket.  
  
 `lpSockAddrLen`  
 Un pointeur vers la longueur de l’adresse dans `lpSockAddr` en octets.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; Sinon, 0 et un code d’erreur spécifique peuvent être récupéré en appelant [GetLastError](#getlasterror). Les erreurs suivantes s’appliquent à cette fonction membre :  
  
- **WSANOTINITIALISED** un bon [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) doit se produire avant d’utiliser cette API.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
- **WSAEFAULT** le `lpSockAddrLen` argument n’est pas assez grand.  
  
- **Winsock** une opération de blocage Windows Sockets est en cours.  
  
- **WSAENOTSOCK** le descripteur n’est pas un socket.  
  
- **WSAEINVAL** le socket n’a pas été lié à une adresse avec **lier**.  
  
### <a name="remarks"></a>Notes  
 Cet appel est particulièrement utile lorsque un **connecter** appel a été effectué sans effectuer une **lier** tout d’abord, cet appel fournit le seul moyen par lequel vous pouvez déterminer l’association locale qui a été définie par le système.  
  
 Pour gérer les adresses IPv6, utilisez [CAsyncSocket::GetSockNameEx](#getsocknameex)  
  
##  <a name="getsocknameex"></a>CAsyncSocket::GetSockNameEx  
 Appelez cette fonction membre pour récupérer le nom local d’un socket (gère les adresses IPv6).  
  
```  
BOOL GetSockNameEx(
    CString& rSocketAddress,  
    UINT& rSocketPort);
```  
  
### <a name="parameters"></a>Paramètres  
 `rSocketAddress`  
 Référence à un `CString` objet qui reçoit une adresse IP numérique en pointillé.  
  
 `rSocketPort`  
 Référence à un **UINT** qui stocke un port.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; Sinon, 0 et un code d’erreur spécifique peuvent être récupéré en appelant [GetLastError](#getlasterror). Les erreurs suivantes s’appliquent à cette fonction membre :  
  
- **WSANOTINITIALISED** un bon [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) doit se produire avant d’utiliser cette API.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
- **WSAEFAULT** le `lpSockAddrLen` argument n’est pas assez grand.  
  
- **Winsock** une opération de blocage Windows Sockets est en cours.  
  
- **WSAENOTSOCK** le descripteur n’est pas un socket.  
  
- **WSAEINVAL** le socket n’a pas été lié à une adresse avec **lier**.  
  
### <a name="remarks"></a>Remarques  
 Cet appel est identique à [fonction membre CAsyncSocket::GetSockName](#getsockname) , sauf qu’il gère IPv6 résout ainsi que les anciens protocoles.  
  
 Cet appel est particulièrement utile lorsque un **connecter** appel a été effectué sans effectuer une **lier** tout d’abord, cet appel fournit le seul moyen par lequel vous pouvez déterminer l’association locale qui a été définie par le système.  
  
##  <a name="getsockopt"></a>CAsyncSocket::GetSockOpt  
 Appelez cette fonction membre pour récupérer une option de socket.  
  
```  
BOOL GetSockOpt(
    int nOptionName,  
    void* lpOptionValue,  
    int* lpOptionLen,  
    int nLevel = SOL_SOCKET);
```  
  
### <a name="parameters"></a>Paramètres  
 `nOptionName`  
 L’option de socket dont la valeur doit être récupéré.  
  
 `lpOptionValue`  
 Pointeur vers la mémoire tampon dans laquelle la valeur de l’option demandée doit être retournée. La valeur associée à l’option sélectionnée est retournée dans la mémoire tampon `lpOptionValue`. L’entier indiqué par `lpOptionLen` doit contenir l’origine de la taille de cette mémoire tampon en octets ; et retour, elle est définie à la taille de la valeur retournée. Pour **SO_LINGER**, il s’agit de la taille d’un `LINGER` structure ; pour toutes les autres options, il sera la taille d’un **BOOL** ou un `int`, en fonction de l’option. Consultez la liste des options et leur taille dans la section Notes.  
  
 `lpOptionLen`  
 Un pointeur vers la taille de la `lpOptionValue` mémoire tampon en octets.  
  
 `nLevel`  
 Le niveau auquel elle est définie ; les niveaux de prise en charge uniquement sont **SOL_SOCKET** et **IPPROTO_TCP**.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; Sinon, 0 et un code d’erreur spécifique peuvent être récupéré en appelant [GetLastError](#getlasterror). Si une option n’a jamais été définie avec `SetSockOpt`, puis `GetSockOpt` retourne la valeur par défaut pour l’option. Les erreurs suivantes s’appliquent à cette fonction membre :  
  
- **WSANOTINITIALISED** un bon [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) doit se produire avant d’utiliser cette API.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
- **WSAEFAULT** le `lpOptionLen` argument n’est pas valide.  
  
- **Winsock** une opération de blocage Windows Sockets est en cours.  
  
- **WSAENOPROTOOPT** l’option est inconnu ou non pris en charge. En particulier, **SO_BROADCAST** n’est pas pris en charge sur les sockets de type **SOCK_STREAM**, tandis que **SO_ACCEPTCONN**, **SO_DONTLINGER**, **SO_KEEPALIVE**, **SO_LINGER**, et **SO_OOBINLINE** ne sont pas pris en charge sur les sockets de type **SOCK_DGRAM**.  
  
- **WSAENOTSOCK** le descripteur n’est pas un socket.  
  
### <a name="remarks"></a>Remarques  
 `GetSockOpt`Récupère la valeur actuelle d’une option de socket associée à un socket de tout type, dans un état et stocke le résultat dans `lpOptionValue`. Les options affectent les opérations de socket, telles que le routage de paquets, out-of-band transfert de données et ainsi de suite.  
  
 Les options suivantes sont prises en charge pour `GetSockOpt`. Le Type identifie le type de données adressées par `lpOptionValue`. Le **TCP_NODELAY** option utilise le niveau de **IPPROTO_TCP**; toutes les autres options utilisent niveau **SOL_SOCKET**.  
  
|Valeur|Type|Signification|  
|-----------|----------|-------------|  
|**SO_ACCEPTCONN**|**BOOL**|Socket est à l’écoute.|  
|**SO_BROADCAST**|**BOOL**|Socket est configuré pour la transmission des messages de diffusion.|  
|**SO_DEBUG**|**BOOL**|Le débogage est activé.|  
|**SO_DONTLINGER**|**BOOL**|Si la valeur est true, le **SO_LINGER** option est désactivée.|  
|**SO_DONTROUTE**|**BOOL**|Le routage est désactivé.|  
|**SO_ERROR**|`int`|Récupérer l’état d’erreur et l’effacer.|  
|**SO_KEEPALIVE**|**BOOL**|Des connexions persistantes sont envoyés.|  
|**SO_LINGER**|**structure de maintien**|Renvoie les options de persistance en cours.|  
|**SO_OOBINLINE**|**BOOL**|Les données hors bande sont reçues dans le flux de données normal.|  
|**SO_RCVBUF**|`int`|Taille de mémoire tampon pour les reçoit.|  
|**SO_REUSEADDR**|**BOOL**|Le socket peut être lié à une adresse qui est déjà en cours d’utilisation.|  
|**SO_SNDBUF**|`int`|Taille de mémoire tampon pour envoie.|  
|**SO_TYPE**|`int`|Le type de socket (par exemple, **SOCK_STREAM**).|  
|**TCP_NODELAY**|**BOOL**|Désactive l'algorithme Nagle pour la fusion des envois.|  
  
 Options de Distribution BSD (Berkeley Software) non pris en charge pour `GetSockOpt` sont :  
  
|Valeur|Type|Signification|  
|-----------|----------|-------------|  
|**SO_RCVLOWAT**|`int`|Limite inférieure de la réception.|  
|**SO_RCVTIMEO**|`int`|Délai de réception.|  
|**SO_SNDLOWAT**|`int`|Envoyer le seuil inférieur.|  
|**SO_SNDTIMEO**|`int`|Délai d’attente d’envoi.|  
|**IP_OPTIONS**||Obtenir des options dans l’en-tête IP.|  
|**TCP_MAXSEG**|`int`|Obtenir la taille des segments TCP.|  
  
 Appel de `GetSockOpt` entraîne une option non prise en charge dans le code d’erreur **WSAENOPROTOOPT** retournés à partir de `GetLastError`.  
  
##  <a name="ioctl"></a>CAsyncSocket::IOCtl  
 Appelez cette fonction membre pour contrôler le mode d’un socket.  
  
```  
BOOL IOCtl(
    long lCommand,  
    DWORD* lpArgument);
```  
  
### <a name="parameters"></a>Paramètres  
 `lCommand`  
 La commande à exécuter sur le socket.  
  
 `lpArgument`  
 Un pointeur vers un paramètre pour `lCommand`.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; Sinon, 0 et un code d’erreur spécifique peuvent être récupéré en appelant [GetLastError](#getlasterror). Les erreurs suivantes s’appliquent à cette fonction membre :  
  
- **WSANOTINITIALISED** un bon [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) doit se produire avant d’utiliser cette API.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
- **WSAEINVAL** `lCommand` n’est pas une commande valide, ou `lpArgument` n’est pas un paramètre acceptable pour `lCommand`, ou la commande n’est pas applicable au type de socket fourni.  
  
- **Winsock** une opération de blocage Windows Sockets est en cours.  
  
- **WSAENOTSOCK** le descripteur n’est pas un socket.  
  
### <a name="remarks"></a>Remarques  
 Cette routine est utilisable sur un socket dans un état. Il est utilisé pour obtenir ou récupérer les paramètres d’opération associées au socket, indépendamment du sous-système de protocole et les communications. Les commandes suivantes sont prises en charge :  
  
- **FIONBIO** activer ou désactiver le mode non bloquant sur le socket. Le `lpArgument` paramètre pointe vers une `DWORD`, qui est différent de zéro si le mode non bloquant doit être activé et zéro si elle est désactivée. Si `AsyncSelect` a été émise sur un socket puis toute tentative d’utilisation **IOCtl** pour définir le socket en mode blocage échoue avec **WSAEINVAL**. Pour définir le socket en mode blocage et empêcher le **WSAEINVAL** erreur, une application doit tout d’abord désactiver la `AsyncSelect` en appelant `AsyncSelect` avec la `lEvent` paramètre égal à 0, puis appelez **IOCtl**.  
  
- **FIONREAD** déterminer le nombre maximal d’octets pouvant être lus avec un **réception** appeler à partir de ce socket. Le `lpArgument` paramètre pointe vers une `DWORD` dans lequel **IOCtl** stocke le résultat. Si le socket est de type **SOCK_STREAM**, **FIONREAD** renvoie le montant total des données qui peuvent être lues dans un seul **réception**; cela est normalement le même que la quantité totale de données en file d’attente sur le socket. Si le socket est de type **SOCK_DGRAM**, **FIONREAD** retourne la taille du premier datagramme en file d’attente sur le socket.  
  
- **SIOCATMARK** déterminer si toutes les données hors bande a été lu. Cela s’applique uniquement à un socket de type **SOCK_STREAM** qui a été configuré pour la réception en ligne des données hors bande ( **SO_OOBINLINE**). Si aucune donnée hors-bande n’est en attente pour la lecture, l’opération retourne zéro. Sinon elle retourne 0 et la prochaine **réception** ou `ReceiveFrom` effectuées sur le socket récupérera certaines ou toutes les données précédant la « marque », l’application doit utiliser le **SIOCATMARK** opération afin de déterminer si les données restent. Si la donnée tout normale précédant la « urgent » (out-of-band), elle sera reçue dans l’ordre. (Notez qu’un **réception** ou `ReceiveFrom` sera ne mélangez jamais out-of-band et normales des données dans le même appel.) Le `lpArgument` paramètre pointe vers une `DWORD` dans lequel **IOCtl** stocke le résultat.  
  
 Cette fonction est un sous-ensemble de **ioctl()** servent de sockets Berkeley. En particulier, il n’existe aucune commande qui est équivalent à **FIOASYNC**, tandis que **SIOCATMARK** est la commande uniquement de niveau socket qui est pris en charge.  
  
##  <a name="listen"></a>CAsyncSocket::Listen  
 Appelez cette fonction membre pour écouter les demandes de connexion entrantes.  
  
```  
BOOL Listen(int nConnectionBacklog = 5);
```  
  
### <a name="parameters"></a>Paramètres  
 *nConnectionBacklog*  
 La longueur maximale que peut atteindre la file d’attente des connexions en attente. La plage valide est de 1 à 5.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; Sinon, 0 et un code d’erreur spécifique peuvent être récupéré en appelant [GetLastError](#getlasterror). Les erreurs suivantes s’appliquent à cette fonction membre :  
  
- **WSANOTINITIALISED** un bon [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) doit se produire avant d’utiliser cette API.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
- **WSAEADDRINUSE** une tentative a été effectuée à l’écoute sur une adresse en cours d’utilisation.  
  
- **Winsock** une opération de blocage Windows Sockets est en cours.  
  
- **WSAEINVAL** le socket n’a pas été lié avec **lier** ou est déjà connecté.  
  
- **WSAEISCONN** le socket est déjà connecté.  
  
- **WSAEMFILE** plus aucun descripteur de fichier est disponible.  
  
- `WSAENOBUFS`Aucun espace tampon n’est disponible.  
  
- **WSAENOTSOCK** le descripteur n’est pas un socket.  
  
- **WSAEOPNOTSUPP** le socket référencé n’est pas un type qui prend en charge la `Listen` opération.  
  
### <a name="remarks"></a>Remarques  
 Pour accepter les connexions, le socket est d’abord créé avec **créer**, une file d’attente pour les connexions entrantes est spécifié avec `Listen`, et les connexions sont acceptées puis **accepter**. `Listen`s’applique uniquement aux sockets qui prennent en charge les connexions, autrement dit, ceux de type **SOCK_STREAM**. Le socket est placé en mode « passif » où les connexions entrantes sont pris en compte et la file d’attente en attente d’acceptation par le processus.  
  
 Cette fonction est généralement utilisée par les serveurs (ou n’importe quelle application qui souhaite accepter les connexions) qui peut avoir plusieurs demandes de connexion à la fois : si une demande de connexion arrive à la file d’attente est pleine, le client reçoit une erreur avec une indication de **WSAECONNREFUSED**.  
  
 `Listen`essaie de continuer à fonctionner rationnelle lorsqu’il n’y a aucuns ports disponibles (descripteurs). Il accepte les connexions jusqu'à ce que la file d’attente est vide. Si les ports sont disponibles, un appel ultérieur à `Listen` ou **accepter** sera rechargement de la file d’attente au actuel ou plus récent » backlog, » si possible et reprend l’écoute des connexions entrantes.  
  
##  <a name="m_hsocket"></a>CAsyncSocket::m_hSocket  
 Contient le **SOCKET** handle pour le socket encapsulé par cet `CAsyncSocket` objet.  
  
```  
SOCKET m_hSocket;  
```  
  
##  <a name="onaccept"></a>CAsyncSocket::OnAccept  
 Appelée par l’infrastructure pour avertir un socket d’écoute qu’il peut accepter les demandes de connexion en attente en appelant le [accepter](#accept) fonction membre.  
  
```  
virtual void OnAccept(int nErrorCode);
```  
  
### <a name="parameters"></a>Paramètres  
 `nErrorCode`  
 L’erreur la plus récente sur un socket. Codes d’erreur suivants s’applique à la `OnAccept` fonction membre :  
  
- **0** la fonction exécutée avec succès.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [Windows Sockets : Notifications de sockets](../../mfc/windows-sockets-socket-notifications.md).  
  
##  <a name="onclose"></a>CAsyncSocket::OnClose  
 Appelée par l’infrastructure pour avertir le socket que le socket connecté est fermé par son processus.  
  
```  
virtual void OnClose(int nErrorCode);
```  
  
### <a name="parameters"></a>Paramètres  
 `nErrorCode`  
 L’erreur la plus récente sur un socket. Codes d’erreur suivants s’appliquent à la `OnClose` fonction membre :  
  
- **0** la fonction exécutée avec succès.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
- **WSAECONNRESET** la connexion a été réinitialisée par la partie distante.  
  
- **WSAECONNABORTED** la connexion a été abandonnée en raison d’une défaillance ou de délai d’attente.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [Windows Sockets : Notifications de sockets](../../mfc/windows-sockets-socket-notifications.md).  
  
##  <a name="onconnect"></a>CAsyncSocket::OnConnect  
 Appelé par l’infrastructure pour notifier au socket de connexion que sa tentative de connexion est terminée avec succès ou erreur.  
  
```  
virtual void OnConnect(int nErrorCode);
```  
  
### <a name="parameters"></a>Paramètres  
 `nErrorCode`  
 L’erreur la plus récente sur un socket. Codes d’erreur suivants s’appliquent à la `OnConnect` fonction membre :  
  
- **0** la fonction exécutée avec succès.  
  
- **WSAEADDRINUSE** l’adresse spécifiée est déjà en cours d’utilisation.  
  
- **WSAEADDRNOTAVAIL** l’adresse spécifiée n’est pas disponible à partir de l’ordinateur local.  
  
- **WSAEAFNOSUPPORT** adresses dans la famille spécifiée ne peut pas être utilisées avec ce socket.  
  
- **WSAECONNREFUSED** tentative de connexion a été rejetée.  
  
- **WSAEDESTADDRREQ** une adresse de destination est requise.  
  
- **WSAEFAULT** le `lpSockAddrLen` argument est incorrect.  
  
- **WSAEINVAL** le socket est déjà lié à une adresse.  
  
- **WSAEISCONN** le socket est déjà connecté.  
  
- **WSAEMFILE** plus aucun descripteur de fichier est disponible.  
  
- **WSAENETUNREACH** le réseau ne peut pas être atteint à partir de cet hôte en ce moment.  
  
- `WSAENOBUFS`Aucun espace tampon n’est disponible. Le socket n’est pas accessible.  
  
- **WSAENOTCONN** le socket n’est pas connecté.  
  
- **WSAENOTSOCK** le descripteur est un fichier, pas un socket.  
  
- **WSAETIMEDOUT** tentative de connexion dépassé sans avoir à établir une connexion.  
  
### <a name="remarks"></a>Notes  
  
> [!NOTE]
>  Dans [CSocket](../../mfc/reference/csocket-class.md), le `OnConnect` fonction de notification n’est jamais appelée. Pour les connexions, vous appelez simplement **connecter**, qui renverra lorsque la connexion est terminée (correctement ou erreur). La gestion des notifications de connexion est un détail d’implémentation MFC.  
  
 Pour plus d’informations, consultez [Windows Sockets : Notifications de sockets](../../mfc/windows-sockets-socket-notifications.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCAsyncSocket n °&1;](../../mfc/reference/codesnippet/cpp/casyncsocket-class_1.cpp)]  
  
##  <a name="onoutofbanddata"></a>CAsyncSocket::OnOutOfBandData  
 Appelé par l’infrastructure pour notifier au socket récepteur que le socket émetteur est hors-bande les données à envoyer.  
  
```  
virtual void OnOutOfBandData(int nErrorCode);
```  
  
### <a name="parameters"></a>Paramètres  
 `nErrorCode`  
 L’erreur la plus récente sur un socket. Codes d’erreur suivants s’appliquent à la `OnOutOfBandData` fonction membre :  
  
- **0** la fonction exécutée avec succès.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
### <a name="remarks"></a>Remarques  
 Les données hors bande sont un canal logiquement indépendant qui est associé à chaque paire de sockets connectées de type **SOCK_STREAM**. Le canal est généralement utilisé pour envoyer des données urgentes.  
  
 MFC prend en charge les données hors bande, mais les utilisateurs de la classe `CAsyncSocket` est déconseillé de l’utiliser. La plus simple consiste à créer un deuxième socket pour transmettre ces données. Pour plus d’informations sur les données hors bande, consultez la page [Windows Sockets : Notifications de sockets](../../mfc/windows-sockets-socket-notifications.md).  
  
##  <a name="onreceive"></a>CAsyncSocket::OnReceive  
 Appelée par l’infrastructure pour avertir le socket qu’il existe des données dans la mémoire tampon qui peut être récupérée en appelant le **réception** fonction membre.  
  
```  
virtual void OnReceive(int nErrorCode);
```  
  
### <a name="parameters"></a>Paramètres  
 `nErrorCode`  
 L’erreur la plus récente sur un socket. Codes d’erreur suivants s’appliquent à la `OnReceive` fonction membre :  
  
- **0** la fonction exécutée avec succès.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [Windows Sockets : Notifications de sockets](../../mfc/windows-sockets-socket-notifications.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCAsyncSocket n °&2;](../../mfc/reference/codesnippet/cpp/casyncsocket-class_2.cpp)]  
  
##  <a name="onsend"></a>CAsyncSocket::OnSend  
 Appelée par l’infrastructure pour avertir le socket qu’il peut maintenant envoyer des données en appelant le **envoyer** fonction membre.  
  
```  
virtual void OnSend(int nErrorCode);
```  
  
### <a name="parameters"></a>Paramètres  
 `nErrorCode`  
 L’erreur la plus récente sur un socket. Codes d’erreur suivants s’appliquent à la `OnSend` fonction membre :  
  
- **0** la fonction exécutée avec succès.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [Windows Sockets : Notifications de sockets](../../mfc/windows-sockets-socket-notifications.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCAsyncSocket n °&3;](../../mfc/reference/codesnippet/cpp/casyncsocket-class_3.cpp)]  
  
##  <a name="operator_eq"></a>CAsyncSocket::operator =  
 Affecte une nouvelle valeur à un `CAsyncSocket` objet.  
  
```  
void operator=(const CAsyncSocket& rSrc);
```  
  
### <a name="parameters"></a>Paramètres  
 `rSrc`  
 Une référence à un fichier `CAsyncSocket` objet.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette fonction pour copier une existante `CAsyncSocket` objet vers un autre `CAsyncSocket` objet.  
  
##  <a name="operator_socket"></a>CAsyncSocket::operator SOCKET  
 Utilisez cet opérateur pour récupérer le **SOCKET** gérer de la `CAsyncSocket` objet.  
  
```  
operator SOCKET() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si l’opération réussit, le handle de la **SOCKET** objet ; sinon, **NULL**.  
  
### <a name="remarks"></a>Notes  
 Vous pouvez utiliser le handle pour appeler directement les API Windows.  
  
##  <a name="receive"></a>CAsyncSocket::Receive  
 Appelez cette fonction membre pour recevoir des données à partir d’un socket.  
  
```  
virtual int Receive(
    void* lpBuf,  
    int nBufLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpBuf`  
 Une mémoire tampon pour les données entrantes.  
  
 `nBufLen`  
 La longueur du `lpBuf` en octets.  
  
 `nFlags`  
 Spécifie le mode dans lequel l’appel est effectué. La sémantique de cette fonction est déterminée par les options de socket et le `nFlags` paramètre. Ce dernier est construit en combinant les valeurs suivantes avec le C++ `OR` opérateur :  
  
- **MSG_PEEK** lire les données entrantes. Les données sont copiées dans la mémoire tampon, mais ne sont pas supprimées de la file d’attente d’entrée.  
  
- **MSG_OOB** traiter les données hors bande.  
  
### <a name="return-value"></a>Valeur de retour  
 Si aucune erreur ne se produit, **réception** renvoie le nombre d’octets reçus. Si la connexion a été fermée, elle retourne 0. Sinon, une valeur de **SOCKET_ERROR** est retourné, et un code d’erreur spécifique peut être récupéré en appelant [GetLastError](#getlasterror). Les erreurs suivantes s’appliquent à cette fonction membre :  
  
- **WSANOTINITIALISED** un bon [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) doit se produire avant d’utiliser cette API.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
- **WSAENOTCONN** le socket n’est pas connecté.  
  
- **Winsock** une opération de blocage Windows Sockets est en cours.  
  
- **WSAENOTSOCK** le descripteur n’est pas un socket.  
  
- **WSAEOPNOTSUPP MSG_OOB** a été spécifié, mais le socket n’est pas de type **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** le socket a été arrêté ; il n’est pas possible d’appeler **réception** sur un socket après `ShutDown` a été appelée avec `nHow` définie sur 0 ou 2.  
  
- **WSAEWOULDBLOCK** le socket est marqué comme non bloquant et **réception** se bloquerait.  
  
- **WSAEMSGSIZE** le datagramme était trop grand pour tenir dans la mémoire tampon spécifiée et a été tronqué.  
  
- **WSAEINVAL** le socket n’a pas été lié avec **lier**.  
  
- **WSAECONNABORTED** le circuit virtuel a été abandonné en raison d’une défaillance ou de délai d’attente.  
  
- **WSAECONNRESET** le circuit virtuel a été réinitialisé par le côté distant.  
  
### <a name="remarks"></a>Notes  
 Cette fonction est utilisée pour les flux connectés ou les sockets datagramme et est utilisée pour lire des données entrantes.  
  
 Pour les sockets de type **SOCK_STREAM**, tel que les informations n’est actuellement disponible jusqu'à la taille de la mémoire tampon fournie sont retournées. Si le socket a été configuré pour la réception en ligne des données hors-bande (option de socket **SO_OOBINLINE**) et out-of-band données non lues, seulement out-of-band données seront renvoyées. L’application peut utiliser les **IOCtlSIOCATMARK** option ou [OnOutOfBandData](#onoutofbanddata) pour déterminer si des données plus out-of-band restent à lire.  
  
 Pour les sockets datagramme, les données sont extraites du premier datagramme en file d’attente, jusqu'à la taille de la mémoire tampon fournie. Si le datagramme est supérieur à la mémoire tampon fournie, la mémoire tampon est remplie avec la première partie du datagramme, les données excédentaires sont perdues, et **réception** renvoie la valeur **SOCKET_ERROR** avec le code d’erreur défini sur **WSAEMSGSIZE**. Si aucune données entrantes ne sont disponibles sur le socket, une valeur de **SOCKET_ERROR** est retournée avec le code d’erreur défini sur **WSAEWOULDBLOCK**. Le [OnReceive](#onreceive) fonction de rappel peut être utilisée pour déterminer si davantage de données arrivent.  
  
 Si le socket est de type **SOCK_STREAM** et le côté distant a fermé la connexion en douceur, un **réception** se termine immédiatement avec 0 octets reçus. Si la connexion a été réinitialisée, un **réception** échoue avec l’erreur **WSAECONNRESET**.  
  
 **Réception** doit être appelée qu’une seule fois pour chaque heure [CAsyncSocket::OnReceive](#onreceive) est appelée.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CAsyncSocket::OnReceive](#onreceive).  
  
##  <a name="receivefrom"></a>CAsyncSocket::ReceiveFrom  
 Appelez cette fonction membre pour recevoir un datagramme et stocke l’adresse source dans le [SOCKADDR](../../mfc/reference/sockaddr-structure.md) structure ou dans `rSocketAddress`.  
  
```  
int ReceiveFrom(
    void* lpBuf,  
    int nBufLen,  
    CString& rSocketAddress,  
    UINT& rSocketPort,  
    int nFlags = 0);

 
int ReceiveFrom(
    void* lpBuf,  
    int nBufLen,  
    SOCKADDR* lpSockAddr,  
    int* lpSockAddrLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpBuf`  
 Une mémoire tampon pour les données entrantes.  
  
 `nBufLen`  
 La longueur du `lpBuf` en octets.  
  
 `rSocketAddress`  
 Référence à un `CString` objet qui reçoit une adresse IP numérique en pointillé.  
  
 `rSocketPort`  
 Référence à un **UINT** qui stocke un port.  
  
 `lpSockAddr`  
 Un pointeur vers un [SOCKADDR](../../mfc/reference/sockaddr-structure.md) structure qui conserve l’adresse source au moment du retour.  
  
 `lpSockAddrLen`  
 Un pointeur vers la longueur de l’adresse source dans `lpSockAddr` en octets.  
  
 `nFlags`  
 Spécifie le mode dans lequel l’appel est effectué. La sémantique de cette fonction est déterminée par les options de socket et le `nFlags` paramètre. Ce dernier est construit en combinant les valeurs suivantes avec le C++ `OR` opérateur :  
  
- **MSG_PEEK** lire les données entrantes. Les données sont copiées dans la mémoire tampon, mais ne sont pas supprimées de la file d’attente d’entrée.  
  
- **MSG_OOB** traiter les données hors bande.  
  
### <a name="return-value"></a>Valeur de retour  
 Si aucune erreur ne se produit, `ReceiveFrom` renvoie le nombre d’octets reçus. Si la connexion a été fermée, elle retourne 0. Sinon, une valeur de **SOCKET_ERROR** est retourné, et un code d’erreur spécifique peut être récupéré en appelant `GetLastError`. Les erreurs suivantes s’appliquent à cette fonction membre :  
  
- **WSANOTINITIALISED** un bon [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) doit se produire avant d’utiliser cette API.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
- **WSAEFAULT** le `lpSockAddrLen` argument n’est pas valide : le `lpSockAddr` tampon est trop petite pour contenir l’adresse de l’homologue.  
  
- **Winsock** une opération de blocage Windows Sockets est en cours.  
  
- **WSAEINVAL** le socket n’a pas été lié avec **lier**.  
  
- **WSAENOTCONN** le socket n’est pas connecté ( **SOCK_STREAM** uniquement).  
  
- **WSAENOTSOCK** le descripteur n’est pas un socket.  
  
- **WSAEOPNOTSUPP MSG_OOB** a été spécifié, mais le socket n’est pas de type **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** le socket a été arrêté ; il n’est pas possible d’appeler `ReceiveFrom` sur un socket après `ShutDown` a été appelée avec `nHow` définie sur 0 ou 2.  
  
- **WSAEWOULDBLOCK** le socket est marqué comme non bloquant et `ReceiveFrom` se bloquerait.  
  
- **WSAEMSGSIZE** le datagramme était trop grand pour tenir dans la mémoire tampon spécifiée et a été tronqué.  
  
- **WSAECONNABORTED** le circuit virtuel a été abandonné en raison d’une défaillance ou de délai d’attente.  
  
- **WSAECONNRESET** le circuit virtuel a été réinitialisé par le côté distant.  
  
### <a name="remarks"></a>Notes  
 Cette fonction est utilisée pour lire des données entrantes sur un socket (éventuellement connecté) et de capturer l’adresse à partir de laquelle les données ont été envoyées.  
  
 Pour gérer les adresses IPv6, utilisez [CAsyncSocket::ReceiveFromEx](#receivefromex).  
  
 Pour les sockets de type **SOCK_STREAM**, tel que les informations n’est actuellement disponible jusqu'à la taille de la mémoire tampon fournie sont retournées. Si le socket a été configuré pour la réception en ligne des données hors-bande (option de socket **SO_OOBINLINE**) et out-of-band données non lues, seulement out-of-band données seront renvoyées. L’application peut utiliser les **IOCtlSIOCATMARK** option ou `OnOutOfBandData` pour déterminer si des données plus out-of-band restent à lire. Le `lpSockAddr` et `lpSockAddrLen` paramètres sont ignorés pour **SOCK_STREAM** sockets.  
  
 Pour les sockets datagramme, les données sont extraites du premier datagramme en file d’attente, jusqu'à la taille de la mémoire tampon fournie. Si le datagramme est supérieur à la mémoire tampon fournie, la mémoire tampon est remplie avec la première partie du message, les données excédentaires sont perdues, et `ReceiveFrom` renvoie la valeur **SOCKET_ERROR** avec le code d’erreur défini sur **WSAEMSGSIZE**.  
  
 Si `lpSockAddr` est différent de zéro, et le socket est de type **SOCK_DGRAM**, l’adresse réseau du socket qui a envoyé les données est copié du [SOCKADDR](../../mfc/reference/sockaddr-structure.md) structure. La valeur pointée par `lpSockAddrLen` est initialisée à la taille de cette structure et est modifié sur retour pour indiquer la taille réelle de l’adresse qui y sont stocké. Si aucune donnée entrante n’est disponible sur le socket, le `ReceiveFrom` appel attend des données arrivent, sauf si le socket est non bloquant. Dans ce cas, une valeur de **SOCKET_ERROR** est retournée avec le code d’erreur défini sur **WSAEWOULDBLOCK**. Le `OnReceive` rappel peut être utilisé pour déterminer si davantage de données arrivent.  
  
 Si le socket est de type **SOCK_STREAM** et le côté distant a fermé la connexion en douceur, un `ReceiveFrom` se termine immédiatement avec 0 octets reçus.  
  
##  <a name="receivefromex"></a>CAsyncSocket::ReceiveFromEx  
 Appelez cette fonction membre pour recevoir un datagramme et stocke l’adresse source dans le [SOCKADDR](../../mfc/reference/sockaddr-structure.md) structure ou dans `rSocketAddress` (prend en charge les adresses IPv6).  
  
```  
int ReceiveFromEx(
    void* lpBuf,  
    int nBufLen,  
    CString& rSocketAddress,  
    UINT& rSocketPort,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpBuf`  
 Une mémoire tampon pour les données entrantes.  
  
 `nBufLen`  
 La longueur du `lpBuf` en octets.  
  
 `rSocketAddress`  
 Référence à un `CString` objet qui reçoit une adresse IP numérique en pointillé.  
  
 `rSocketPort`  
 Référence à un **UINT** qui stocke un port.  
  
 `nFlags`  
 Spécifie le mode dans lequel l’appel est effectué. La sémantique de cette fonction est déterminée par les options de socket et le `nFlags` paramètre. Ce dernier est construit en combinant les valeurs suivantes avec le C++ `OR` opérateur :  
  
- **MSG_PEEK** lire les données entrantes. Les données sont copiées dans la mémoire tampon, mais ne sont pas supprimées de la file d’attente d’entrée.  
  
- **MSG_OOB** traiter les données hors bande.  
  
### <a name="return-value"></a>Valeur de retour  
 Si aucune erreur ne se produit, `ReceiveFromEx` renvoie le nombre d’octets reçus. Si la connexion a été fermée, elle retourne 0. Sinon, une valeur de **SOCKET_ERROR** est retourné, et un code d’erreur spécifique peut être récupéré en appelant `GetLastError`. Les erreurs suivantes s’appliquent à cette fonction membre :  
  
- **WSANOTINITIALISED** un bon [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) doit se produire avant d’utiliser cette API.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
- **WSAEFAULT** le `lpSockAddrLen` argument n’est pas valide : le `lpSockAddr` tampon est trop petite pour contenir l’adresse de l’homologue.  
  
- **Winsock** une opération de blocage Windows Sockets est en cours.  
  
- **WSAEINVAL** le socket n’a pas été lié avec **lier**.  
  
- **WSAENOTCONN** le socket n’est pas connecté ( **SOCK_STREAM** uniquement).  
  
- **WSAENOTSOCK** le descripteur n’est pas un socket.  
  
- **WSAEOPNOTSUPP MSG_OOB** a été spécifié, mais le socket n’est pas de type **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** le socket a été arrêté ; il n’est pas possible d’appeler `ReceiveFromEx` sur un socket après `ShutDown` a été appelée avec `nHow` définie sur 0 ou 2.  
  
- **WSAEWOULDBLOCK** le socket est marqué comme non bloquant et `ReceiveFromEx` se bloquerait.  
  
- **WSAEMSGSIZE** le datagramme était trop grand pour tenir dans la mémoire tampon spécifiée et a été tronqué.  
  
- **WSAECONNABORTED** le circuit virtuel a été abandonné en raison d’une défaillance ou de délai d’attente.  
  
- **WSAECONNRESET** le circuit virtuel a été réinitialisé par le côté distant.  
  
### <a name="remarks"></a>Notes  
 Cette fonction est utilisée pour lire des données entrantes sur un socket (éventuellement connecté) et de capturer l’adresse à partir de laquelle les données ont été envoyées.  
  
 Cette fonction est identique à [CAsyncSocket::ReceiveFrom](#receivefrom) , sauf qu’il gère IPv6 résout ainsi que les anciens protocoles.  
  
 Pour les sockets de type **SOCK_STREAM**, tel que les informations n’est actuellement disponible jusqu'à la taille de la mémoire tampon fournie sont retournées. Si le socket a été configuré pour la réception en ligne des données hors-bande (option de socket **SO_OOBINLINE**) et out-of-band données non lues, seulement out-of-band données seront renvoyées. L’application peut utiliser les **IOCtlSIOCATMARK** option ou `OnOutOfBandData` pour déterminer si des données plus out-of-band restent à lire. Le `lpSockAddr` et `lpSockAddrLen` paramètres sont ignorés pour **SOCK_STREAM** sockets.  
  
 Pour les sockets datagramme, les données sont extraites du premier datagramme en file d’attente, jusqu'à la taille de la mémoire tampon fournie. Si le datagramme est supérieur à la mémoire tampon fournie, la mémoire tampon est remplie avec la première partie du message, les données excédentaires sont perdues, et `ReceiveFromEx` renvoie la valeur **SOCKET_ERROR** avec le code d’erreur défini sur **WSAEMSGSIZE**.  
  
 Si `lpSockAddr` est différent de zéro, et le socket est de type **SOCK_DGRAM**, l’adresse réseau du socket qui a envoyé les données est copié du [SOCKADDR](../../mfc/reference/sockaddr-structure.md) structure. La valeur pointée par `lpSockAddrLen` est initialisée à la taille de cette structure et est modifié sur retour pour indiquer la taille réelle de l’adresse qui y sont stocké. Si aucune donnée entrante n’est disponible sur le socket, le `ReceiveFromEx` appel attend des données arrivent, sauf si le socket est non bloquant. Dans ce cas, une valeur de **SOCKET_ERROR** est retournée avec le code d’erreur défini sur **WSAEWOULDBLOCK**. Le `OnReceive` rappel peut être utilisé pour déterminer si davantage de données arrivent.  
  
 Si le socket est de type **SOCK_STREAM** et le côté distant a fermé la connexion en douceur, un `ReceiveFromEx` se termine immédiatement avec 0 octets reçus.  
  
##  <a name="send"></a>CAsyncSocket::Send  
 Appelez cette fonction membre pour l’envoi de données sur un socket connecté.  
  
```  
virtual int Send(
    const void* lpBuf,  
    int nBufLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpBuf`  
 Une mémoire tampon contenant les données à transmettre.  
  
 `nBufLen`  
 La longueur des données dans `lpBuf` en octets.  
  
 `nFlags`  
 Spécifie le mode dans lequel l’appel est effectué. La sémantique de cette fonction est déterminée par les options de socket et le `nFlags` paramètre. Ce dernier est construit en combinant les valeurs suivantes avec le C++ `OR` opérateur :  
  
- **MSG_DONTROUTE** Spécifie que les données ne doivent pas subir de routage. Un fournisseur Windows Sockets peut choisir d’ignorer cet indicateur.  
  
- **MSG_OOB** envoyer des données d’out-of-band ( **SOCK_STREAM** uniquement).  
  
### <a name="return-value"></a>Valeur de retour  
 Si aucune erreur ne se produit, **envoyer** retourne le nombre total de caractères envoyés. (Notez que cela peut être inférieur au nombre indiqué par `nBufLen`.) Sinon, une valeur de **SOCKET_ERROR** est retourné, et un code d’erreur spécifique peut être récupéré en appelant [GetLastError](#getlasterror). Les erreurs suivantes s’appliquent à cette fonction membre :  
  
- **WSANOTINITIALISED** un bon [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) doit se produire avant d’utiliser cette API.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
- **WSAEACCES** l’adresse demandée est une adresse de diffusion, mais l’indicateur approprié n’a pas été définie.  
  
- **Winsock** une opération de blocage Windows Sockets est en cours.  
  
- **WSAEFAULT** le `lpBuf` argument n’est pas une partie de l’espace d’adressage utilisateur valide.  
  
- **WSAENETRESET** la connexion doit être réinitialisée, car l’implémentation Windows Sockets abandonnée.  
  
- `WSAENOBUFS`L’implémentation Windows Sockets signale un interblocage de la mémoire tampon.  
  
- **WSAENOTCONN** le socket n’est pas connecté.  
  
- **WSAENOTSOCK** le descripteur n’est pas un socket.  
  
- **WSAEOPNOTSUPP MSG_OOB** a été spécifié, mais le socket n’est pas de type **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** le socket a été arrêté ; il n’est pas possible d’appeler **envoyer** sur un socket après `ShutDown` a été appelée avec `nHow` défini sur 1 ou 2.  
  
- **WSAEWOULDBLOCK** le socket est marqué comme non bloquant et l’opération demandée.  
  
- **WSAEMSGSIZE** le socket est de type **SOCK_DGRAM**, et le datagramme est supérieur à la valeur maximale prise en charge par l’implémentation Windows Sockets.  
  
- **WSAEINVAL** le socket n’a pas été lié avec **lier**.  
  
- **WSAECONNABORTED** le circuit virtuel a été abandonné en raison d’une défaillance ou de délai d’attente.  
  
- **WSAECONNRESET** le circuit virtuel a été réinitialisé par le côté distant.  
  
### <a name="remarks"></a>Notes  
 **Envoyer** est utilisé pour écrire des données sortant sur les sockets de flux de données ou de datagramme connectés. Pour les sockets de datagramme, il convient pour ne pas dépasser la taille maximale du paquet IP des sous-réseaux sous-jacente, qui est fourni par le **iMaxUdpDg** élément dans le [WSADATA](../../mfc/reference/wsadata-structure.md) structure renvoyée par `AfxSocketInit`. Si les données sont trop longues à traverser atomiquement le protocole sous-jacent, l’erreur **WSAEMSGSIZE** est retournée `GetLastError`, et aucune donnée n’est transmise.  
  
 Notez que, pour un datagramme, socket l’achèvement d’une **envoyer** n’indique pas que les données ont été correctement remises.  
  
 Sur `CAsyncSocket` les objets de type **SOCK_STREAM**, le nombre d’octets écrits peut être comprise entre 1 et la longueur attendue, selon la disponibilité de mémoire tampon sur les hôtes locaux et étrangers.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CAsyncSocket::OnSend](#onsend).  
  
##  <a name="sendto"></a>CAsyncSocket::SendTo  
 Appelez cette fonction membre pour envoyer des données vers une destination spécifique.  
  
```  
int SendTo(
    const void* lpBuf,  
    int nBufLen,  
    UINT nHostPort,  
    LPCTSTR lpszHostAddress = NULL,  
    int nFlags = 0);

 
int SendTo(
    const void* lpBuf,  
    int nBufLen,  
    const SOCKADDR* lpSockAddr,  
    int nSockAddrLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpBuf`  
 Une mémoire tampon contenant les données à transmettre.  
  
 `nBufLen`  
 La longueur des données dans `lpBuf` en octets.  
  
 `nHostPort`  
 Le port identifiant l’application de socket.  
  
 `lpszHostAddress`  
 L’adresse réseau du socket à laquelle cet objet est connecté : un nom d’ordinateur tel que « FTP.Microsoft.com », ou un nombre en pointillés comme « 128.56.22.8 ».  
  
 `nFlags`  
 Spécifie le mode dans lequel l’appel est effectué. La sémantique de cette fonction est déterminée par les options de socket et le `nFlags` paramètre. Ce dernier est construit en combinant les valeurs suivantes avec le C++ `OR` opérateur :  
  
- **MSG_DONTROUTE** Spécifie que les données ne doivent pas subir de routage. Un fournisseur Windows Sockets peut choisir d’ignorer cet indicateur.  
  
- **MSG_OOB** envoyer des données d’out-of-band ( **SOCK_STREAM** uniquement).  
  
 `lpSockAddr`  
 Un pointeur vers un [SOCKADDR](../../mfc/reference/sockaddr-structure.md) structure qui contient l’adresse de socket cible.  
  
 `nSockAddrLen`  
 La longueur de l’adresse dans `lpSockAddr` en octets.  
  
### <a name="return-value"></a>Valeur de retour  
 Si aucune erreur ne se produit, `SendTo` renvoie le nombre total de caractères envoyés. (Notez que cela peut être inférieur au nombre indiqué par `nBufLen`.) Sinon, une valeur de **SOCKET_ERROR** est retourné, et un code d’erreur spécifique peut être récupéré en appelant [GetLastError](#getlasterror). Les erreurs suivantes s’appliquent à cette fonction membre :  
  
- **WSANOTINITIALISED** un bon [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) doit se produire avant d’utiliser cette API.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
- **WSAEACCES** l’adresse demandée est une adresse de diffusion, mais l’indicateur approprié n’a pas été définie.  
  
- **Winsock** une opération de blocage Windows Sockets est en cours.  
  
- **WSAEFAULT** le `lpBuf` ou `lpSockAddr` paramètres ne font pas partie de l’espace d’adressage utilisateur, ou le `lpSockAddr` argument est trop petit (inférieur à la taille d’un [SOCKADDR](../../mfc/reference/sockaddr-structure.md) structure).  
  
- **WSAEINVAL** le nom d’hôte n’est pas valide.  
  
- **WSAENETRESET** la connexion doit être réinitialisée, car l’implémentation Windows Sockets abandonnée.  
  
- `WSAENOBUFS`L’implémentation Windows Sockets signale un interblocage de la mémoire tampon.  
  
- **WSAENOTCONN** le socket n’est pas connecté ( **SOCK_STREAM** uniquement).  
  
- **WSAENOTSOCK** le descripteur n’est pas un socket.  
  
- **WSAEOPNOTSUPP MSG_OOB** a été spécifié, mais le socket n’est pas de type **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** le socket a été arrêté ; il n’est pas possible d’appeler `SendTo` sur un socket après `ShutDown` a été appelée avec `nHow` défini sur 1 ou 2.  
  
- **WSAEWOULDBLOCK** le socket est marqué comme non bloquant et l’opération demandée.  
  
- **WSAEMSGSIZE** le socket est de type **SOCK_DGRAM**, et le datagramme est supérieur à la valeur maximale prise en charge par l’implémentation Windows Sockets.  
  
- **WSAECONNABORTED** le circuit virtuel a été abandonné en raison d’une défaillance ou de délai d’attente.  
  
- **WSAECONNRESET** le circuit virtuel a été réinitialisé par le côté distant.  
  
- **WSAEADDRNOTAVAIL** l’adresse spécifiée n’est pas disponible à partir de l’ordinateur local.  
  
- **WSAEAFNOSUPPORT** adresses dans la famille spécifiée ne peut pas être utilisées avec ce socket.  
  
- **WSAEDESTADDRREQ** une adresse de destination est requise.  
  
- **WSAENETUNREACH** le réseau ne peut pas être atteint à partir de cet hôte en ce moment.  
  
### <a name="remarks"></a>Remarques  
 `SendTo`est utilisée sur les sockets datagramme ou un flux de données et est utilisé pour écrire des données sortant sur un socket. Pour les sockets de datagramme, il convient pour ne pas dépasser la taille maximale du paquet IP des sous-réseaux sous-jacente, qui est fourni par le **iMaxUdpDg** élément dans le [WSADATA](../../mfc/reference/wsadata-structure.md) structure remplis par [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit). Si les données sont trop longues à traverser atomiquement le protocole sous-jacent, l’erreur **WSAEMSGSIZE** est retournée, et aucune donnée n’est transmise.  
  
 Notez que l’achèvement d’une `SendTo` n’indique pas que les données ont été correctement remises.  
  
 `SendTo`est utilisé uniquement sur un **SOCK_DGRAM** socket pour envoyer un datagramme à un socket spécifique identifié par le `lpSockAddr` paramètre.  
  
 Pour envoyer une diffusion (sur un **SOCK_DGRAM** uniquement), l’adresse dans le `lpSockAddr` paramètre doit être construit à l’aide de l’adresse IP spéciale **INADDR_BROADCAST** (défini dans le fichier d’en-tête Windows Sockets WINSOCK. (H) avec le numéro de port souhaité. Ou, si le `lpszHostAddress` paramètre est **NULL**, le socket est configuré pour la diffusion. Il est généralement déconseillé pour un datagramme diffusé à dépasser la taille à laquelle la fragmentation peut se produire, ce qui implique que la partie données du datagramme (à l’exception des en-têtes) ne doit pas dépasser 512 octets.  
  
 Pour gérer les adresses IPv6, utilisez [CAsyncSocket::SendToEx](#sendtoex).  
  
##  <a name="sendtoex"></a>CAsyncSocket::SendToEx  
 Appelez cette fonction membre pour envoyer des données vers une destination spécifique (gère les adresses IPv6).  
  
```  
int SendToEx(
    const void* lpBuf,  
    int nBufLen,  
    UINT nHostPort,  
    LPCTSTR lpszHostAddress = NULL,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpBuf`  
 Une mémoire tampon contenant les données à transmettre.  
  
 `nBufLen`  
 La longueur des données dans `lpBuf` en octets.  
  
 `nHostPort`  
 Le port identifiant l’application de socket.  
  
 `lpszHostAddress`  
 L’adresse réseau du socket à laquelle cet objet est connecté : un nom d’ordinateur tel que « FTP.Microsoft.com », ou un nombre en pointillés comme « 128.56.22.8 ».  
  
 `nFlags`  
 Spécifie le mode dans lequel l’appel est effectué. La sémantique de cette fonction est déterminée par les options de socket et le `nFlags` paramètre. Ce dernier est construit en combinant les valeurs suivantes avec le C++ `OR` opérateur :  
  
- **MSG_DONTROUTE** Spécifie que les données ne doivent pas subir de routage. Un fournisseur Windows Sockets peut choisir d’ignorer cet indicateur.  
  
- **MSG_OOB** envoyer des données d’out-of-band ( **SOCK_STREAM** uniquement).  
  
### <a name="return-value"></a>Valeur de retour  
 Si aucune erreur ne se produit, `SendToEx` renvoie le nombre total de caractères envoyés. (Notez que cela peut être inférieur au nombre indiqué par `nBufLen`.) Sinon, une valeur de **SOCKET_ERROR** est retourné, et un code d’erreur spécifique peut être récupéré en appelant [GetLastError](#getlasterror). Les erreurs suivantes s’appliquent à cette fonction membre :  
  
- **WSANOTINITIALISED** un bon [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) doit se produire avant d’utiliser cette API.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
- **WSAEACCES** l’adresse demandée est une adresse de diffusion, mais l’indicateur approprié n’a pas été définie.  
  
- **Winsock** une opération de blocage Windows Sockets est en cours.  
  
- **WSAEFAULT** le `lpBuf` ou `lpSockAddr` paramètres ne font pas partie de l’espace d’adressage utilisateur, ou le `lpSockAddr` argument est trop petit (inférieur à la taille d’un [SOCKADDR](../../mfc/reference/sockaddr-structure.md) structure).  
  
- **WSAEINVAL** le nom d’hôte n’est pas valide.  
  
- **WSAENETRESET** la connexion doit être réinitialisée, car l’implémentation Windows Sockets abandonnée.  
  
- `WSAENOBUFS`L’implémentation Windows Sockets signale un interblocage de la mémoire tampon.  
  
- **WSAENOTCONN** le socket n’est pas connecté ( **SOCK_STREAM** uniquement).  
  
- **WSAENOTSOCK** le descripteur n’est pas un socket.  
  
- **WSAEOPNOTSUPP MSG_OOB** a été spécifié, mais le socket n’est pas de type **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** le socket a été arrêté ; il n’est pas possible d’appeler `SendToEx` sur un socket après `ShutDown` a été appelée avec `nHow` défini sur 1 ou 2.  
  
- **WSAEWOULDBLOCK** le socket est marqué comme non bloquant et l’opération demandée.  
  
- **WSAEMSGSIZE** le socket est de type **SOCK_DGRAM**, et le datagramme est supérieur à la valeur maximale prise en charge par l’implémentation Windows Sockets.  
  
- **WSAECONNABORTED** le circuit virtuel a été abandonné en raison d’une défaillance ou de délai d’attente.  
  
- **WSAECONNRESET** le circuit virtuel a été réinitialisé par le côté distant.  
  
- **WSAEADDRNOTAVAIL** l’adresse spécifiée n’est pas disponible à partir de l’ordinateur local.  
  
- **WSAEAFNOSUPPORT** adresses dans la famille spécifiée ne peut pas être utilisées avec ce socket.  
  
- **WSAEDESTADDRREQ** une adresse de destination est requise.  
  
- **WSAENETUNREACH** le réseau ne peut pas être atteint à partir de cet hôte en ce moment.  
  
### <a name="remarks"></a>Notes  
 Cette méthode est identique à [CAsyncSocket::SendTo](#sendto) , sauf qu’il gère IPv6 résout ainsi que les anciens protocoles.  
  
 `SendToEx`est utilisée sur les sockets datagramme ou un flux de données et est utilisé pour écrire des données sortant sur un socket. Pour les sockets de datagramme, il convient pour ne pas dépasser la taille maximale du paquet IP des sous-réseaux sous-jacente, qui est fourni par le **iMaxUdpDg** élément dans le [WSADATA](../../mfc/reference/wsadata-structure.md) structure remplis par [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit). Si les données sont trop longues à traverser atomiquement le protocole sous-jacent, l’erreur **WSAEMSGSIZE** est retournée, et aucune donnée n’est transmise.  
  
 Notez que l’achèvement d’une `SendToEx` n’indique pas que les données ont été correctement remises.  
  
 `SendToEx`est utilisé uniquement sur un **SOCK_DGRAM** socket pour envoyer un datagramme à un socket spécifique identifié par le `lpSockAddr` paramètre.  
  
 Pour envoyer une diffusion (sur un **SOCK_DGRAM** uniquement), l’adresse dans le `lpSockAddr` paramètre doit être construit à l’aide de l’adresse IP spéciale **INADDR_BROADCAST** (défini dans le fichier d’en-tête Windows Sockets WINSOCK. (H) avec le numéro de port souhaité. Ou, si le `lpszHostAddress` paramètre est **NULL**, le socket est configuré pour la diffusion. Il est généralement déconseillé pour un datagramme diffusé à dépasser la taille à laquelle la fragmentation peut se produire, ce qui implique que la partie données du datagramme (à l’exception des en-têtes) ne doit pas dépasser 512 octets.  
  
##  <a name="setsockopt"></a>CAsyncSocket::SetSockOpt  
 Appelez cette fonction membre pour définir une option de socket.  
  
```  
BOOL SetSockOpt(
    int nOptionName,  
    const void* lpOptionValue,  
    int nOptionLen,  
    int nLevel = SOL_SOCKET);
```  
  
### <a name="parameters"></a>Paramètres  
 `nOptionName`  
 L’option de socket dont la valeur doit être définie.  
  
 `lpOptionValue`  
 Pointeur vers la mémoire tampon dans laquelle la valeur de l’option demandée est fournie.  
  
 `nOptionLen`  
 La taille de la `lpOptionValue` mémoire tampon en octets.  
  
 `nLevel`  
 Le niveau auquel elle est définie ; les niveaux de prise en charge uniquement sont **SOL_SOCKET** et **IPPROTO_TCP**.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; Sinon, 0 et un code d’erreur spécifique peuvent être récupéré en appelant [GetLastError](#getlasterror). Les erreurs suivantes s’appliquent à cette fonction membre :  
  
- **WSANOTINITIALISED** un bon [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) doit se produire avant d’utiliser cette API.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
- **WSAEFAULT** `lpOptionValue` n’est pas dans une partie de l’espace d’adressage de processus valide.  
  
- **Winsock** une opération de blocage Windows Sockets est en cours.  
  
- **WSAEINVAL** `nLevel` n’est pas valide, ou les informations contenues dans `lpOptionValue` n’est pas valide.  
  
- **WSAENETRESET** connexion a expiré lorsque **SO_KEEPALIVE** est défini.  
  
- **WSAENOPROTOOPT** l’option est inconnu ou non pris en charge. En particulier, **SO_BROADCAST** n’est pas pris en charge sur les sockets de type **SOCK_STREAM**, tandis que **SO_DONTLINGER**, **SO_KEEPALIVE**, **SO_LINGER**, et **SO_OOBINLINE** ne sont pas pris en charge sur les sockets de type **SOCK_DGRAM**.  
  
- **WSAENOTCONN** connexion a été réinitialisée lorsque **SO_KEEPALIVE** est défini.  
  
- **WSAENOTSOCK** le descripteur n’est pas un socket.  
  
### <a name="remarks"></a>Remarques  
 `SetSockOpt`définit la valeur actuelle d’une option de socket associée à un socket de tout type, dans n’importe quel état. Bien que les options peuvent exister à plusieurs niveaux de protocole, cette spécification définit uniquement les options qui existent au niveau du socket « supérieur ». Les options affectent les opérations de socket, par exemple si les données expédiées sont reçues dans le flux de données normale, si les messages de diffusion peuvent être envoyés sur le socket et ainsi de suite.  
  
 Il existe deux types d’options de socket : Boolean options permettant d’activer ou désactiver une fonctionnalité ou un comportement et qui nécessitent une valeur entière ou une structure. Pour activer une option booléenne, `lpOptionValue` pointe vers un entier différent de zéro. Pour désactiver l’option `lpOptionValue` pointe vers un entier égal à zéro. `nOptionLen`doit être égal à **sizeof (bool)** options booléennes. Pour les autres options, `lpOptionValue` pointe vers l’entier ou la structure qui contient la valeur souhaitée pour l’option, et `nOptionLen` est la longueur de l’entier ou la structure.  
  
 **SO_LINGER** l’action effectuée lorsque non envoyés données en file d’attente sur un socket de contrôles et la **fermer** fonction est appelée pour fermer le socket.  
  
 Par défaut, un socket ne peut pas être lié (voir [lier](#bind)) à une adresse locale qui est déjà en cours d’utilisation. Parfois, cependant, il peut être souhaitable de « réutiliser » une adresse de cette façon. Étant donné que chaque connexion est identifiée par la combinaison des adresses locales et distantes, il n’est pas un problème à la présence de deux sockets liés à la même adresse locale, que les adresses distantes sont différents.  
  
 Pour informer l’implémentation Windows Sockets qui un **lier** appel sur un socket ne doit pas être rejeté car l’adresse souhaitée est déjà en cours d’utilisation par un autre socket, l’application doit définir le **SO_REUSEADDR** option pour le socket avant l’émission de socket le **lier** appeler. Notez que l’option est interprétée uniquement au moment de la **lier** appeler : il est donc inutile (mais sans incidence) pour définir l’option sur un socket qui ne doit ne pas être lié à une adresse existante, et la définition ou la réinitialisation de l’option après la **lier** appel n’a aucun effet sur ce socket ou un autre.  
  
 Une application peut demander que l’implémentation Windows Sockets permettent l’utilisation de paquets « keep-alive » sur les connexions de protocole TCP (Transmission Control) en activant le **SO_KEEPALIVE** option de socket. Une implémentation Windows Sockets devez prend pas en charge l’utilisation de connexions persistantes : si elle existe, la sémantique de précision sont spécifiques à l’implémentation, mais doit être conforme à la section 4.2.3.6 de la RFC 1122 : « Requirements for Internet Hosts — les couches de Communication. » Si une connexion est supprimée à la suite de « persistantes » le code d’erreur **WSAENETRESET** est retournée pour tous les appels en cours sur le socket, et tous les appels suivants échoueront avec **WSAENOTCONN**.  
  
 Le **TCP_NODELAY** option désactive l’algorithme Nagle. L’algorithme Nagle est utilisé pour réduire le nombre de petits paquets envoyés par un hôte en mémoire tampon d’envoi sans accusé de réception de données jusqu'à ce qu’un paquet de taille réelle peut être envoyé. Toutefois, pour certaines applications cet algorithme peut nuire aux performances, et **TCP_NODELAY** peut être utilisé pour désactiver cette option. Les rédacteurs d’application ne doivent pas être définie **TCP_NODELAY** à moins que l’impact de cette opération est connue et souhaitées, depuis le paramètre **TCP_NODELAY** peut avoir un impact négatif sur les performances réseau. **TCP_NODELAY** est la seule option de socket qui utilise le niveau de prise en charge **IPPROTO_TCP**; toutes les autres options utilisent niveau **SOL_SOCKET**.  
  
 Certaines implémentations de l’alimentation de Windows Sockets sortir des informations de débogage si le **SO_DEBUG** option est définie par une application.  
  
 Les options suivantes sont prises en charge pour `SetSockOpt`. Le Type identifie le type de données adressées par `lpOptionValue`.  
  
|Valeur|Type|Signification|  
|-----------|----------|-------------|  
|**SO_BROADCAST**|**BOOL**|Autoriser la transmission de messages de diffusion sur le socket.|  
|**SO_DEBUG**|**BOOL**|Enregistrer les informations de débogage.|  
|**SO_DONTLINGER**|**BOOL**|Ne pas bloquer **fermer** en attente d’envoi des données non envoyées. Cette option est équivalente à la définition **SO_LINGER** avec **l_onoff** la valeur zéro.|  
|**SO_DONTROUTE**|**BOOL**|Ne pas acheminer : envoyer directement à l’interface.|  
|**SO_KEEPALIVE**|**BOOL**|Envoyer des connexions persistantes.|  
|**SO_LINGER**|**structure de maintien**|Attendre pendant la **fermer** si non envoyés donnée n’est présente.|  
|**SO_OOBINLINE**|**BOOL**|Recevoir des données de hors-bande dans le flux de données normal.|  
|**SO_RCVBUF**|`int`|Spécifiez reçoit de la taille de mémoire tampon pour.|  
|**SO_REUSEADDR**|**BOOL**|Autoriser le socket soit lié à une adresse qui est déjà en cours d’utilisation. (See [Bind](#bind).)|  
|**SO_SNDBUF**|`int`|Spécifiez la taille de mémoire tampon d’envoi.|  
|**TCP_NODELAY**|**BOOL**|Désactive l'algorithme Nagle pour la fusion des envois.|  
  
 Options de Distribution BSD (Berkeley Software) non pris en charge pour `SetSockOpt` sont :  
  
|Valeur|Type|Signification|  
|-----------|----------|-------------|  
|**SO_ACCEPTCONN**|**BOOL**|Écoute de socket|  
|**SO_ERROR**|`int`|Obtenir l’état d’erreur et l’effacer.|  
|**SO_RCVLOWAT**|`int`|Limite inférieure de la réception.|  
|**SO_RCVTIMEO**|`int`|Délai de réception|  
|**SO_SNDLOWAT**|`int`|Envoyer le seuil inférieur.|  
|**SO_SNDTIMEO**|`int`|Délai d’attente d’envoi.|  
|**SO_TYPE**|`int`|Type de socket.|  
|**IP_OPTIONS**||Définir le champ d’options dans l’en-tête IP.|  
  
##  <a name="shutdown"></a>CAsyncSocket::ShutDown  
 Appel de cette fonction membre pour désactiver envoie, reçoit, ou les deux sur le socket.  
  
```  
BOOL ShutDown(int nHow = sends);
```  
  
### <a name="parameters"></a>Paramètres  
 `nHow`  
 Un indicateur qui décrit les types d’opération sera n’est plus autorisé, à l’aide de valeurs énumérées suivantes :  
  
- **reçoit = 0**  
  
- **envoie = 1**  
  
- **à la fois = 2**  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; Sinon, 0 et un code d’erreur spécifique peuvent être récupéré en appelant [GetLastError](#getlasterror). Les erreurs suivantes s’appliquent à cette fonction membre :  
  
- **WSANOTINITIALISED** un bon [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) doit se produire avant d’utiliser cette API.  
  
- **WSAENETDOWN** implémentation des Sockets Windows l’a détecté que le sous-système réseau a échoué.  
  
- **WSAEINVAL** `nHow` n’est pas valide.  
  
- **Winsock** une opération de blocage Windows Sockets est en cours.  
  
- **WSAENOTCONN** le socket n’est pas connecté ( **SOCK_STREAM** uniquement).  
  
- **WSAENOTSOCK** le descripteur n’est pas un socket.  
  
### <a name="remarks"></a>Remarques  
 `ShutDown`est utilisé sur tous les types de sockets pour désactiver la réception, transmission ou les deux. Si `nHow` est 0, reçoit suivantes sur le socket est rejetée. Cela n’a aucun effet sur les couches de protocole inférieures.  
  
 Pour les protocoles TCP (Transmission Control), la fenêtre TCP n’est pas modifiée et les données entrantes seront acceptées (mais pas reconnues) jusqu'à ce que la fenêtre est épuisée. De protocole UDP (User Datagram), les datagrammes entrants sont acceptés et en file d’attente. En aucun cas un paquet ICMP d’erreur est généré. Si `nHow` est 1, les envois suivants ne sont pas autorisées. Pour les sockets TCP, un FIN est envoyé. Paramètre `nHow` 2 désactive les envois et réceptions tel que décrit ci-dessus.  
  
 Notez que `ShutDown` ne pas fermer le socket et les ressources liées à la prise ne seront pas libérées tant que **fermer** est appelée. Une application ne doit pas dépendre de la possibilité de réutiliser un socket après que qu’il a été arrêté. En particulier, une implémentation Windows Sockets n’est pas requis pour prendre en charge l’utilisation de **connecter** sur un socket de ce type.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CAsyncSocket::OnReceive](#onreceive).  
  
##  <a name="socket"></a>CASyncSocket::Socket  
 Alloue un handle de socket.  
  
```  
BOOL Socket(
    int nSocketType = SOCK_STREAM,  
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,  
    int nProtocolType = 0,  
    int nAddressFormat = PF_INET);
```  
  
### <a name="parameters"></a>Paramètres  
 `nSocketType`  
 Spécifie `SOCK_STREAM` ou `SOCK_DGRAM`.  
  
 `lEvent`  
 Masque de bits qui spécifie une combinaison d’événements réseau qui intéressent l’application.  
  
- `FD_READ`: Souhaite recevoir une notification de préparation pour la lecture.  
  
- `FD_WRITE`: Souhaite recevoir une notification de préparation pour l’écriture.  
  
- `FD_OOB`: Souhaite recevoir une notification de l’arrivée des données hors bande.  
  
- `FD_ACCEPT`: Souhaite recevoir une notification de connexions entrantes.  
  
- `FD_CONNECT`: Souhaite recevoir une notification de connexion terminée.  
  
- `FD_CLOSE`: Choisir de recevoir la notification de la fermeture du socket.  
  
 `nProtocolType`  
 Protocole à utiliser avec le socket qui est spécifique à la famille d’adresses indiquée.  
  
 `nAddressFormat`  
 Spécification de la famille d’adresses.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `TRUE` en cas de réussite, `FALSE` en cas d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode alloue un handle de socket. Il n’appelle pas [CAsyncSocket::Bind](#bind) de liaison du socket à une adresse spécifiée, vous devez appeler `Bind` ultérieurement à la liaison du socket à une adresse spécifiée. Vous pouvez utiliser [CAsyncSocket::SetSockOpt](#setsockopt) pour définir l’option de socket avant leur liaison.  
  
## <a name="see-also"></a>Voir aussi  
 [CObject (classe)](../../mfc/reference/cobject-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CSocket (classe)](../../mfc/reference/csocket-class.md)   
 [CSocketFile (classe)](../../mfc/reference/csocketfile-class.md)

