---
title: "CGopherConnection Class | Microsoft Docs"
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
  - "CGopherConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CGopherConnection class"
  - "connecter à des serveurs"
  - "connecter à des serveurs, gopher servers"
  - "protocole gopher"
  - "gopher server"
  - "Internet connections, gopher"
  - "Internet server, gopher"
  - "protocols, gopher"
  - "serveurs, connecter à"
  - "services, gopher"
ms.assetid: b5b96aea-ac99-430e-bd84-d1372b43f78f
caps.latest.revision: 21
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CGopherConnection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gère la connexion à un serveur Web de Gopher.  
  
> [!NOTE]
>  Les classes `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` et leurs membres ont été déconseillées car elles ne fonctionnent pas à la plateforme Windows XP, mais ils continueront à travailler sur les plateformes antérieures.  
  
## Syntaxe  
  
```  
class CGopherConnection : public CInternetConnection  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CGopherConnection::CGopherConnection](../Topic/CGopherConnection::CGopherConnection.md)|Construit un objet `CGopherConnection`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CGopherConnection::CreateLocator](../Topic/CGopherConnection::CreateLocator.md)|Crée un objet de [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) pour rechercher des fichiers sur un serveur Gopher.|  
|[CGopherConnection::GetAttribute](../Topic/CGopherConnection::GetAttribute.md)|Récupère des informations d'attribut sur l'objet de Gopher.|  
|[CGopherConnection::OpenFile](../Topic/CGopherConnection::OpenFile.md)|Ouvre un fichier de Gopher.|  
  
## Notes  
 Le service de Gopher est l'un des trois services Internet identifiés par les classes WinInet MFC.  
  
 La classe `CGopherConnection` contient un constructeur et trois fonctions membres supplémentaires qui gèrent le service de Gopher : [OpenFile](../Topic/CGopherConnection::OpenFile.md), [CreateLocator](../Topic/CGopherConnection::CreateLocator.md), et [GetAttribute](../Topic/CGopherConnection::GetAttribute.md).  
  
 Pour communiquer avec un serveur Web de Gopher, vous devez d'abord créer une instance de [CInternetSession](../../mfc/reference/cinternetsession-class.md), puis appelez [CInternetSession::GetGopherConnection](../Topic/CInternetSession::GetGopherConnection.md), qui crée l'objet d' `CGopherConnection` et retourne un pointeur vers elle.  Vous ne créez jamais directement un objet d' `CGopherConnection` .  
  
 Pour en savoir plus sur la façon dont `CGopherConnection` fonctionne avec les autres classes Internet MFC, consultez l'article [Programmation avec Internet WinInet](../../mfc/win32-internet-extensions-wininet.md).  Pour plus d'informations sur l'utilisation des deux autres services Internet pris en charge, FTP et HTTP consultez les classes [CHttpConnection](../../mfc/reference/chttpconnection-class.md) et [CFtpConnection](../../mfc/reference/cftpconnection-class.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CGopherConnection`  
  
## Configuration requise  
 **Header:** afxinet.h  
  
## Voir aussi  
 [CInternetConnection Class](../../mfc/reference/cinternetconnection-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CFtpConnection Class](../../mfc/reference/cftpconnection-class.md)   
 [CHttpConnection Class](../../mfc/reference/chttpconnection-class.md)   
 [CInternetConnection Class](../../mfc/reference/cinternetconnection-class.md)   
 [CGopherLocator Class](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFile Class](../../mfc/reference/cgopherfile-class.md)   
 [CInternetSession Class](../../mfc/reference/cinternetsession-class.md)