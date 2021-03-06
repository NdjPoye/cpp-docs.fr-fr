---
title: Conditions préalables pour les Classes clientes Internet | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Internet files [MFC], writing to
- Internet [MFC], connections
- FTP (File Transfer Protocol), MFC classes
- Gopher prerequisites [MFC]
- files [MFC], writing to
- classes [MFC], connections
- HTTP [MFC], prerequisites for Internet clients
- connections [MFC], classes for
- Internet client class prerequisites [MFC]
- files [MFC], reading
- URLs [MFC], Internet client applications
- prerequisites, Internet client classes [MFC]
- Gopher client applications [MFC]
ms.assetid: c51d1dfe-260c-4228-8100-e4efd90e9599
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6c16c3658ee5d27def4892997c50115dc0b8831
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="prerequisites-for-internet-client-classes"></a>Composants requis pour les classes clientes Internet
Certaines actions effectuées par un client Internet (lecture d’un fichier, par exemple) ont des actions préalables (dans ce cas, l’établissement d’une connexion Internet). Les tableaux suivants répertorient les conditions préalables pour certaines actions client.  
  
### <a name="general-internet-url-ftp-gopher-or-http"></a>URL Internet en général (FTP, Gopher ou HTTP)  
  
|Action|Prérequis|  
|------------|------------------|  
|Établir une connexion.|Créer un [CInternetSession](../mfc/reference/cinternetsession-class.md) à base d’une application cliente Internet.|  
|Ouvrez une URL.|Établir une connexion. Appelez [CInternetSession::OpenURL](../mfc/reference/cinternetsession-class.md#openurl). Le `OpenURL` fonction retourne un objet de ressource en lecture seule.|  
|Données de l’URL de la lecture.|Ouvrir l’URL. Appelez [CInternetFile::Read](../mfc/reference/cinternetfile-class.md#read).|  
|Définir une option Internet.|Établir une connexion. Appelez [CInternetSession::SetOption](../mfc/reference/cinternetsession-class.md#setoption).|  
|Définir une fonction à appeler avec les informations d’état.|Établir une connexion. Appelez [CInternetSession::EnableStatusCallback](../mfc/reference/cinternetsession-class.md#enablestatuscallback). Substituer [CInternetSession::OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) pour traiter des appels.|  
  
### <a name="ftp"></a>FTP  
  
|Action|Composants requis|  
|------------|------------------|  
|Établir une connexion FTP.|Créer un [CInternetSession](../mfc/reference/cinternetsession-class.md) comme base de cette application cliente Internet. Appelez [CInternetSession::GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection) pour créer un [CFtpConnection](../mfc/reference/cftpconnection-class.md) objet.|  
|Rechercher la première ressource.|Établir une connexion FTP. Créer un [CFtpFileFind](../mfc/reference/cftpfilefind-class.md) objet. Appelez [CFtpFileFind::FindFile](../mfc/reference/cftpfilefind-class.md#findfile).|  
|Énumérer toutes les ressources disponibles.|Rechercher le premier fichier. Appelez [CFtpFileFind::FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile) jusqu'à ce qu’elle retourne FALSE.|  
|Ouvrir un fichier FTP.|Établir une connexion FTP. Appelez [CFtpConnection::OpenFile](../mfc/reference/cftpconnection-class.md#openfile) pour créer et ouvrir un [CInternetFile](../mfc/reference/cinternetfile-class.md) objet.|  
|Lire un fichier FTP.|Ouvrir un fichier FTP avec accès en lecture. Appelez [CInternetFile::Read](../mfc/reference/cinternetfile-class.md#read).|  
|Écrire dans un fichier FTP.|Ouvrir un fichier FTP avec accès en écriture. Appelez [CInternetFile::Write](../mfc/reference/cinternetfile-class.md#write).|  
|Modifiez le répertoire client sur le serveur.|Établir une connexion FTP. Appelez [CFtpConnection::SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory).|  
|Récupérer le répertoire du client en cours sur le serveur.|Établir une connexion FTP. Appelez [CFtpConnection::GetCurrentDirectory](../mfc/reference/cftpconnection-class.md#getcurrentdirectory).|  
  
### <a name="http"></a>HTTP  
  
|Action|Prérequis|  
|------------|------------------|  
|Établir une connexion HTTP.|Créer un [CInternetSession](../mfc/reference/cinternetsession-class.md) comme base de cette application cliente Internet. Appelez [CInternetSession::GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection) pour créer un [objet CHttpConnection](../mfc/reference/chttpconnection-class.md) objet.|  
|Ouvrir un fichier HTTP.|Établir une connexion HTTP. Appelez [CHttpConnection::OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest) pour créer un [CHttpFile](../mfc/reference/chttpfile-class.md) objet. Appelez [CHttpFile::AddRequestHeaders](../mfc/reference/chttpfile-class.md#addrequestheaders). Appelez [CHttpFile::SendRequest](../mfc/reference/chttpfile-class.md#sendrequest).|  
|Lire un fichier HTTP.|Ouvrir un fichier HTTP. Appelez [CInternetFile::Read](../mfc/reference/cinternetfile-class.md#read).|  
|Obtenir des informations concernant une requête HTTP.|Établir une connexion HTTP. Appelez [CHttpConnection::OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest) pour créer un [CHttpFile](../mfc/reference/chttpfile-class.md) objet. Appelez [CHttpFile::QueryInfo](../mfc/reference/chttpfile-class.md#queryinfo).|  
  
### <a name="gopher"></a>Gopher  
  
|Action|Prérequis|  
|------------|------------------|  
|Établir une connexion gopher.|Créer un [CInternetSession](../mfc/reference/cinternetsession-class.md) comme base de cette application cliente Internet. Appelez [CInternetSession::GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection) pour créer un [objet CGopherConnection](../mfc/reference/cgopherconnection-class.md).|  
|Rechercher le premier fichier dans le répertoire actif.|Établir une connexion gopher. Créer un [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md) objet. Appelez [CGopherConnection::CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator) pour créer un [objet CGopherLocator](../mfc/reference/cgopherlocator-class.md) objet. Passez le localisateur à [CGopherFileFind::FindFile](../mfc/reference/cgopherfilefind-class.md#findfile). Appelez [CGopherFileFind::GetLocator](../mfc/reference/cgopherfilefind-class.md#getlocator) pour obtenir l’adresse d’un fichier si vous avez besoin plus tard.|  
|Énumérer tous les fichiers disponibles.|Rechercher le premier fichier. Appelez [CGopherFileFind::FindNextFile](../mfc/reference/cgopherfilefind-class.md#findnextfile) jusqu'à ce qu’elle retourne FALSE.|  
|Ouvrez un fichier gopher.|Établir une connexion gopher. Créer un localisateur gopher avec [CGopherConnection::CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator) ou trouver un localisateur avec [CGopherFileFind::GetLocator](../mfc/reference/cgopherfilefind-class.md#getlocator). Appelez [CGopherConnection::OpenFile](../mfc/reference/cgopherconnection-class.md#openfile).|  
|Lire un fichier gopher.|Ouvrez un fichier gopher. Utilisez [CGopherFile](../mfc/reference/cgopherfile-class.md).|  
  
## <a name="see-also"></a>Voir aussi  
 [Extension Internet Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [Classes MFC pour la création d’Applications clientes Internet](../mfc/mfc-classes-for-creating-internet-client-applications.md)   
 [Écriture d’une application cliente Internet en utilisant des classes WinInet MFC](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
