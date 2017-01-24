---
title: "&#201;tapes dans une application cliente HTTP classique | Microsoft Docs"
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
  - "applications (MFC), Client HTTP"
  - "applications clientes (C++), HTTP"
  - "applications clientes HTTP"
  - "applications Internet (C++), applications clientes HTTP"
  - "Internet (applications clientes) (C++), table HTTP"
  - "classes WinInet, HTTP"
ms.assetid: f86552e8-8acd-4b23-bdc5-0c3a247ebd74
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &#201;tapes dans une application cliente HTTP classique
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le tableau suivant montre les étapes que vous pouvez effectuer dans une application cliente HTTP standard.  
  
|Votre objectif|Mesures que vous prenez|Effets|  
|--------------------|-----------------------------|------------|  
|Démarrez une session HTTP.|Créez un objet [CInternetSession](../mfc/reference/cinternetsession-class.md).|Initialise WinInet et se connecte au serveur.|  
|Connectez vous à un serveur HTTP.|Utilisez [CInternetSession::GetHttpConnection](../Topic/CInternetSession::GetHttpConnection.md).|Retourne un objet [CHttpConnection](../mfc/reference/chttpconnection-class.md).|  
|Ouvrez une requête HTTP.|Utilisez [CHttpConnection::OpenRequest](../Topic/CHttpConnection::OpenRequest.md).|Retourne un objet  [CHttpFile](../mfc/reference/chttpfile-class.md).|  
|Envoyez une demande HTTP.|Utilisez [CHttpFile::AddRequestHeaders](../Topic/CHttpFile::AddRequestHeaders.md) et [CHttpFile::SendRequest](../Topic/CHttpFile::SendRequest.md).|Recherche le fichier.  Retourne FALSE si le fichier est introuvable.|  
|Lire dans le fichier.|Utilisez [CHttpFile](../mfc/reference/chttpfile-class.md).|Lit le nombre d'octets spécifié avec une mémoire tampon que vous fournissez.|  
|Gestion des exceptions.|Utilisez la classe [CInternetException](../mfc/reference/cinternetexception-class.md).|Gère tous les types d'exception Internet communs.|  
|Termine la session HTTP.|Jetez l'objet [CInternetSession](../mfc/reference/cinternetsession-class.md).|Nettoie automatiquement les handles et les connexions de fichiers ouverts.|  
  
## Voir aussi  
 [Extension Internet Win32 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Composants requis pour les classes clientes Internet](../mfc/prerequisites-for-internet-client-classes.md)   
 [Écriture d'une application cliente Internet en utilisant des classes WinInet MFC](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)