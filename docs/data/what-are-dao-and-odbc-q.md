---
title: "Que sont DAO et ODBC&#160;? | Microsoft Docs"
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
  - "DAO (Data Access Objects), et ODBC"
  - "ODBC, à propos d'ODBC"
ms.assetid: 22cc2f75-7ff6-47bc-ac56-56a40591104c
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Que sont DAO et ODBC&#160;?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DAO \(Data Access Objects\) et ODBC \(Open Database Connectivity\) sont des interfaces de programmation d'applications \(API, Application Programming Interfaces\) qui permettent d'écrire des applications indépendantes de tout système SGBD \(Système de Gestion de Base de Données\) particulier.  
  
 La technique DAO est familière aux programmeurs de bases de données qui se servent de Microsoft Access Basic ou de Microsoft Visual Basic.  DAO utilise le moteur de bases de données Microsoft Jet pour fournir un ensemble d'objets d'accès aux données : objets database, objets tabledef et querydef, objets recordset, etc.  DAO fonctionne de façon optimale avec les fichiers .mdb, à l'instar de ceux créés par Microsoft Access, mais vous pouvez également accéder aux sources de données ODBC via DAO et le moteur de bases de données Microsoft Jet.  
  
 ODBC fournit une interface API que différents éditeurs de bases de données implémentent par l'intermédiaire de pilotes ODBC spécifiques à un système SGBD particulier.  Votre programme utilise cette interface API pour appeler le gestionnaire de pilotes ODBC, qui passe les appels au pilote approprié.  Le pilote, à son tour, interagit avec le SGBD par l'intermédiaire de SQL.  
  
> [!NOTE]
>  ODBC est un composant majeur de l'architecture WOSA \(Windows Open Standards Architecture\) de Microsoft.  La technique DAO est optimisée autour du moteur de bases de données Microsoft Jet, mais vous pouvez quand même accéder aux sources de données ODBC et à d'autres sources de données externes à l'aide de ce moteur, alors que les différentes API ODBC et les classes MFC qui lui servent de base sont toujours disponibles et conservent leur rôle dans la sélection d'outils de base de données.  
  
## Voir aussi  
 [Forum aux questions sur l'accès aux données](../data/data-access-frequently-asked-questions-mfc-data-access.md)