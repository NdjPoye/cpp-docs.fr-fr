---
title: "&#192; quelles sources de donn&#233;es puis-je acc&#233;der avec DAO et ODBC&#160;? | Microsoft Docs"
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
  - "DAO (C++), types de source de données"
  - "données (C++), DAO"
  - "données (C++), ODBC"
  - "accès aux données (C++), DAO"
  - "sources de données (C++), accessibles à l'aide de DAO et ODBC"
  - "bases de données (C++), accéder dans DAO"
  - "FAQ (Forum Aux Questions) (C++), bases de données accessibles"
  - "ODBC (C++), sources de données accessibles"
  - "ODBC (sources de données) (C++), accessibles"
ms.assetid: c88abb45-526a-467a-a01b-d9396bd63236
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &#192; quelles sources de donn&#233;es puis-je acc&#233;der avec DAO et ODBC&#160;?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les deux jeux de classes MFC permettent d'accéder à une large panoplie de sources de données et rendent possible l'écriture d'applications qui sont indépendantes de la source de données.  
  
##  <a name="_core_databases_you_can_access_with_dao"></a> Bases de données accessibles avec DAO  
 En utilisant DAO et les classes DAO MFC, vous pouvez accéder aux sources de données suivantes :  
  
-   Les bases de données utilisant le moteur de bases de données Microsoft Jet, créé à l'aide de Microsoft Access ou Microsoft Visual Basic, versions 1.x, 2.x et 3.0 du moteur de bases de données.  
  
-   Bases de données ISAM, en particulier :  
  
    -   dBASE III, dBASE IV et dBASE 5.0  
  
    -   Paradox, versions 3.x, 4.x et 5.x  
  
-   Les bases de données ODBC \(Open Database Connectivity\), y compris mais sans s'y limiter Microsoft SQL Server, SYBASE SQL Server et ORACLE Server.  Pour accéder à une base de données ODBC, vous devez disposer d'un pilote ODBC approprié pour la base de données à laquelle vous souhaitez accéder.  Pour obtenir la liste des pilotes ODBC contenus dans cette version de Visual C\+\+ et des informations sur l'obtention de pilotes supplémentaires, consultez [Liste de pilotes ODBC](../data/odbc/odbc-driver-list.md).  
  
-   Feuilles de calcul Microsoft Excel, versions 3.0, 4.0, 5.0 et 7.0.  
  
-   Feuilles de calcul Lotus WKS, WK1, WK3 et WK4.  
  
-   Fichiers texte.  
  
 DAO convient le mieux avec les bases de données que le moteur de base de données Microsoft Jet peut lire,  qui incluent tous éléments précités sauf les sources de données ODBC.  Les meilleures performances sont obtenues avec les bases de données Microsoft Jet \(.mdb\).  Il est plus efficace d'attacher des tables externes, notamment dans les sources de données ODBC, à une base de données .mdb que d'ouvrir la base de données externe directement via les classes DAO MFC sans connexion.  
  
##  <a name="_core_databases_you_can_access_with_odbc"></a> Bases de données accessibles avec ODBC  
 En utilisant les classes ODBC et ODBC MFC, vous pouvez accéder à n'importe quelle source de données, locale ou distante, pour laquelle l'utilisateur de votre application dispose d'un pilote ODBC. Les pilotes ODBC 16 bits, 32 bits et 64 bits, sont disponibles pour une large gamme de sources de données.  Si vous travaillez avec une base de données Microsoft Jet \(.mdb\), vous obtiendrez de meilleures performances avec les classes DAO qu'avec le pilote ODBC de Microsoft Access.  
  
## Voir aussi  
 [Forum aux questions sur l'accès aux données](../data/data-access-frequently-asked-questions-mfc-data-access.md)