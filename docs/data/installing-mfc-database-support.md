---
title: "Installation de la prise en charge des bases de donn&#233;es MFC | Microsoft Docs"
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
  - "DAO (C++), installer les composants"
  - "bases de données (C++), installer la prise en charge des bases de données"
  - "bases de données (C++), MFC"
  - "installer DAO"
  - "installer ODBC"
  - "ODBC (composants) (C++), installer"
  - "ODBC (pilotes) (C++), installer"
ms.assetid: a6c2fc84-9e0e-4f39-a464-0bcbc415b946
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Installation de la prise en charge des bases de donn&#233;es MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

##  <a name="_core_odbc_drivers_installed"></a> Pilotes ODBC installés  
 Le programme d'installation installe les pilotes ODBC suivants :  
  
-   Pilote Microsoft Access  
  
-   Pilote Microsoft dBASE  
  
-   Pilote Microsoft Excel  
  
-   Pilote Microsoft FoxPro VFP  
  
-   Pilote Microsoft Visual FoxPro  
  
-   Pilote Microsoft ODBC pour Oracle  
  
-   Pilote Microsoft Paradox  
  
-   Pilote Microsoft Text  
  
-   Pilote Microsoft SQL Server  
  
 Pour plus d'informations sur l'obtention de pilotes supplémentaires et pour la liste des pilotes ODBC contenus dans cette version de Visual C\+\+, consultez [Liste de pilotes ODBC](../data/odbc/odbc-driver-list.md).  
  
##  <a name="_core_odbc_sdk_components_installed"></a> Composants du Kit de développement ODBC SDK installés  
 Visual C\+\+ comprend de nombreux composants ODBC clés, notamment les fichiers d'en\-tête, les bibliothèques, les DLL et les outils requis.  Ces composants incluent l'application du Panneau de configuration Administrateur ODBC, qui permet de configurer les sources de données ODBC, et le gestionnaire de pilotes ODBC.  Sont également compris des pilotes ODBC pour de nombreux SGBD courants, énumérés dans [Pilotes ODBC installés](#_core_odbc_drivers_installed).  
  
 Le Kit de développement ODBC SDK fournit des informations et des outils supplémentaires pour l'écriture et le test de pilotes ODBC.  Notez qu'à partir de Visual C\+\+ .NET, le Kit de développement ODBC SDK n'est plus inclus sur le média d'installation de Visual C\+\+ .NET ; il fait désormais partie intégrante du [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] avec Visual Studio .NET Prerequisites.  
  
##  <a name="_core_dao_sdk_components_installed"></a> Composants du Kit de développement DAO SDK installés  
  
> [!NOTE]
>  Microsoft recommande l'utilisation d'OLE DB ou d'ODBC pour les nouveaux projets.  La technologie DAO doit être réservée aux applications existantes.  
  
 Les composants suivants du Kit de développement DAO SDK sont installés par défaut :  
  
-   Microsoft Jet \(4.0 SP3\)  
  
-   Microsoft Jet \(3 x MDB\)  
  
-   Microsoft Jet \(1 x, 2 x\)  
  
-   Tous les formats de base de données répertoriés sous [À quelles bases de données puis\-je accéder avec DAO et ODBC ?](../data/what-data-sources-can-i-access-with-dao-and-odbc-q.md)  
  
 Dans Visual C\+\+ .NET, le Kit de développement DAO SDK est installé avec Visual Studio .NET Prerequisites.  Exécutez \\Jet\\Jetsetup.exe.  
  
> [!NOTE]
>  Microsoft recommande l'utilisation de Jet 4.0 Service Pack 3 \(version 2927.04\) ou version ultérieure.  Jet 4.0 Service Pack 3 fourni avec Windows 2000 et Windows ME.  Cette version de Jet réduit le nombre de versions de Jet à tester avec votre application.  Windows XP sera peut\-être commercialisé avec une autre version de Jet.  Consultez « Remarque à propos de la redistribution des composants DAO » dans [Redistribution des contrôles](../data/ado-rdo/redistributing-controls.md).  
  
 Si vous voulez installer d'autres composants du Kit de développement DAO SDK, tels que les classes C\+\+ du Kit de développement DAO SDK, des exemples de fichiers ou la version d'aide Windows du fichier d'aide de DAO, installez le Kit de développement DAO SDK à partir du CD\-ROM Visual C\+\+ 6.0.  
  
 Pour les mises à jour et les nouveautés sur OLE DB, consultez le site Web universel d'accès aux données dans [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=121548](http://go.microsoft.com/fwlink/?LinkId=121548).  
  
## Voir aussi  
 [Programmation de l'accès aux données \(MFC\/ATL\)](../data/data-access-programming-mfc-atl.md)