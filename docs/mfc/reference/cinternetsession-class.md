---
title: "CInternetSession Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CInternetSession"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInternetSession class"
  - "Internet sessions"
ms.assetid: ef54feb4-9d0f-4e65-a45d-7a4cf6c40e51
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CInternetSession Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée et initialise les sessions unique ou plusieurs simultanées Internet et, si nécessaire, décrit la connexion à un serveur proxy.  
  
## Syntaxe  
  
```  
class CInternetSession : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CInternetSession::CInternetSession](../Topic/CInternetSession::CInternetSession.md)|Construit un objet `CInternetSession`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CInternetSession::Close](../Topic/CInternetSession::Close.md)|Ferme la connexion Internet lorsque la session d'Internet est terminée.|  
|[CInternetSession::EnableStatusCallback](../Topic/CInternetSession::EnableStatusCallback.md)|Génère une routine de rappel d'état.|  
|[CInternetSession::GetContext](../Topic/CInternetSession::GetContext.md)|Ferme la connexion Internet lorsque la session d'Internet est terminée.|  
|[CInternetSession::GetCookie](../Topic/CInternetSession::GetCookie.md)|Cookies de retour pour l'URL spécifiée et tous son parent URL.|  
|[CInternetSession::GetCookieLength](../Topic/CInternetSession::GetCookieLength.md)|Extrait la variable spécifiant la longueur du cookie stocké dans la mémoire tampon.|  
|[CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md)|Ouvre une session FTP avec un serveur.  Se connecte l'utilisateur.|  
|[CInternetSession::GetGopherConnection](../Topic/CInternetSession::GetGopherConnection.md)|Ouvre un serveur Gopher pour une application essaie d'ouvrir une connexion.|  
|[CInternetSession::GetHttpConnection](../Topic/CInternetSession::GetHttpConnection.md)|Ouvre un serveur HTTP pour une application essaie d'ouvrir une connexion.|  
|[CInternetSession::OnStatusCallback](../Topic/CInternetSession::OnStatusCallback.md)|Met à jour l'état d'une exécution lorsque le rappel d'état est activé.|  
|[CInternetSession::OpenURL](../Topic/CInternetSession::OpenURL.md)|Analyse et ouvre une URL.|  
|[CInternetSession::SetCookie](../Topic/CInternetSession::SetCookie.md)|Définit un cookie pour l'URL spécifiée.|  
|[CInternetSession::SetOption](../Topic/CInternetSession::SetOption.md)|Définit des options pour la session d'Internet.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CInternetSession::operator HINTERNET](../Topic/CInternetSession::operator%20HINTERNET.md)|Un handle à la session active Internet.|  
  
## Notes  
 Si votre connexion Internet doit être mise à jour pour la durée d'une application, vous pouvez créer un membre d' `CInternetSession` de la classe [CWinApp](../../mfc/reference/cwinapp-class.md).  
  
 Une fois que vous avez établi une connexion Internet, vous pouvez appeler [OpenURL](../Topic/CInternetSession::OpenURL.md).  `CInternetSession` analyse l'URL pour vous en appelant la fonction globale [AfxParseURL](../Topic/AfxParseURL.md).  Indépendamment de son type de fournisseur, `CInternetSession` interprète l'URL et le gère automatiquement.  Il peut traiter des demandes de fichiers locaux marqués avec la ressource « file:\/\/ » en URL.  `OpenURL` retourne un pointeur vers un objet de [CStdioFile](../../mfc/reference/cstdiofile-class.md) si le nom que vous le passez est un fichier local.  
  
 Si vous ouvrez une URL sur un serveur Web à l'aide de `OpenURL`, vous pouvez lire les informations du site.  Si vous souhaitez exécuter des actions de service particulier \(par exemple, HTTP, FTP, ou Gopher\) sur les fichiers situés sur un serveur, vous devez établir la connexion correcte avec ce serveur.  Pour ouvrir un type particulier de connexion directement à un service particulier, utilisez l'une des fonctions membres suivantes :  
  
-   [GetGopherConnection](../Topic/CInternetSession::GetGopherConnection.md) pour ouvrir une pièce jointe à un service de Gopher.  
  
-   [GetHttpConnection](../Topic/CInternetSession::GetHttpConnection.md) pour ouvrir une pièce jointe à un service HTTP.  
  
-   [GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md) pour ouvrir une pièce jointe à un service FTP.  
  
 [SetOption](../Topic/CInternetSession::SetOption.md) vous permet de définir les options de requête de votre session, telles que les valeurs du délai d'attente, numéro de relances, et ainsi de suite.  
  
 Les fonctions membres d'`CInternetSession`[SetCookie](../Topic/CInternetSession::SetCookie.md), [GetCookie](../Topic/CInternetSession::GetCookie.md), et [GetCookieLength](../Topic/CInternetSession::GetCookieLength.md) fournissent les moyens de gérer une base de données de cookie Win32, via lequel les serveurs et les scripts mettent à jour les informations d'état à propos de la station de travail clientes.  
  
 Pour plus d'informations sur les tâches de base de programmation Internet, consultez l'article [Premières étapes Internet : WinInet](../../mfc/wininet-basics.md).  Pour plus d'informations sur l'utilisation des classes WinInet MFC, consultez l'article [Programmation avec Internet WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
> [!NOTE]
>  `CInternetSession` lève [AfxThrowNotSupportedException](../Topic/AfxThrowNotSupportedException.md) pour les types de services non pris en charge.  Seuls les types de services suivants sont actuellement pris en charge : FTP, HTTP, Gopher, puis fichier.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CInternetSession`  
  
## Configuration requise  
 **Header:** afxinet.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CInternetConnection Class](../../mfc/reference/cinternetconnection-class.md)   
 [CHttpConnection Class](../../mfc/reference/chttpconnection-class.md)   
 [CFtpConnection Class](../../mfc/reference/cftpconnection-class.md)   
 [CGopherConnection Class](../../mfc/reference/cgopherconnection-class.md)