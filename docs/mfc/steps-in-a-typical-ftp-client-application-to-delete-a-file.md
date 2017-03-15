---
title: "&#201;tapes pour supprimer un fichier dans une application cliente FTP classique | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FTP (File Transfer Protocol), applications clientes"
  - "applications Internet, applications clientes FTP"
  - "Internet (applications clientes), FTP (supprimer)"
  - "classes WinInet, FTP"
ms.assetid: 2c347a96-c0a4-4827-98fe-668406e552bc
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# &#201;tapes pour supprimer un fichier dans une application cliente FTP classique
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le tableau suivant montre les étapes que vous pouvez effectuer dans une application client FTP typique qui supprime un fichier.  
  
|Votre objectif|Mesures que vous prenez|Effets|  
|--------------------|-----------------------------|------------|  
|Démarrez une session FTP.|Créez un objet métier de la classe [CInternetSession](../mfc/reference/cinternetsession-class.md)|Initialise WinInet et se connecte au serveur.|  
|Connectez vous à un serveur FTP.|Utilisez [CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md).|Retourne un objet [CFtpConnection](../mfc/reference/cftpconnection-class.md).|  
|Vérifiez que vous êtes dans le bon répertoire du serveur FTP.|Utilisez [CFtpConnection::GetCurrentDirectory](../Topic/CFtpConnection::GetCurrentDirectory.md) ou [CFtpConnection::GetCurrentDirectoryAsURL](../Topic/CFtpConnection::GetCurrentDirectoryAsURL.md).|Retourne le nom ou l'URL du répertoire auquel vous êtes connecté sur le serveur, selon la fonction membre sélectionnée.|  
|Accédez à un nouveau répertoire FTP sur le serveur.|Utilisez [CFtpConnection::SetCurrentDirectory](../Topic/CFtpConnection::SetCurrentDirectory.md).|Modifie le répertoire auquel vous êtes connecté sur le serveur.|  
|Recherchez le premier fichier dans le répertoire FTP.|Utilisez [CFtpFileFind::FindFile](../Topic/CFtpFileFind::FindFile.md).|Recherche le premier fichier.  Retourne FALSE si aucun fichier n'est trouvé.|  
|Recherchez le premier fichier dans le répertoire FTP.|Utilisez[CFtpFileFind::FindNextFile](../Topic/CFtpFileFind::FindNextFile.md).|Recherche le fichier suivant.  Retourne FALSE si le fichier est introuvable.|  
|Supprimez le fichier recherché avec **FindFile** ou `FindNextFile`.|Utilisez [CFtpConnection::Remove](../Topic/CFtpConnection::Remove.md), avec le nom de fichier retourné par **FindFile** ou `FindNextFile`.|Supprime le fichier sur le serveur pour lire ou écrire.|  
|Gestion des exceptions.|Utilisez la classe [CInternetException](../mfc/reference/cinternetexception-class.md).|Gère tous les types d'exception Internet communs.|  
|Termine la session FTP.|Jetez l'objet [CInternetSession](../mfc/reference/cinternetsession-class.md).|Nettoie automatiquement les handles et les connexions de fichiers ouverts.|  
  
## Voir aussi  
 [Extension Internet Win32 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Composants requis pour les classes clientes Internet](../mfc/prerequisites-for-internet-client-classes.md)   
 [Écriture d'une application cliente Internet en utilisant des classes WinInet MFC](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)