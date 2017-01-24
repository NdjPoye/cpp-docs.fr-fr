---
title: "ODBC et MFC | Microsoft Docs"
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
  - "connexions (C++), source de données"
  - "connexions (C++), bases de données"
  - "sources de données (C++), connecter à"
  - "connexions de base de données (C++), classes ODBC MFC"
  - "bases de données (C++), connecter à"
  - "MFC (C++), ODBC et"
  - "ODBC (C++), MFC"
ms.assetid: 98f02fd7-1235-437b-89a9-edfd0fc797f7
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ODBC et MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Pour utiliser les classes de base de données MFC destinées à une plateforme Win32 \(comme Windows NT\), vous devez posséder le pilote ODBC approprié pour votre source de données.  Certains pilotes sont inclus dans Visual C\+\+ ; d'autres peuvent être obtenus auprès de Microsoft ou d'autres fournisseurs.  Pour plus d'informations, consultez [Liste de pilotes ODBC](../../data/odbc/odbc-driver-list.md).  
  
 Cette rubrique introduit les concepts principaux des classes de base de données ODBC de la bibliothèque MFC \(Microsoft Foundation Classes\) et propose un aperçu du fonctionnement entre ces classes.  Pour plus d'informations sur ODBC et MFC, consultez les rubriques suivantes :  
  
-   [Connexion à une source de données](../../data/odbc/connecting-to-a-data-source.md)  
  
-   [Sélection et manipulation d'enregistrements](../../data/odbc/selecting-and-manipulating-records.md)  
  
-   [Affichage et manipulation de données dans un formulaire](../../data/odbc/displaying-and-manipulating-data-in-a-form.md)  
  
-   [Utilisation des documents et vues](../../data/odbc/working-with-documents-and-views.md)  
  
-   [Accès à ODBC et SQL](../../data/odbc/access-to-odbc-and-sql.md)  
  
-   [Informations supplémentaires sur les classes ODBC MFC](../../data/odbc/further-reading-about-the-mfc-odbc-classes.md)  
  
 Les classes de base de données MFC basées sur ODBC sont conçues pour fournir l'accès à toute base de données pour laquelle un pilote ODBC est disponible.  Puisque les classes utilisent ODBC, votre application peut accéder aux données de différents formats et différentes configurations locales\/distantes.  Vous ne devez pas écrire de code dans une casse spéciale pour gérer différents systèmes de gestion de base de données \(SGBD\).  Si vos utilisateurs ont un pilote ODBC approprié pour les données auxquelles ils veulent accéder, ils peuvent utiliser votre programme pour manipuler les données dans les tables enregistrées dans ce programme.  
  
## Voir aussi  
 [ODBC \(Open Database Connectivity\)](../../data/odbc/open-database-connectivity-odbc.md)