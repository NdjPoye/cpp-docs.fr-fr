---
title: "CInternetConnection Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CInternetConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "asynchronous connections"
  - "CInternetConnection class"
  - "Internet connections"
ms.assetid: 62a5d1c3-8471-4e36-a064-48831829b2a7
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CInternetConnection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gère la connexion à un serveur Web.  
  
## Syntaxe  
  
```  
class CInternetConnection : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CInternetConnection::CInternetConnection](../Topic/CInternetConnection::CInternetConnection.md)|Construit un objet `CInternetConnection`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CInternetConnection::GetContext](../Topic/CInternetConnection::GetContext.md)|Obtient l'ID de contexte pour cet objet de Connexion.|  
|[CInternetConnection::GetServerName](../Topic/CInternetConnection::GetServerName.md)|Obtient le nom du serveur associé à la connexion.|  
|[CInternetConnection::GetSession](../Topic/CInternetConnection::GetSession.md)|Obtient un pointeur vers l'objet de [CInternetSession](../../mfc/reference/cinternetsession-class.md) associé à la connexion.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CInternetConnection::operator HINTERNET](../Topic/CInternetConnection::operator%20HINTERNET.md)|Un handle à une session Internet.|  
  
## Notes  
 C'est la classe de base pour les classes MFC [CFtpConnection](../../mfc/reference/cftpconnection-class.md), [CHttpConnection](../../mfc/reference/chttpconnection-class.md), et [CGopherConnection](../../mfc/reference/cgopherconnection-class.md).  Chacune de ces classes fournit des fonctionnalités supplémentaires pour communiquer avec le serveur FTP respectifs, HTTP, ou le serveur Gopher.  
  
 Pour communiquer directement avec un serveur Web, vous devez disposer d'un objet de [CInternetSession](../../mfc/reference/cinternetsession-class.md) et un objet d' `CInternetConnection` .  
  
 Pour en savoir plus sur la façon dont les classes WinInet fonctionnent, consultez l'article [Programmation avec Internet WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CInternetConnection`  
  
## Configuration requise  
 **Header:** afxinet.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)