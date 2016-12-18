---
title: "Classes d&#39;exceptions | Microsoft Docs"
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
  - "vc.classes.exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes d'exceptions"
  - "gestion des exceptions, classes d'exceptions"
  - "MFC, exceptions"
ms.assetid: 1a2caf12-b3e9-4189-86d2-bf7a595bf025
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes d&#39;exceptions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La bibliothèque de classes fournit un mécanisme de gestion des exceptions basé sur la classe `CException`.  Le framework d'application utilise des exceptions dans son code ; utilisez les également dans le vôtre.  Pour plus d'informations, consultez [Gestion des exceptions](../mfc/exception-handling-in-mfc.md).  Vous pouvez dériver vos propres types d'exception de `CException`.  
  
 MFC fournit une classe d'exception dont vous pouvez dériver votre propre exception ainsi que la classe d'exception pour toutes les exceptions qu'il prend en charge.  
  
 [CException](../mfc/reference/cexception-class.md)  
 Classe de base pour les exceptions .  
  
 [CArchiveException](../mfc/reference/carchiveexception-class.md)  
 Une exception d'archive.  
  
 [CDaoException](../mfc/reference/cdaoexception-class.md)  
 Une exception résultant d'un échec d'une opération de base de données DAO.  
  
 [CDBException](../mfc/reference/cdbexception-class.md)  
 Une exception résultant d'une défaillance de traitement de base de données ODBC.  
  
 [CFileException](../mfc/reference/cfileexception-class.md)  
 Une exception orientée fichier.  
  
 [CMemoryException](../mfc/reference/cmemoryexception-class.md)  
 Une exception de mémoire pleine  
  
 [CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md)  
 Une exception résultant de l'utilisation d'une fonctionnalité non prise en charge.  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 Une exception résultant d'une défaillance de traitement OLE.  Cette classe est utilisée par les conteneurs et les serveurs.  
  
 [COleDispatchException](../mfc/reference/coledispatchexception-class.md)  
 Une exception résultant d'une erreur pendant l'automation.  Les exceptions d'automation sont levées par les serveurs COM et interceptées par les clients d'automation.  
  
 [CResourceException](../mfc/reference/cresourceexception-class.md)  
 Une exception résultant d'échec de chargement d'une ressource windows.  
  
 [CUserException](../mfc/reference/cuserexception-class.md)  
 Une exception utilisée pour arrêter une opération initialisée l'utilisateur.  En général, l'utilisateur a été notifié du problème avant que cette exception soit levée.  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)