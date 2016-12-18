---
title: "Comment MFC facilite la cr&#233;ation d&#39;applications clientes Internet | Microsoft Docs"
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
  - "applications Internet, MFC"
  - "Internet (applications clientes), MFC"
  - "MFC, applications Internet"
ms.assetid: 94437b3f-f15c-437d-b5fd-264a2efec9ab
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment MFC facilite la cr&#233;ation d&#39;applications clientes Internet
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La bibliothèque MFC encapsule les fonctions d'extension Internet Win32 \(WinInet\) d'une manière qui fournit un contexte familier pour les programmeurs de MFC.  MFC fournit trois classes de fichiers Internet \([CInternetFile](../mfc/reference/cinternetfile-class.md), [CHttpFile](../mfc/reference/chttpfile-class.md), et [CGopherFile](../mfc/reference/cgopherfile-class.md)\) dérivées de la classe de [CStdioFile](../mfc/reference/cstdiofile-class.md).  Non seulement ces classes permettent de récupérer et manipuler les données familères d'Internet aux programmeurs qui ont utilisé `CStdioFile` des fichiers locaux, mais avec ces classes vous pouvez traiter des fichiers locaux et les fichiers Internet de manière cohérente et transparente.  
  
 Les classes WinInet MFC fournissent les mêmes fonctionnalités que `CStdioFile` pour les données qui sont transférées sur Internet.  Ces classes synthétisent les protocoles Internet pour HTTP, FTP, et le Gopher dans une interface de programmation d'application de niveau supérieur, qui fournit un chemin d'accès rapide et facile pour créer des applications internet averties.  Par exemple, la connexion à un serveur FTP nécessite toujours plusieurs étapes à un niveau, mais en tant que développeur de MFC, vous devez uniquement effectuer un appel à `CInternetSession::GetFTPConnection` pour créer cette connexion.  
  
 En outre, les classes WinInet MFC offrent les avantages suivants :  
  
-   E\/S mise en mémoire tampon  
  
-   Type sécurisé pour gérer des données  
  
-   Paramètres par défaut pour de nombreuses fonctions  
  
-   Gestion des exceptions pour les erreurs courantes Internet  
  
-   Nettoyage automatique des gestions et ouvrir des connexions.  
  
## Voir aussi  
 [Extension Internet Win32 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Comment WinInet facilite la création d'applications clientes Internet](../mfc/how-wininet-makes-it-easier-to-create-internet-client-applications.md)