---
title: "Redistribution des composants ODBC &#224; vos clients | Microsoft Docs"
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
  - "composants (C++)"
  - "composants (C++), distribuer"
  - "composants (C++), redistribuer"
  - "Administrateur ODBC"
  - "ODBC (composants), redistribuer"
  - "ODBC, distribuer des composants"
ms.assetid: 17b065b4-a307-4b89-99ac-d05831cfab87
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Redistribution des composants ODBC &#224; vos clients
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Si vous incorporez la fonctionnalité des programmes de l'Administrateur ODBC dans votre application, vous devez également distribuer les fichiers exécutant ces programmes à vos utilisateurs.  Ces fichiers ODBC se situent dans le répertoire \\OS\\System du CD\-ROM de Visual C\+\+.  Dans ce même répertoire, le fichier Redistrb.wri et le contrat de licence comprennent une liste des fichiers ODBC que vous pouvez redistribuer.  
  
 Consultez la documentation relative aux pilotes ODBC que vous voulez distribuer.  Vous devez déterminer les DLL et autres fichiers que vous voulez distribuer.  
  
 Lisez également [Installation de la prise en charge des bases de données](../../data/installing-database-support-mfc-atl.md) pour des informations sur les composants et les pilotes ODBC, ainsi que [Redistribution des contrôles](../../data/ado-rdo/redistributing-controls.md), qui explique comment redistribuer les contrôles ActiveX.  
  
 De plus, vous devez souvent inclure un autre fichier :  le fichier Odbccr32.dll, qui est la bibliothèque de curseurs ODBC.  Cette bibliothèque offre la possibilité aux pilotes de niveau 1 de défiler vers l'avant et vers l'arrière.  Elle permet aussi de prendre en charge les instantanés.  Pour plus d'informations sur la bibliothèque de curseurs ODBC, consultez [ODBC : bibliothèque de curseurs ODBC](../../data/odbc/odbc-the-odbc-cursor-library.md).  
  
 Pour plus d'informations sur l'utilisation de ODBC avec les classes de base de données, consultez les rubriques suivantes :  
  
-   [ODBC : bibliothèque de curseurs ODBC](../../data/odbc/odbc-the-odbc-cursor-library.md)  
  
-   [ODBC : configuration d'une source de données ODBC](../../data/odbc/odbc-configuring-an-odbc-data-source.md)  
  
-   [ODBC : appel direct de fonctions API ODBC](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)  
  
## Voir aussi  
 [Éléments fondamentaux relatifs à ODBC](../../data/odbc/odbc-basics.md)   
 [Administrateur ODBC](../../data/odbc/odbc-administrator.md)