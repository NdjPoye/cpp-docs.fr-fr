---
title: "CHttpConnection Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CHttpConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHttpConnection class"
  - "connecter à des serveurs"
  - "connecter à des serveurs, serveurs HTTP"
  - "connexions (C++), HTTP"
  - "HTTP (connexions)"
  - "serveurs HTTP, connecter à"
  - "Internet connections, HTTP"
  - "Internet protocols"
  - "Internet protocols, HTTP"
  - "Internet server, HTTP"
  - "protocols, HTTP"
  - "serveurs, connecter à"
ms.assetid: a402b662-c445-4988-800d-c8278551babe
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CHttpConnection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gère la connexion à un serveur HTTP.  
  
## Syntaxe  
  
```  
class CHttpConnection : public CInternetConnection  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CHttpConnection::CHttpConnection](../Topic/CHttpConnection::CHttpConnection.md)|Crée un objet `CHttpConnection`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CHttpConnection::OpenRequest](../Topic/CHttpConnection::OpenRequest.md)|Ouvre une requête HTTP.|  
  
## Notes  
 HTTP est l'un des trois protocoles de serveur Web implémentés par les classes WinInet MFC.  
  
 La classe `CHttpConnection` contient un constructeur et une fonction membre, [OpenRequest](../Topic/CHttpConnection::OpenRequest.md), qui gère les connexions à un serveur avec un protocole HTTP.  
  
 Pour communiquer avec un serveur HTTP, vous devez d'abord créer une instance de [CInternetSession](../../mfc/reference/cinternetsession-class.md), puis créez un objet de [CHttpConnection](#_mfc_chttpconnection) .  Vous ne créez jamais directement un objet d' `CHttpConnection` ; au contraire, appelez [CInternetSession::GetHttpConnection](../Topic/CInternetSession::GetHttpConnection.md), qui crée l'objet d' `CHttpConnection` et retourne un pointeur vers elle.  
  
 Pour en savoir plus sur la façon dont `CHttpConnection` fonctionne avec les autres classes Internet MFC, consultez l'article [Programmation avec Internet WinInet](../../mfc/win32-internet-extensions-wininet.md).  Pour plus d'informations sur la connexion aux serveurs à l'aide de les deux autres protocoles Internet pris en charge, le Gopher et FTP, consultez les classes [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) et [CFtpConnection](../../mfc/reference/cftpconnection-class.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CHttpConnection`  
  
## Configuration requise  
 **Header:** afxinet.h  
  
## Voir aussi  
 [CInternetConnection Class](../../mfc/reference/cinternetconnection-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CInternetConnection Class](../../mfc/reference/cinternetconnection-class.md)   
 [CHttpFile Class](../../mfc/reference/chttpfile-class.md)