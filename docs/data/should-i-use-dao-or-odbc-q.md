---
title: "Dois-je utiliser DAO ou ODBC&#160;? | Microsoft Docs"
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
  - "DAO (C++), différences par rapport à ODBC"
  - "classes de base de données (C++), DAO"
  - "classes de base de données (C++), ODBC"
  - "ODBC (C++), différences par rapport à DAO"
ms.assetid: 9f67613f-0056-4ece-8c3a-9872e9563d57
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Dois-je utiliser DAO ou ODBC&#160;?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Dans Visual C\+\+ .NET, les Assistants et l'environnement Visual C\+\+ ne prennent plus en charge DAO \(même si les classes DAO sont incluses et que vous pouvez toujours les utiliser\).  Microsoft vous recommande d'utiliser les modèles OLE DB ou ODBC pour vos nouveaux projets.  Vous ne devez utiliser DAO que dans les applications existantes.  
  
 Quel jeu de classes MFC devez\-vous utiliser ?  Tout dépend de vos besoins :  
  
-   Utilisez les classes ODBC si vous travaillez exclusivement avec des sources de données ODBC, notamment dans les configurations client\-serveur, où les classes ODBC MFC offrent de meilleures performances.  
  
-   Utilisez les classes DAO si vous travaillez essentiellement avec les bases de données Microsoft Jet \(.mdb\) ou d'autres formats de bases de données que le moteur de bases de données Microsoft Jet peut lire directement.  Pour obtenir la liste de ces bases de données, consultez [À quelles bases de données puis\-je accéder avec DAO et ODBC ?](../data/what-data-sources-can-i-access-with-dao-and-odbc-q.md)  
  
-   Accédez aux sources de données ODBC via les classes DAO lorsque vous souhaitez tirer parti de la vitesse du moteur de bases de données Microsoft Jet et des fonctionnalités supplémentaires des classes DAO.  
  
    > [!NOTE]
    >  DAO requiert de l'espace supplémentaire sur le disque dur.  
  
 Les classes DAO offrent les avantages suivants :  
  
-   performances accrues dans certains cas, notamment lors de l'utilisation de bases de données Microsoft Jet \(.mdb\) ;  
  
-   compatibilité avec les classes ODBC et avec Microsoft Access Basic et Microsoft Visual Basic ;  
  
-   accès aux règles de validation ;  
  
-   possibilité de spécifier des relations entre les tables ;  
  
-   modèle d'accès aux données plus riche, avec la prise en charge des langages de définition de données \(DDL\) et de manipulation de données \(DML\).  Pour plus d'informations, consultez [Définition et manipulation de base de données](../data/are-ddl-and-dml-supported-q.md).  
  
 Le tableau suivant résume les différences clés pour vous aider à choisir.  
  
### Choix entre les classes ODBC et DAO MFC  
  
|Fonctionnalité|Avec les classes DAO ?|Avec les classes ODBC ?|  
|--------------------|----------------------------|-----------------------------|  
|Accès aux fichiers .MDB|Oui|Oui|  
|Accès aux sources de données ODBC|Oui|Oui|  
|Disponibilité pour 16 bits|Non|Oui|  
|Disponibilité pour 32 bits|Oui|Oui|  
|Disponibilité pour 64 bits|Non|Oui|  
|Compactage de base de données|Oui|Non|  
|Prise en charge du moteur de base de données|Moteur de bases de données Microsoft Jet|Système SGBD cible|  
|Prise en charge DDL|Oui|Uniquement par l'intermédiaire d'appels ODBC directs|  
|Prise en charge DML|Oui|Oui|  
|Nature de l'implémentation MFC|« Wrapper » des fonctions DAO de base|Abstraction simplifiée plutôt qu'un « wrapper » de l'interface API ODBC|  
|Optimisation pour|Fichiers .mdb \(Microsoft Access\)|Tout système SGBD pour lequel vous avez un pilote, notamment dans les configurations client\-serveur|  
|Prise en charge des transactions|Par solution, ou pour les données ODBC, par base de données|Par base de données|  
  
 N'oubliez pas que les fonctionnalités des pilotes ODBC varient.  Pour plus d'informations, consultez le *Guide de référence du programmeur* ODBC et le fichier d'aide du pilote ODBC.  
  
## Voir aussi  
 [Forum aux questions sur l'accès aux données](../data/data-access-frequently-asked-questions-mfc-data-access.md)