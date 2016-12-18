---
title: "&#201;tapes dans une application cliente FTP classique | Microsoft Docs"
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
  - "FTP (File Transfer Protocol)"
  - "FTP (File Transfer Protocol), applications clientes"
  - "applications Internet, applications clientes FTP"
  - "Internet (applications clientes), table FTP"
  - "classes WinInet, FTP"
ms.assetid: 70bed7b5-6040-40d1-bc77-702e63a698f2
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &#201;tapes dans une application cliente FTP classique
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une application cliente \(généralement [CInternetSession](../mfc/reference/cinternetsession-class.md) et crée un objet [CFtpConnection](../mfc/reference/cftpconnection-class.md).  Notez que ces classes WinInet MFC ne contrôle pas réellement les paramètres du type de proxy ; IIS est.  
  
 En outre, consultez les articles de la Base de connaissances :  
  
-   HOWTO : FTP avec le proxy CERN\- sur l'utilisation de l'API de WinInet \(ID d'article : Q166961\)  
  
-   APERÇU : FTP avec le proxy protégé par mot de passe CERN\- sur \(ID d'article : Q216214\)  
  
-   Le gestionnaire des services Internet n'affiche pas les services installés de proxy \(ID d'article : Q216802\)  
  
 Le tableau suivant montre les étapes que vous pouvez effectuer dans une application cliente FTP standard.  
  
|Votre objectif|Mesures que vous prenez|Effets|  
|--------------------|-----------------------------|------------|  
|Démarrez une session FTP.|Créez un objet [CInternetSession](../mfc/reference/cinternetsession-class.md).|Initialise WinInet et se connecte au serveur.|  
|Connectez vous à un serveur FTP.|Utilisez [CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md).|Retourne un objet [CFtpConnection](../mfc/reference/cftpconnection-class.md).|  
|Accédez à un nouveau répertoire FTP sur le serveur.|Utilisez [CFtpConnection::SetCurrentDirectory](../Topic/CFtpConnection::SetCurrentDirectory.md).|Modifie le répertoire auquel vous êtes connecté sur le serveur.|  
|Recherchez le premier fichier dans le répertoire FTP.|Utilisez [CFtpFileFind::FindFile](../Topic/CFtpFileFind::FindFile.md).|Recherche le premier fichier.  Retourne FALSE si aucun fichier n'est trouvé.|  
|Recherchez le premier fichier dans le répertoire FTP.|Utilisez [CFtpFileFind::FindNextFile](../Topic/CFtpFileFind::FindNextFile.md).|Recherche le fichier suivant.  Retourne FALSE si le fichier est introuvable.|  
|Ouvrez le fichier recherché par **FindFile** ou `FindNextFile` pour lire ou écrire.|Utilisez [CFtpConnection::OpenFile](../Topic/CFtpConnection::OpenFile.md), avec le nom de fichier renvoyé par [FindFile](../Topic/CFtpFileFind::FindFile.md) ou [FindNextFile](../Topic/CFtpFileFind::FindNextFile.md).|Supprime le fichier sur le serveur pour lire ou écrire.  Retourne la longueur d'un objet [CInternetFile](../mfc/reference/cinternetfile-class.md).|  
|Lire ou écrire dans le fichier.|Utilisez [CInternetFile::Read](../Topic/CInternetFile::Read.md) ou [CInternetFile::Write](../Topic/CInternetFile::Write.md).|Lit le nombre d'octets spécifié, avec une mémoire tampon que vous fournissez.|  
|Gestion des exceptions.|Utilisez la classe [CInternetException](../mfc/reference/cinternetexception-class.md).|Gère tous les types d'exception Internet communs.|  
|Termine la session FTP.|Jetez l'objet [CInternetSession](../mfc/reference/cinternetsession-class.md).|Nettoie automatiquement les handles et les connexions de fichiers ouverts.|  
  
## Voir aussi  
 [Extension Internet Win32 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Composants requis pour les classes clientes Internet](../mfc/prerequisites-for-internet-client-classes.md)   
 [Écriture d'une application cliente Internet en utilisant des classes WinInet MFC](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)