---
title: "Threads et classes ODBC | Microsoft Docs"
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
  - "classes ODBC, et threads"
  - "ODBC, applications multithread"
  - "threads (MFC), prise en charge ODBC"
ms.assetid: 16543926-7331-41a6-ba50-72288f2a61b7
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Threads et classes ODBC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Depuis la version 4.2 de MFC, la prise en charge de multithreading est assurée pour les classes ODBC MFC.  Notez cependant que MFC ne fournit aucune prise en charge de multithreading pour les classes DAO.  
  
 La prise en charge de multithreading pour les classes ODBC connaît certaines limites.  Puisque ces classes encapsulent l'API ODBC, elles sont limitées à la prise en charge de multithreading des composants sur lesquels elles sont construites.  Par exemple, la plupart des pilotes ODBC ne sont pas thread\-safe ; les classes ODBC MFC ne sont donc pas thread\-safe si vous les utilisez avec l'un de ces pilotes.  Vérifiez si votre pilote particulier est thread\-safe.  
  
 Lors de la création d'une application multithread, soyez vigilant lorsque vous utilisez plusieurs threads pour manipuler le même objet.  Par exemple, l'utilisation d'un même objet `CRecordset` dans deux threads peut entraîner des problèmes lors de la récupération de données ; une opération d'extraction dans un thread peut remplacer les données extraites dans l'autre thread.  Une utilisation plus ordinaire des classes ODBC MFC dans des threads distincts consiste à partager un objet `CDatabase` ouvert entre les threads afin d'utiliser la même connexion ODBC, avec un objet `CRecordset` distinct dans chaque thread.  Notez que vous ne devez pas passer un objet `CDatabase` non ouvert à un objet `CRecordset` dans un autre thread.  
  
> [!NOTE]
>  Si plusieurs threads doivent manipuler le même objet, implémentez les mécanismes de synchronisation appropriés, tels que les sections critiques.  Sachez que certaines opérations, comme **Open**, ne sont pas protégées.  Assurez\-vous que ces opérations ne seront pas appelées simultanément à partir de threads distincts.  
  
 Pour plus d'informations sur la création d'applications multithread, consultez [Rubriques relatives au multithreading](../../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
## Voir aussi  
 [ODBC \(Open Database Connectivity\)](../../data/odbc/open-database-connectivity-odbc.md)   
 [Programmation de l'accès aux données \(MFC\/ATL\)](../../data/data-access-programming-mfc-atl.md)