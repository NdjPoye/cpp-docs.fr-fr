---
title: "Classes MFC pour la cr&#233;ation d&#39;applications clientes Internet | Microsoft Docs"
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
  - "classes (C++), MFC"
  - "applications Internet, MFC"
  - "Internet (applications clientes), MFC"
  - "MFC, classes WinInet"
  - "classes WinInet, classes"
ms.assetid: 67d34117-9839-4f4b-8bb8-0e4a9471c606
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes MFC pour la cr&#233;ation d&#39;applications clientes Internet
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC fournit les classes suivantes et les fonctions globales pour écrire des applications clientes Internet.  La mise en retrait montre une classe est dérivée de la classe retrait au\-dessus de elle.  `CGopherFile` et `CHttpFile` dérivent de `CInternetFile`, par exemple.  Ces classes et fonctions globales sont déclarées dans AFXINET.H, sauf `CFileFind`, qui est déclaré dans. AFX.H.  
  
## Classes  
  
-   [CInternetSession](../mfc/reference/cinternetsession-class.md)  
  
-   [CInternetConnection](../mfc/reference/cinternetconnection-class.md)  
  
    -   [CFtpConnection](../mfc/reference/cftpconnection-class.md)  
  
    -   [CGopherConnection](../mfc/reference/cgopherconnection-class.md)  
  
    -   [CHttpConnection](../mfc/reference/chttpconnection-class.md)  
  
-   [CInternetFile](../mfc/reference/cinternetfile-class.md)  
  
    -   [CGopherFile](../mfc/reference/cgopherfile-class.md)  
  
    -   [CHttpFile](../mfc/reference/chttpfile-class.md)  
  
-   [CFileFind](../mfc/reference/cfilefind-class.md)  
  
    -   [CFtpFileFind](../mfc/reference/cftpfilefind-class.md)  
  
    -   [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md)  
  
-   [CGopherLocator](../mfc/reference/cgopherlocator-class.md)  
  
-   [CInternetException](../mfc/reference/cinternetexception-class.md)  
  
## fonctions globales  
  
-   [AfxParseURL](../Topic/AfxParseURL.md)  
  
-   [AfxGetInternetHandleType](../Topic/AfxGetInternetHandleType.md)  
  
-   [AfxThrowInternetException](../Topic/AfxThrowInternetException.md)  
  
## Voir aussi  
 [Extension Internet Win32 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Composants requis pour les classes clientes Internet](../mfc/prerequisites-for-internet-client-classes.md)   
 [Écriture d'une application cliente Internet en utilisant des classes WinInet MFC](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)