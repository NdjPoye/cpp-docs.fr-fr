---
title: "Windows Sockets, classes (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.net"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes de sockets"
  - "Windows Sockets (C++), classes"
ms.assetid: 58b9ab8d-9e44-4db3-8265-e04e713d2e9a
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Sockets, classes (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Windows Sockets fournit un réseau de protocoles indépendants pour communiquer entre deux ordinateurs.  Ces prises peuvent être synchrones \(votre programme attend que la communication est effectuée\) ou asynchrone \(votre programme continue d'exécuter lorsque la communication passe sur\).  
  
 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)  
 Encapsule l'API Windows Sockets API dans un wrapper léger.  
  
 [CSocket](../mfc/reference/csocket-class.md)  
 Abstraction de niveau supérieur dérivée de `CAsyncSocket`.  Elle fonctionne de manière synchrone.  
  
 [CSocketFile](../mfc/reference/csocketfile-class.md)  
 Fournit une interface de `CFile` à un Winsock.  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)