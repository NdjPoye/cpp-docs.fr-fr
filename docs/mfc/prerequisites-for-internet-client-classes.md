---
title: "Composants requis pour les classes clientes Internet | Microsoft Docs"
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
  - "classes (C++), connexions"
  - "connexions (C++), classes pour"
  - "fichiers (C++), lire"
  - "fichiers (C++), écrire dans"
  - "FTP (File Transfer Protocol), classes MFC"
  - "Gopher (applications clientes)"
  - "Gopher (composants requis)"
  - "HTTP, composants requis pour les clients Internet"
  - "Internet (C++), connexions"
  - "classe de client Internet (composants requis) (C++)"
  - "Fichiers Internet (C++), écrire dans"
  - "composants requis, classes de client Internet"
  - "URL (C++), Internet (applications clientes)"
ms.assetid: c51d1dfe-260c-4228-8100-e4efd90e9599
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Composants requis pour les classes clientes Internet
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Certaines actions effectuées par un client Internet \(la lecture d'un fichier, par exemple\) implique des actions nécessaires \(dans ce cas, l'établissement d'une connexion Internet\).  Les tableaux suivants répertorient les éléments requis pour certaines actions clientes.  
  
### URL Internet générale \(FTP, Gopher, ou HTTP\)  
  
|Action|Condition préalable|  
|------------|-------------------------|  
|Établir une connexion.|Créer une [CInternetSession](../mfc/reference/cinternetsession-class.md) pour générer la base d'une application cliente Internet.|  
|Ouvrir une URL.|Établir une connexion.  Appeler [CInternetSession::OpenURL](../Topic/CInternetSession::OpenURL.md).  La fonction `OpenURL` retourne un objet de ressource en lecture seule.|  
|Lire les données d'URL.|Ouvrir l'URL.  Appeler [CInternetFile::Read](../Topic/CInternetFile::Read.md).|  
|Définir une option Internet.|Établir une connexion.  Appeler [CInternetSession::SetOption](../Topic/CInternetSession::SetOption.md).|  
|Définir une fonction à appeler avec les informations d'état.|Établir une connexion.  Appeler [CInternetSession::EnableStatusCallback](../Topic/CInternetSession::EnableStatusCallback.md).  Redéfinir [CInternetSession::OnStatusCallback](../Topic/CInternetSession::OnStatusCallback.md) pour traiter des appels.|  
  
### FTP  
  
|Action|Condition préalable|  
|------------|-------------------------|  
|Établir une connexion FTP.|Créer [CInternetSession](../mfc/reference/cinternetsession-class.md) comme base de cette application cliente Internet.  Appeler [CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md) pour créer un objet [CFtpConnection](../mfc/reference/cftpconnection-class.md).|  
|Trouver la première ressource.|Établir une connexion FTP.  Créer un objet [CFtpFileFind](../mfc/reference/cftpfilefind-class.md).  Appeler [CFtpFileFind::FindFile](../Topic/CFtpFileFind::FindFile.md).|  
|Énumérer toutes les ressources disponibles.|trouver le premier fichier :  Appeler [CFtpFileFind::FindNextFile](../Topic/CFtpFileFind::FindNextFile.md) jusqu'à ce qu'il retourne FALSE.|  
|Ouvrir un fichier FTP.|Établir une connexion FTP.  Appeler [CFtpConnection::OpenFile](../Topic/CFtpConnection::OpenFile.md) pour créer et ouvrir un objet [CInternetFile](../mfc/reference/cinternetfile-class.md).|  
|Lire un fichier FTP.|Ouvrir un fichier FTP avec un accès en lecture.  Appeler [CInternetFile::Read](../Topic/CInternetFile::Read.md).|  
|Ecrire dans un fichier FTP|Ouvrir un fichier FTP avec accès en écriture.  Appeler [CInternetFile::Write](../Topic/CInternetFile::Write.md).|  
|Accéder au répertoire du client sur le serveur.|Établir une connexion FTP.  Appeler [CFtpConnection::SetCurrentDirectory](../Topic/CFtpConnection::SetCurrentDirectory.md).|  
|Récupérer le répertoire actif du client sur le serveur.|Établir une connexion FTP.  Appeler [CFtpConnection::GetCurrentDirectory](../Topic/CFtpConnection::GetCurrentDirectory.md).|  
  
### HTTP  
  
|Action|Condition préalable|  
|------------|-------------------------|  
|Établir une connexion HTTP.|Créer [CInternetSession](../mfc/reference/cinternetsession-class.md) comme base de cette application cliente Internet.  Appeler [CInternetSession::GetHttpConnection](../Topic/CInternetSession::GetHttpConnection.md) pour créer un objet [CHttpConnection](../mfc/reference/chttpconnection-class.md).|  
|Ouvrir un fichier HTTP.|Établir une connexion HTTP.  Appeler [CHttpConnection::OpenRequest](../Topic/CHttpConnection::OpenRequest.md) pour créer un objet [CHttpFile](../mfc/reference/chttpfile-class.md).  Appeler [CHttpFile::AddRequestHeaders](../Topic/CHttpFile::AddRequestHeaders.md).  Appeler [CHttpFile::SendRequest](../Topic/CHttpFile::SendRequest.md).|  
|Lire un fichier HTTP.|Ouvrir un fichier HTTP.  Appeler [CInternetFile::Read](../Topic/CInternetFile::Read.md).|  
|Obtenir des informations sur un requête HTTP.|Établir une connexion HTTP.  Appeler [CHttpConnection::OpenRequest](../Topic/CHttpConnection::OpenRequest.md) pour créer un objet [CHttpFile](../mfc/reference/chttpfile-class.md).  Appeler [CHttpFile::QueryInfo](../Topic/CHttpFile::QueryInfo.md).|  
  
### gopher  
  
|Action|Condition préalable|  
|------------|-------------------------|  
|Créez une connexion de Gopher.|Créer [CInternetSession](../mfc/reference/cinternetsession-class.md) comme base de cette application cliente Internet.  Appeler [CInternetSession::GetGopherConnection](../Topic/CInternetSession::GetGopherConnection.md) pour créer [CGopherConnection](../mfc/reference/cgopherconnection-class.md).|  
|Recherchez le premier fichier dans le répertoire en cours.|Créez une connexion de Gopher.  Créer un objet [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md).  Appeler [CGopherConnection::CreateLocator](../Topic/CGopherConnection::CreateLocator.md) pour créer un objet [CGopherLocator](../mfc/reference/cgopherlocator-class.md).  Passer le localisateur pointe vers [CGopherFileFind::FindFile](../Topic/CGopherFileFind::FindFile.md).  Appeler [CGopherFileFind::GetLocator](../Topic/CGopherFileFind::GetLocator.md) pour obtenir le localisateur d'un fichier si vous avez besoin d'utiliser ultérieurement.|  
|Enumérer tous les fichiers disponibles.|Trouver le premier fichier :  Appeler [CGopherFileFind::FindNextFile](../Topic/CGopherFileFind::FindNextFile.md) jusqu'à ce qu'il retourne FALSE.|  
|Ouvrir un fichier gopher|Créez une connexion de Gopher.  Créer un localisateur de Gopher avec [CGopherConnection::CreateLocator](../Topic/CGopherConnection::CreateLocator.md) ou recherchez un localisateur de [CGopherFileFind::GetLocator](../Topic/CGopherFileFind::GetLocator.md).  Appeler [CGopherConnection::OpenFile](../Topic/CGopherConnection::OpenFile.md).|  
|Lire un fichier de Gopher.|Ouvrir un fichier gopher  Utiliser [CGopherFile](../mfc/reference/cgopherfile-class.md).|  
  
## Voir aussi  
 [Extension Internet Win32 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Classes MFC pour la création d'applications clientes Internet](../mfc/mfc-classes-for-creating-internet-client-applications.md)   
 [Écriture d'une application cliente Internet en utilisant des classes WinInet MFC](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)