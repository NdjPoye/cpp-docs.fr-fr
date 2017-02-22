---
title: "Windows Sockets&#160;: conversion de cha&#238;nes | Microsoft Docs"
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
  - "sockets (C++), problèmes de conversion de chaînes de caractères multioctets"
  - "conversion de chaînes, chaînes de caractères multioctets"
  - "Windows Sockets (C++), conversion de chaînes de caractères multioctets"
ms.assetid: 9df522b5-6b23-41e0-bb96-e4e623baf141
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Windows Sockets&#160;: conversion de cha&#238;nes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article et deux autres expliquent plusieurs problèmes de programmation Windows \(.  Cet article aborde la conversion de chaînes.  Les autres problèmes sont traités dans [Protocole Windows : Blocage](../mfc/windows-sockets-blocking.md) et [Protocole Windows : Ordre d'octet](../mfc/windows-sockets-byte-ordering.md).  
  
 Si vous utilisez ou dérivez de la classe [CAsyncSocket](../mfc/reference/casyncsocket-class.md), vous devez gérer ces problèmes vous\-même.  Si vous utilisez ou dérivez de la classe [CSocket](../mfc/reference/csocket-class.md), MFC les gère automatiquement.  
  
## convertir des chaînes  
 Si vous communiquez entre les applications qui utilisent des chaînes stockées dans différents formats de caractères étendus, par exemple\) ou des jeux de caractères multioctets \(MBCS\), ou entre une de ces et une application utilisant les chaînes de caractères ANSI, vous devez gérer les conversions vous\-même en `CAsyncSocket`.  L'objet de `CArchive` utilisé avec un objet de `CSocket` gère cette conversion automatiquement via les fonctions de la classe [CString](../atl-mfc-shared/reference/cstringt-class.md).  Pour plus d'informations, consultez la spécification de protocole Windows, situé dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 Pour plus d'informations, consultez :  
  
-   [Windows Sockets : utilisation de la classe CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Sockets : utilisation de sockets avec des archives](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Sockets : arrière\-plan](../mfc/windows-sockets-background.md)  
  
-   [Windows Sockets : sockets flux](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Sockets : sockets datagramme](../mfc/windows-sockets-datagram-sockets.md)  
  
## Voir aussi  
 [Windows Sockets dans MFC](../mfc/windows-sockets-in-mfc.md)