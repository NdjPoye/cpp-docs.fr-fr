---
title: "Qu&#39;est-ce que le mod&#232;le de programmation de bases de donn&#233;es MFC&#160;? | Microsoft Docs"
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
  - "DAO (C++), MFC"
  - "accès aux données (C++), technologies"
  - "bases de données (C++), MFC"
  - "MFC (C++), applications de bases de données"
  - "ODBC (C++), MFC"
  - "ODBC (classes) (C++), classes de base de données MFC"
ms.assetid: f6f15bb8-4115-41f2-ad68-036e74a11bd9
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Qu&#39;est-ce que le mod&#232;le de programmation de bases de donn&#233;es MFC&#160;?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DAO et ODBC ont des interfaces similaires même si, de manière sous\-jacente, elles sont implémentées différemment par les MFC ; il est relativement aisé de porter vos applications de l'une à l'autre, notamment de ODBC vers DAO.  Pour plus d'informations sur le portage d'applications de ODBC vers DAO, consultez la [Technical Note 55](../mfc/tn055-migrating-mfc-odbc-database-class-applications-to-mfc-dao-classes.md).  Les interfaces DAO et ODBC MFC sont également semblables à celles de Visual Basic.  
  
 Le modèle de programmation MFC met en œuvre un objet de base de données pour chaque base de données ouverte.  L'objet de base de données représente la connexion à la base de données.  Vous effectuez les requêtes et les mises à jour par l'intermédiaire d'objets Recordset.  DAO fournit des objets supplémentaires, décrits plus loin, pour travailler avec la structure des tables, enregistrer les requêtes en vue de les réutiliser, etc.  La bibliothèque MFC fournit des classes pour chacun de ces objets : un jeu de classes pour DAO et un autre pour ODBC.  
  
 L'utilisation de la bibliothèque MFC simplifie l'accès aux données.  Les classes de bases de données DAO et ODBC fournissent des abstractions de haut niveau qui vous affranchissent de l'utilisation directe de l'interface DAO ou ODBC.  L'écriture dans leurs API est plus complexe que l'utilisation des classes MFC.  Ceci est particulièrement vrai lorsque vous écrivez de petites applications relativement simples.  
  
 Les classes de bases de données ajoutent les composants suivants à la bibliothèque de classes MFC :  
  
-   des classes de bases de données C\+\+ qui fournissent une API de haut niveau pour l'accès aux bases de données par l'intermédiaire de DAO ou ODBC ;  
  
-   des extensions de l'Assistant Application et **Ajouter une classe** pour la création de classes de bases de données spécifiques à l'application ;  
  
-   des programmes exemple qui illustrent l'utilisation des classes et des Assistants ;  
  
-   la documentation en ligne qui comprend des vues d'ensemble, des articles traitant de la programmation et des articles de référence sur les classes.  
  
 Pour plus d'informations sur ces composants, consultez [ODBC et MFC](../data/odbc/odbc-and-mfc.md).  
  
 Pour plus d'informations, consultez :  
  
-   [Choix entre DAO et ODBC](../data/should-i-use-dao-or-odbc-q.md)  
  
-   [Disponibilité du langage DDL \(Database Definition Language\) et DML \(Database Manipulation Language\)](../data/are-ddl-and-dml-supported-q.md) dans DAO et ODBC  
  
-   [Installation de la prise en charge des bases de données MFC](../data/installing-mfc-database-support.md)  
  
-   Classes [ODBC](../data/odbc/odbc-and-mfc.md) dans MFC.  
  
-   [Documentation de la programmation de l'accès aux données MFC](../data/mfc-database-documentation.md)  
  
-   [Implémentation de ODBC par MFC](../data/odbc/odbc-and-mfc.md)  
  
## Voir aussi  
 [Forum aux questions sur l'accès aux données](../data/data-access-frequently-asked-questions-mfc-data-access.md)