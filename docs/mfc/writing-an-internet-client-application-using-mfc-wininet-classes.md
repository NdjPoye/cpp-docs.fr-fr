---
title: "&#201;criture d&#39;une application cliente Internet en utilisant des classes WinInet MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "applications Internet, applications clientes"
  - "applications Internet, WinInet"
  - "Internet (applications clientes)"
  - "Internet (applications clientes), écrire"
  - "MFC, applications Internet"
  - "classes WinInet, programmation"
ms.assetid: a2c4a40c-a94e-4b3e-9dbf-f8a8dc8e5428
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &#201;criture d&#39;une application cliente Internet en utilisant des classes WinInet MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les bases de chaque application client Internet est la session Internet.  MFC implémente les sessions Internet en tant qu'objets de classe [CISessioninternet](../mfc/reference/cinternetsession-class.md).  En utilisant cette classe, vous pouvez créer une connexion Internet ou plusieurs sessions simultanées.  
  
 Pour communiquer avec un serveur, vous avez besoin d'un objet de [CConnexioninternet](../mfc/reference/cinternetconnection-class.md) ainsi que `CInternetSession`.  Vous pouvez créer `CInternetConnection` à l'aide de [CSessionInternet::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md), de [CSessionInternet::GetHttpConnection](../Topic/CInternetSession::GetHttpConnection.md), ou de [CSessionInternet::GetGopherConnection](../Topic/CInternetSession::GetGopherConnection.md).  Chacun de ces appels est spécifique au type de protocole.  Ces appels n'ouvrent pas un fichier sur le serveur pour lire ou écrire.  Si vous avez l'intention de lire ou d'écrire des données, vous devez ouvrir le fichier en tant qu'étape distincte.  
  
 Pour la plupart des sessions Internet, les travaux de `CInternetSession` vont de pair avec un objet de [CFichierInternet](../mfc/reference/cinternetfile-class.md):  
  
-   Pour une connexion Internet, vous devez créer une instance de [CSessionInternet](../mfc/reference/cinternetsession-class.md).  
  
-   Si votre session Internet lit et écrit des données, vous devez créer une instance de `CInternetFile` \(ou les sous\-classes, [CHttpFile](../mfc/reference/chttpfile-class.md) ou [CGopherFile](../mfc/reference/cgopherfile-class.md)\).  La méthode la plus simple pour lire des données consiste à appeler [CSessionInternetSession::OpenURL](../Topic/CInternetSession::OpenURL.md).  Cette fonction analyse un localisateur \(URL\) de ressource universel fourni par vous, ouvre une connexion au serveur spécifié par l'URL, et retourne un objet en lecture seule de `CInternetFile`.  `CInternetSession::OpenURL` n'est pas spécifique à un type de protocole — les mêmes travaux d'appel pour un serveur, protocole HTTP, ou l'URL de Gopher.  Travaux de `CInternetSession::OpenURL` avec les fichiers locaux \(retourne `CStdioFile` au lieu de `CInternetFile`\).  
  
-   Si votre session Internet ne lit la pas ou n'écrit pas les données, mais effectue d'autres tâches, telles que la suppression d'un fichier dans un répertoire FTP, vous pouvez ne pas avoir à créer une instance de `CInternetFile`.  
  
 Il existe deux manières de créer un objet de `CInternetFile`:  
  
-   Si vous utilisez `CInternetSession::OpenURL` pour établir la connexion au serveur, l'appel à `OpenURL` retourne `CStdioFile`.  
  
-   Si l'utilisation **CSessionInternet::ObtenirConnexionFtp**, `GetGopherConnection`, ou `GetHttpConnection` d'établir la connexion au serveur, vous devez appeler `CFtpConnection::OpenFile`, `CGopherConnection::OpenFile`, ou **CHttpConnection::OpenRequest,** respectivement, pour retourner `CInternetFile`, `CGopherFile`, ou `CHttpFile`, respectivement.  
  
 Les étapes pour implémenter une application cliente Internet varient selon que vous créez un client générique Internet selon **OpenURL** ou un client spécifique au protocole utilisant l'une des fonctions de **ObtenirConnexion**.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Comment écrire une application cliente Internet qui fonctionne génériquement avec FTP, le protocole HTTP, et le Gopher ?](../mfc/steps-in-a-typical-internet-client-application.md)  
  
-   [Comment écrire une application cliente FTP qui ouvre un fichier ?](../mfc/steps-in-a-typical-ftp-client-application.md)  
  
-   [Comment écrire une application cliente FTP qui n'ouvre pas un fichier mais effectue une opération de répertoire, telle que la suppression d'un fichier ?](../mfc/steps-in-a-typical-ftp-client-application-to-delete-a-file.md)  
  
-   [Comment écrire une application cliente de Gopher ?](../mfc/steps-in-a-typical-gopher-client-application.md)  
  
-   [Comment écrire une application cliente HTTP ?](../mfc/steps-in-a-typical-http-client-application.md)  
  
## Voir aussi  
 [Extension Internet Win32 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Classes MFC pour la création d'applications clientes Internet](../mfc/mfc-classes-for-creating-internet-client-applications.md)   
 [Composants requis pour les classes clientes Internet](../mfc/prerequisites-for-internet-client-classes.md)