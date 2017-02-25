---
title: "&#201;l&#233;ments fondamentaux relatifs &#224; ODBC | Microsoft Docs"
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
  - "ODBC (composants)"
  - "ODBC (composants), composants requis"
  - "ODBC (bibliothèque de curseurs), ODBC (composants)"
  - "ODBC, à propos d'ODBC"
  - "ODBC, composants"
ms.assetid: ec529702-0fb2-4754-b8de-d1efa8eca18f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# &#201;l&#233;ments fondamentaux relatifs &#224; ODBC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique décrit les concepts de base relatifs à ODBC \(Open Database Connectivity\) :  
  
-   [Comment ODBC utilise\-t\-il les classes de base de données ?](../../data/odbc/odbc-and-the-database-classes.md)  
  
-   [Comment les pilotes ODBC utilisent\-ils les feuilles de réponse dynamiques ?](../../data/odbc/odbc-driver-requirements-for-dynasets.md)  
  
-   [Quels sont les composants ODBC dont vous avez besoin pour redistribuer vos applications ?](../../data/odbc/redistributing-odbc-components-to-your-customers.md)  
  
 Vous pouvez également consulter la rubrique [ODBC : bibliothèque de curseurs ODBC](../../data/odbc/odbc-the-odbc-cursor-library.md).  
  
> [!NOTE]
>  Les sources de données ODBC sont accessibles via les classes ODBC MFC, comme le décrit cette rubrique, ou via les classes DAO \(Data Access Object\) MFC.  
  
> [!NOTE]
>  Les classes ODBC MFC prennent en charge Unicode et le multithreading.  Pour plus d'informations sur la prise en charge du multithreading, consultez [Threads et classes ODBC](../../data/odbc/odbc-classes-and-threads.md).  
  
 ODBC est une interface d'appels permettant aux applications d'accéder aux données de toute base de données pour laquelle un pilote ODBC existe.  Avec ODBC, vous pouvez créer des applications de base de données avec accès à n'importe quelle base de données pour laquelle l'utilisateur final possède un pilote ODBC.  ODBC fournit une API permettant à votre application d'être indépendante du système de gestion de base de données \(SGBD\) source.  
  
 ODBC est la partie de base de données WOSA \(Microsoft Windows Open Services Architecture\), une interface permettant aux applications de bureau Windows de se connecter à plusieurs environnements informatiques sans devoir réécrire l'application pour chaque plateforme.  
  
 Les composants de ODBC sont les suivants :  
  
-   API ODBC  
  
     Une bibliothèque d'appels de fonction, un ensemble de codes d'erreur et une syntaxe [SQL](../../data/odbc/sql.md) \(Structured Query Language\) standard pour accéder aux données des systèmes de gestion de base de données.  
  
-   Gestionnaire de pilote ODBC  
  
     Une bibliothèque de liens dynamiques \(Odbc32.dll\) qui charge les pilotes de base de données ODBC de la part d'une application.  Cette DLL est transparente pour votre application.  
  
-   Pilotes de base de données ODBC  
  
     Une ou plusieurs DLL qui traitent les appels de fonction ODBC pour des systèmes de gestion de base de données spécifiques.  Pour obtenir la liste des pilotes fournis, consultez [Liste de pilotes ODBC](../../data/odbc/odbc-driver-list.md).  
  
-   [Bibliothèque de curseurs ODBC](../../data/odbc/odbc-the-odbc-cursor-library.md)  
  
     Une bibliothèque de liens dynamiques \(Odbccr32.dll\) qui réside entre le gestionnaire de pilote ODBC et les pilotes, et qui gère la visualisation successive des données.  
  
-   [Administrateur ODBC](../../data/odbc/odbc-administrator.md)  
  
     Un outil utilisé pour configurer un système de gestion de base de données afin de le rendre disponible en tant que source de données pour une application.  
  
 Une application devient totalement indépendante des systèmes de gestion de base de données \(SGBD\) lorsqu'elle fonctionne par le biais d'un pilote ODBC écrit spécialement pour un système SGDB plutôt que de fonctionner directement avec celui\-ci.  Le pilote traduit les appels en commandes que peut utiliser son système SGBD, ce qui simplifie le travail du développeur et rend ce pilote disponible pour une large gamme de sources de données.  
  
 Les classes de base de données prennent en charge toute source de données pour laquelle vous possédez un pilote ODBC.  Par exemple, une source de données pourrait inclure une base de données relationnelle, une base de données ISAM \(Indexed Sequential Access Method\), une feuille de calcul Microsoft Excel ou un fichier texte.  Les pilotes ODBC gèrent les connexions à la source de données et SQL est utilisé afin de sélectionner des enregistrements dans la base de données.  
  
 Pour obtenir la liste des pilotes ODBC contenus dans cette version de Visual C\+\+ et des informations sur l'obtention de pilotes supplémentaires, consultez [Liste de pilotes ODBC](../../data/odbc/odbc-driver-list.md).  
  
## Voir aussi  
 [ODBC \(Open Database Connectivity\)](../../data/odbc/open-database-connectivity-odbc.md)