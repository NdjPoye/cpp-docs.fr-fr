---
title: "Programmation de l&#39;acc&#232;s aux donn&#233;es (MFC/ATL) | Microsoft Docs"
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
  - "données (C++), technologies d'accès aux données"
  - "accès aux données (C++), bibliothèques de classes pour les bases de données"
  - "bases de données (C++), MFC"
  - "MFC (C++), applications d'accès aux données"
  - "OLE DB (C++), technologies d'accès aux données"
ms.assetid: def97b2c-b5a6-445f-afeb-308050fd4852
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Programmation de l&#39;acc&#232;s aux donn&#233;es (MFC/ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ propose plusieurs manières de travailler avec des bases de données.  La meilleure méthode consiste à utiliser l'une des bibliothèques de classes telles que la bibliothèque ATL \(Active Template Library\) ou la bibliothèque MFC \(Microsoft Foundation Class\), qui simplifient l'utilisation des API de base de données.  
  
> [!NOTE]
>  Cette rubrique traite des technologies plus anciennes que vous pouvez utiliser pour la programmation des bases de données dans Visual C\+\+.  Pour plus d'informations sur la programmation de l'accès aux données à l'aide de Visual C\+\+ et SQL Server 2005, consultez [Accès aux données](../dotnet/data-access-using-adonet-cpp-cli.md), [Accès aux données dans Visual Studio](../Topic/Accessing%20data%20in%20Visual%20Studio.md) et [Creating SQL Server 2005 Objects In Managed Code](http://msdn.microsoft.com/fr-fr/5358a825-e19b-49aa-8214-674ce5fed1da).  
  
 Les classes de bibliothèques prennent en charge les types d'accès aux données suivants :  
  
-   ATL fournit des attributs de bases de données et des modèles OLE DB.  
  
-   MFC fournit la connectivité ODBC \(Open Database Connectivity\) et un pilote ODBC.  
  
 Ces bibliothèques fournissent des abstractions qui simplifient l'utilisation des bases de données, avec la vitesse, la puissance et la souplesse de C\+\+.  Ils intègrent votre travail d'accès aux données à l'infrastructure d'application de la bibliothèque.  
  
 En guise d'alternative, vous pouvez appeler directement des fonctions d'API de base de données à partir des Kits de développement logiciel \(SDK\) COM, ODBC ou DAO.  Pour plus d'informations sur la programmation directe avec les fonctions d'API COM, DAO ou ODBC, consultez le Kit SDK COM, DAO ou ODBC.  
  
 Utilisez ATL OLE DB si vous avez besoin d'accéder à des données quel que soit le format dans lequel elles sont stockées.  Utilisez les classes ODBC MFC quand vous n'utilisez pas de bases de données Microsoft Jet \(.mdb\) et que vous souhaitez travailler avec l'API ODBC pour bénéficier d'une indépendance complète de la source de données.  Utilisez les classes DAO MFC quand vous voulez travailler avec des bases de données Microsoft Jet \(.mdb\) ou avec des bases de données externes telles que des sources de données ODBC.  
  
> [!NOTE]
>  Microsoft recommande d'utiliser OLE DB ou ODBC pour les nouveaux projets.  DAO doit être utilisé uniquement pour la maintenance des applications existantes.  
  
 Outre l'écriture d'applications de bases de données autonomes, vous pouvez souvent utiliser une base de données de manière efficace dans d'autres genres de programmes comme support de stockage et de récupération pratique.  
  
|Pour en savoir plus sur|Voir|  
|-----------------------------|----------|  
|**Sélection d'une technologie de base de données**||  
|Différences entre ODBC et  DAO|[Dois\-je utiliser DAO ou ODBC ?](../data/should-i-use-dao-or-odbc-q.md)|  
|Utilisation de la Base de connaissances Microsoft pour rechercher d'autres articles sur les bases de données écrits par des techniciens du support technique|[Base de connaissances Microsoft](../data/where-can-i-find-microsoft-knowledge-base-articles-on-database-topics-q.md)|  
|**Prise en charge de base de données ATL \(OLE DB\)**||  
|Programmation OLE DB \(rubriques conceptuelles\)|[Vue d'ensemble de la programmation OLE DB](../data/oledb/ole-db-programming-overview.md)|  
|Utilisation des modèles du consommateur OLE DB \(rubriques conceptuelles\)|[Modèles du consommateur OLE DB](../data/oledb/ole-db-consumer-templates-cpp.md)|  
|Attributs du consommateur OLE DB|[Attributs du consommateur OLE DB](../windows/ole-db-consumer-attributes.md)|  
|Utilisation des modèles du fournisseur OLE DB \(rubriques conceptuelles\)|[Modèles du fournisseur OLE DB](../data/oledb/ole-db-provider-templates-cpp.md)|  
|Ajout d'un consommateur OLE DB à un projet MFC|[Création d'un consommateur OLE DB](../data/oledb/creating-an-ole-db-consumer.md)|  
|**Prise en charge des bases de données MFC \(ODBC et DAO\)**||  
|DAO et ODBC|[Que sont DAO et ODBC ?](../data/what-are-dao-and-odbc-q.md)|  
|Quand utiliser les classes de base de données MFC|[Quand dois\-je utiliser les classes de base de données ?](../data/when-should-i-use-the-database-classes-q.md)|  
|En savoir plus sur le modèle de programmation de base de données MFC|[Qu'est\-ce que le modèle de programmation de bases de données MFC ?](../data/what-is-the-mfc-database-programming-model-q.md)|  
|Choisir entre les classes DAO MFC et les classes ODBC MFC|[Dois\-je utiliser DAO ou ODBC ?](../data/should-i-use-dao-or-odbc-q.md)|  
|Sources de données accessibles avec DAO et ODBC|[À quelles sources de données puis\-je accéder avec DAO et ODBC ?](../data/what-data-sources-can-i-access-with-dao-and-odbc-q.md)|  
|ODBC \(Open Database Connectivity\)|[ODBC et MFC](../data/odbc/odbc-and-mfc.md)|  
|Indique si vous pouvez appeler des API DAO ou ODBC directement lors de l'utilisation des classes|[Puis\-je appeler DAO ou ODBC directement ?](../data/can-i-call-dao-or-odbc-directly-q.md)|  
|Pilotes ODBC fournis|[Liste de pilotes ODBC](../data/odbc/odbc-driver-list.md)|  
|Fonctionnement des classes de base de données avec l'architecture document\/vue MFC|[MFC : utilisation de classes de bases de données avec des documents et des vues](../data/mfc-using-database-classes-with-documents-and-views.md)|  
|Installation de la prise en charge des bases de données MFC ; pilotes ODBC installés dans Visual C\+\+ par défaut ; composants du Kit SDK ODBC et DAO installés|[Installation de la prise en charge des bases de données MFC](../data/installing-mfc-database-support.md)|  
|**Contrôles liés aux données \(ADO et RDO\)**||  
|Écriture d'un programme qui utilise des contrôles liés aux données|[Contrôles liés aux données \(ADO et RDO\)](../data/ado-rdo/data-bound-controls-ado-and-rdo.md)|  
|Liaison de données à l'aide de contrôles ActiveX|[Contrôles ActiveX MFC : utilisation de la liaison de données dans un contrôle ActiveX](../mfc/mfc-activex-controls-using-data-binding-in-an-activex-control.md)|  
|Distribution de contrôles ActiveX|[Contrôles ActiveX MFC : distribution de contrôles ActiveX](../mfc/mfc-activex-controls-distributing-activex-controls.md)|  
  
## Voir aussi  
 [Accès aux données](../Topic/Data%20Access%20in%20Visual%20C++.md)