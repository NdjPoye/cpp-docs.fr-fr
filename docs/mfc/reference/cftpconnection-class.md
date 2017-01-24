---
title: "CFtpConnection Class | Microsoft Docs"
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
  - "CFtpConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFtpConnection class"
  - "FTP (File Transfer Protocol), établir des connexions"
  - "Internet connections, FTP"
  - "Internet services, FTP"
ms.assetid: 5e3a0501-8893-49cf-a3d5-0628d8d6b936
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFtpConnection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gère la connexion FTP sur un serveur Web et permet la manipulation directe des dossiers et des fichiers sur ce serveur.  
  
## Syntaxe  
  
```  
class CFtpConnection : public CInternetConnection  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CFtpConnection::CFtpConnection](../Topic/CFtpConnection::CFtpConnection.md)|Construit un objet `CFtpConnection`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFtpConnection::Command](../Topic/CFtpConnection::Command.md)|Envoie une commande directement à un serveur FTP.|  
|[CFtpConnection::CreateDirectory](../Topic/CFtpConnection::CreateDirectory.md)|Crée un dossier sur le serveur.|  
|[CFtpConnection::GetCurrentDirectory](../Topic/CFtpConnection::GetCurrentDirectory.md)|Obtient le répertoire actif pour cette connexion.|  
|[CFtpConnection::GetCurrentDirectoryAsURL](../Topic/CFtpConnection::GetCurrentDirectoryAsURL.md)|Obtient le répertoire actif pour cette connexion comme URL.|  
|[CFtpConnection::GetFile](../Topic/CFtpConnection::GetFile.md)|Obtient un fichier de serveur connecté|  
|[CFtpConnection::OpenFile](../Topic/CFtpConnection::OpenFile.md)|Ouvre un fichier sur le serveur connecté.|  
|[CFtpConnection::PutFile](../Topic/CFtpConnection::PutFile.md)|Définit un fichier sur le serveur.|  
|[CFtpConnection::Remove](../Topic/CFtpConnection::Remove.md)|Supprime un fichier du serveur.|  
|[CFtpConnection::RemoveDirectory](../Topic/CFtpConnection::RemoveDirectory.md)|Supprime le répertoire spécifié du serveur.|  
|[CFtpConnection::Rename](../Topic/CFtpConnection::Rename.md)|Renomme un fichier sur le serveur.|  
|[CFtpConnection::SetCurrentDirectory](../Topic/CFtpConnection::SetCurrentDirectory.md)|Définit le dossier actif FTP.|  
  
## Notes  
 FTP est l'un des trois services Internet identifiés par les classes WinInet MFC.  
  
 Pour communiquer avec un serveur Web FTP, vous devez d'abord créer une instance de [CInternetSession](../../mfc/reference/cinternetsession-class.md), puis créez un objet d' `CFtpConnection` .  Vous ne créez jamais directement un objet d' `CFtpConnection` ; au contraire, appelez [CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md), qui crée l'objet d' `CFtpConnection` et retourne un pointeur vers elle.  
  
 Pour en savoir plus sur la façon dont `CFtpConnection` fonctionne avec les autres classes Internet MFC, consultez l'article [Programmation avec Internet WinInet](../../mfc/win32-internet-extensions-wininet.md).  Pour plus d'informations sur la communication avec les deux autres services en charge, HTTP et le Gopher, consultez les classes [CHttpConnection](../../mfc/reference/chttpconnection-class.md) et [CGopherConnection](../../mfc/reference/cgopherconnection-class.md).  
  
## Exemple  
 Consultez l'exemple de la vue d'ensemble de la classe de [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) .  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CFtpConnection`  
  
## Configuration requise  
 **Header:** afxinet.h  
  
## Voir aussi  
 [CInternetConnection Class](../../mfc/reference/cinternetconnection-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CInternetConnection Class](../../mfc/reference/cinternetconnection-class.md)   
 [CInternetSession Class](../../mfc/reference/cinternetsession-class.md)