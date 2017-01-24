---
title: "Les langages DDL et DML sont-ils pris en charge&#160;? | Microsoft Docs"
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
  - "langage de manipulation de données (DML) dans ODBC MFC (C++)"
  - "bases de données (C++), accéder dans DAO"
  - "bases de données (C++), accès DDL"
  - "bases de données (C++), accès DML"
  - "DDL (C++), prise en charge des MFC"
  - "DML (C++)"
  - "DML (C++), ODBC MFC"
ms.assetid: 07f96d81-78d4-4bec-9138-b15d68fd5ce0
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Les langages DDL et DML sont-ils pris en charge&#160;?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les classes DAO MFC prennent en charge deux types d'accès aux bases de données :  
  
-   **DDL \(Data definition language\)** Permet de créer et de supprimer des bases de données, de créer et de supprimer des tables, de définir des index et des champs de tables, et d'exécuter d'autres actions affectant la structure de votre base de données.  
  
-   **DML \(Data manipulation language\)** Permet d'exécuter des requêtes, d'ajouter, de supprimer et d'éditer des enregistrements, et de manipuler le contenu de la base de données.  
  
 Les classes ODBC MFC prennent en charge uniquement DML, mais vous pouvez appeler les fonctionnalités de l'API ODBC directement pour exécuter des tâches DDL.  
  
## Voir aussi  
 [Forum aux questions sur l'accès aux données](../data/data-access-frequently-asked-questions-mfc-data-access.md)