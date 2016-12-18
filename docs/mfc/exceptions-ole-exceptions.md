---
title: "Exceptions&#160;: exceptions OLE | Microsoft Docs"
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
  - "gestion des exceptions, OLE"
  - "exceptions, OLE"
  - "exceptions OLE"
  - "exceptions OLE, classes de gestion"
  - "OLE, exceptions"
ms.assetid: 2f8e0161-b94f-48bb-a5a2-6f644b192527
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Exceptions&#160;: exceptions OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les techniques et les fonctionnalités de gestion des exceptions dans OLE sont les mêmes que celles pour gérer les exceptions.  Pour plus d'informations sur la gestion des exceptions, consultez l'article [Gestion d'exceptions C\+\+](../cpp/cpp-exception-handling.md).  
  
 Tous les objets d'exception sont dérivés de la classe de base abstraite `CException`.  MFC fournit deux classes permettant de gérer des exceptions OLE:  
  
-   [COleException](../mfc/reference/coleexception-class.md) pour la gestion d'exceptions générales OLE.  
  
-   [COleDispatchException](../mfc/reference/coledispatchexception-class.md) pour la création et la gestion des exception d'expédition \(automation\) OLE.  
  
 La différence entre ces deux classes est la quantité d'informations qu'elles contiennent et où elles sont utilisées.  `COleException` a un membre de données publiques qui contient le code d'état OLE pour l'exception.  `COleDispatchException` fournit des informations, notamment :  
  
-   Une erreur de code spécifique à l'application  
  
-   Une description de l'erreur, telle que « disque plein »  
  
-   Un contexte d'aide que votre application peut utiliser pour fournir des informations supplémentaires à l'utilisateur  
  
-   Le nom du fichier d'aide de votre application  
  
-   Le nom de l'application ou objet qui a généré l'exception.  
  
 `COleDispatchException` fournit des informations supplémentaires afin qu'elles puissent être utilisées sur les produits tels que Microsoft Visual Basic.  La description d'erreur verbale peut être utilisée dans un message ou dans une autre notification; les informations de l'Aide peuvent être utilisées pour aider l'utilisateur à répondre aux conditions qui ont provoqué l'exception.  
  
 Deux fonctions globales correspondent aux deux classes d'exception OLE: [AfxThrowOleException](../Topic/AfxThrowOleException.md) et [AfxThrowOleDispatchException](../Topic/AfxThrowOleDispatchException.md).  Utilisez\-les pour lever des exceptions générales OLE et des exceptions d'expédition OLE, respectivement.  
  
## Voir aussi  
 [Gestion des exceptions](../mfc/exception-handling-in-mfc.md)