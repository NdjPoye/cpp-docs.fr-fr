---
title: "Classes MFC pour la création d’Applications clientes Internet | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC, WinInet classes
- WinInet classes [MFC], classes
- classes [MFC], MFC
- Internet client applications [MFC], MFC
- Internet applications [MFC], MFC
ms.assetid: 67d34117-9839-4f4b-8bb8-0e4a9471c606
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9ddbab63bb587ac726337ee719cfab03a760a305
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-classes-for-creating-internet-client-applications"></a>Classes MFC pour la création d'applications clientes Internet
MFC fournit les classes suivantes et les fonctions globales pour l’écriture d’applications clientes Internet. Mise en retrait indique une classe est dérivée de la classe non mis en retrait au-dessus de lui. `CGopherFile`et `CHttpFile` dérivent `CInternetFile`, par exemple. Ces classes et fonctions globales sont déclarées dans AFXINET. H, sauf `CFileFind`, qui est déclaré dans AFX. H.  
  
## <a name="classes"></a>Classes  
  
-   [CInternetSession](../mfc/reference/cinternetsession-class.md)  
  
-   [CInternetConnection](../mfc/reference/cinternetconnection-class.md)  
  
    -   [CFtpConnection](../mfc/reference/cftpconnection-class.md)  
  
    -   [Objet CGopherConnection](../mfc/reference/cgopherconnection-class.md)  
  
    -   [Objet CHttpConnection](../mfc/reference/chttpconnection-class.md)  
  
-   [CInternetFile](../mfc/reference/cinternetfile-class.md)  
  
    -   [CGopherFile](../mfc/reference/cgopherfile-class.md)  
  
    -   [CHttpFile](../mfc/reference/chttpfile-class.md)  
  
-   [CFileFind](../mfc/reference/cfilefind-class.md)  
  
    -   [CFtpFileFind](../mfc/reference/cftpfilefind-class.md)  
  
    -   [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md)  
  
-   [Objet CGopherLocator](../mfc/reference/cgopherlocator-class.md)  
  
-   [CInternetException](../mfc/reference/cinternetexception-class.md)  
  
## <a name="global-functions"></a>Fonctions globales  
  
-   [AfxParseURL](reference/internet-url-parsing-globals.md#afxparseurl)  
  
-   [AfxGetInternetHandleType](reference/internet-url-parsing-globals.md#afxgetinternethandletype)  
  
-   [AfxThrowInternetException](reference/internet-url-parsing-globals.md#afxthrowinternetexception)  
  
## <a name="see-also"></a>Voir aussi  
 [Extension Internet Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [Conditions préalables pour les Classes clientes Internet](../mfc/prerequisites-for-internet-client-classes.md)   
 [Écriture d’une application cliente Internet en utilisant des classes WinInet MFC](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
