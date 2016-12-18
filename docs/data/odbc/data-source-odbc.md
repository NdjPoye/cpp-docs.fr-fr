---
title: "Source de donn&#233;es (ODBC) | Microsoft Docs"
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
  - "CDatabase (classe), connexions de source de données"
  - "configurer les sources de données ODBC"
  - "sources de données ODBC"
  - "sources de données ODBC, configurer"
  - "sources de données ODBC, représentées par CDatabase"
ms.assetid: b246721f-b9e1-49bd-a6c7-f348b8c3d537
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Source de donn&#233;es (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique s'applique aux classes ODBC MFC.  
  
 Dans la terminologie de base de données, une source de données représente un groupe spécifique de données, les informations nécessaires pour accéder à ces données et l'emplacement de la source de données, pouvant être décrite par un nom de source de données.  Pour utiliser la classe [CDatabase](../../mfc/reference/cdatabase-class.md), vous devez configurer la source de données à l'aide de l'Administrateur ODBC.  Une base de données distante s'exécutant sur Microsoft SQL Server au sein d'un réseau ou un fichier Microsoft Access dans un répertoire local constitue des exemples de sources de données.  Vous pouvez accéder à toute source de données pour laquelle vous possédez un pilote ODBC à partir de votre application.  
  
 Une ou plusieurs sources de données peuvent être actives simultanément dans votre application, chacune étant représentée par un objet `CDatabase`.  Plusieurs connexions simultanées à une source de données peuvent également être actives.  Vous pouvez vous connecter à des sources de données distantes ou locales, selon les pilotes installés et les fonctionnalités de vos pilotes ODBC.  Pour plus d'informations sur les sources de données et l'Administrateur ODBC, consultez [ODBC](../../data/odbc/odbc-basics.md) et [Administrateur ODBC](../../data/odbc/odbc-administrator.md).  
  
 Les rubriques suivantes fournissent plus d'informations sur les sources de données :  
  
-   [Source de données : gestion des connexions \(ODBC\)](../../data/odbc/data-source-managing-connections-odbc.md)  
  
-   [Source de données : détermination du schéma de la source de données \(ODBC\)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)  
  
## Voir aussi  
 [ODBC \(Open Database Connectivity\)](../../data/odbc/open-database-connectivity-odbc.md)