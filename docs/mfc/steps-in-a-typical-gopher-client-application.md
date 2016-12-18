---
title: "&#201;tapes dans une application cliente Gopher classique | Microsoft Docs"
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
  - "Gopher (applications clientes)"
  - "applications Internet, applications clientes Gopher"
  - "Internet (applications clientes), table Gopher"
  - "classes WinInet, gopher"
ms.assetid: 3e4e1869-5da0-453d-8ba9-b648c894bb90
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &#201;tapes dans une application cliente Gopher classique
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le tableau suivant montre les étapes que vous pouvez effectuer dans une application cliente Gopher standard.  
  
|Votre objectif|Mesures que vous prenez|Effets|  
|--------------------|-----------------------------|------------|  
|Démarrez une session de Gopher.|Créez un objet [CInternetSession](../mfc/reference/cinternetsession-class.md).|Initialise WinInet et se connecte au serveur.|  
|Se connecte à un serveur Gopher.|Utilise [CInternetSession::GetGopherConnection](../Topic/CInternetSession::GetGopherConnection.md).|Retourne un objet [CGopherConnection](../mfc/reference/cgopherconnection-class.md).|  
|Recherchez la première ressource du Gopher.|Utilise [CGopherFileFind::FindFile](../Topic/CGopherFileFind::FindFile.md).|Recherche le premier fichier.  Retourne FALSE si aucun fichier n'est trouvé.|  
|Recherche la ressource suivante du Gopher.|Utilise [CGopherFileFind::FindNextFile](../Topic/CGopherFileFind::FindNextFile.md).|Recherche le fichier suivant.  Retourne FALSE si le fichier est introuvable.|  
|Ouvrez le fichier trouvé par **FindFile** ou `FindNextFile` pour le lire.|Obtient un localisateur de Gopher à l'aide de [CGopherFileFind::GetLocator](../Topic/CGopherFileFind::GetLocator.md).  Utilise [CGopherConnection::OpenFile](../Topic/CGopherConnection::OpenFile.md).|Ouvre le fichier spécifié par le localisateur.  `OpenFile` retourne un objet [CGopherFile](../mfc/reference/cgopherfile-class.md).|  
|Ouvrez un fichier à l'aide d'un localisateur de Gopher que vous fournissez.|Créez un localisateur de Gopher avec [CGopherConnection::CreateLocator](../Topic/CGopherConnection::CreateLocator.md).  Utilise [CGopherConnection::OpenFile](../Topic/CGopherConnection::OpenFile.md).|Ouvre le fichier spécifié par le localisateur.  `OpenFile` retourne un objet [CGopherFile](../mfc/reference/cgopherfile-class.md).|  
|Lire dans le fichier.|Utiliser [CGopherFile](../mfc/reference/cgopherfile-class.md).|Lit le nombre d'octets spécifié, avec une mémoire tampon que vous fournissez.|  
|Gestion des exceptions.|Utilisez la classe [CInternetException](../mfc/reference/cinternetexception-class.md).|Gère tous les types d'exception Internet communs.|  
|Arrêtez la session de Gopher.|Jetez l'objet [CInternetSession](../mfc/reference/cinternetsession-class.md).|Nettoie automatiquement les handles et les connexions de fichiers ouverts.|  
  
## Voir aussi  
 [Extension Internet Win32 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Composants requis pour les classes clientes Internet](../mfc/prerequisites-for-internet-client-classes.md)   
 [Écriture d'une application cliente Internet en utilisant des classes WinInet MFC](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)