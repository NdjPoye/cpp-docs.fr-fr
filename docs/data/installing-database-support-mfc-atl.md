---
title: "Installation de la prise en charge des bases de donn&#233;es (MFC/ATL) | Microsoft Docs"
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
  - "ATL (C++), prise en charge de la base de données"
  - "accès aux données (C++), installer la prise en charge des bases de données"
  - "bases de données (C++), installer la prise en charge des bases de données"
  - "installer la prise en charge des bases de données"
ms.assetid: 3820ba96-4fb8-4405-83dd-bb3bc5998667
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Installation de la prise en charge des bases de donn&#233;es (MFC/ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Quand vous exécutez le programme d'installation de Visual C\+\+ .NET, les composants de base de données suivants sont installés automatiquement :  
  
-   Tous les composants OLE DB ATL nécessaires.  Pour plus d'informations, consultez [Installation de la prise en charge des bases de données ATL](../data/installing-atl-database-support.md).  
  
-   Un ensemble de pilotes ODBC avec le gestionnaire de pilote ODBC et le programme d'administration ODBC.  Pour plus d'informations, consultez « Pilotes ODBC installés » et « Composants du Kit de développement ODBC installés » dans [Installation de la prise en charge des bases de données MFC](../data/installing-mfc-database-support.md).  
  
-   Composants nécessaires à partir du Kit de développement de logiciel \(SDK\) DAO.  Cela inclut les fichiers d'aide, qui ne sont pas intégrés à cette documentation.  Toutefois, si vous utilisez DAO, vous devez installer une version de Jet compatible avec votre système d'exploitation.  Pour plus d'informations, consultez « Composants du Kit de développement logiciel DAO installés » dans [Installation de la prise en charge des bases de données MFC](../data/installing-mfc-database-support.md).  
  
 Dans le cadre de l'installation de base, le programme d'installation installe également Microsoft Data Access Components \(MDAC\), qui est nécessaire pour prendre en charge la programmation de l'accès aux données dans Visual C\+\+ .NET.  
  
 Visual C\+\+ .NET installe le Kit de développement logiciel \(SDK\) MDAC 2.7.  Vous devez consulter le site web Microsoft Universal Data Access à l'adresse [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=121548](http://go.microsoft.com/fwlink/?LinkId=121548) pour obtenir les mises à jour et les informations relatives au kit SDK MDAC.  
  
 Si vous redistribuez des applications d'accès aux données, vous devez également avoir le programme de redistribution MDAC 2.7.  Le Kit de développement logiciel \(SDK\) MDAC 2.7 est conçu pour être utilisé avec le programme de redistribution MDAC 2.7 \(Mdac\_typ.exe\) inclus dans le répertoire MDAC sur le CD\-ROM Visual Studio .NET Prerequisites.  Vous pouvez également télécharger Mdac\_typ.exe à partir du lien de téléchargement du kit SDK MDAC 2.7 répertorié plus haut.  Pour plus d'informations sur la redistribution des composants, consultez [Redistribution des contrôles](../data/ado-rdo/redistributing-controls.md).  
  
## Voir aussi  
 [Accès aux données](../Topic/Data%20Access%20in%20Visual%20C++.md)