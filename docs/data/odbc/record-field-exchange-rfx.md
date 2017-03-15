---
title: "Record Field Exchange (RFX) | Microsoft Docs"
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
  - "données (MFC)"
  - "données (MFC), déplacer entre différents recordsets et sources"
  - "classes de base de données (C++), RFX"
  - "ODBC (C++), RFX"
  - "RFX (ODBC) (C++)"
ms.assetid: f5ddfbf0-2901-48d7-9848-4fb84de3c7ee
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Record Field Exchange (RFX)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les classes de base de données ODBC MFC automatisent le transfert de données entre la source de données et un objet [recordset](../../data/odbc/recordset-odbc.md).  Lorsque vous dérivez une classe de [CRecordset](../../mfc/reference/crecordset-class.md) et n'utilisez pas l'extraction de lignes en bloc, les données sont transférées par le mécanisme RFX \(Record Field eXchange\).  
  
> [!NOTE]
>  Si vous avez implémenté l'extraction de lignes en bloc dans une classe `CRecordset` dérivée, alors l'infrastructure utilise le mécanisme RFX en bloc \(Bulk RFX\) pour transférer les données.  Pour plus d'informations, consultez [Recordset : extraction globale d'enregistrements \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 RFX est similaire à DDX \(Dialog Data eXchange\).  Le transfert de données entre une source de données et les données membres de type champ d'un recordset nécessite plusieurs appels à la fonction [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) du recordset et une importante interaction entre l'infrastructure et [ODBC](../../data/odbc/odbc-basics.md).  Le mécanisme RFX est de type sécurisé et vous épargne d'avoir à appeler les fonctions ODBC comme **::SQLBindCol**.  Pour plus d'informations sur DDX, consultez [Échange et validation de données de boîtes de dialogue](../../mfc/dialog-data-exchange-and-validation.md).  
  
 RFX fonctionne en grande partie de façon transparente.  Si vous déclarez les classes du recordset à l'aide de l'Assistant Création d'applications MFC ou de **Ajouter une classe** \(comme indiqué dans [Ajout d'un consommateur ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)\), RFX est intégré automatiquement aux classes.  Votre classe recordset doit être dérivée de la classe de base `CRecordset` fournie par l'infrastructure.  L'Assistant Création d'applications MFC permet de créer une classe du recordset initiale.  **Add Class** permet d'ajouter toute autre classe du recordset dont vous avez besoin.  Pour plus d'informations et des exemples, consultez [Ajout d'un consommateur ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md).  
  
 Vous devez manuellement ajouter du code RFX si vous voulez :  
  
-   Utiliser des requêtes paramétrées.  Pour plus d'informations, consultez [Recordset : paramétrage d'un recordset \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
-   Effectuer des jointures \(utilisation d'un seul recordset pour des colonnes provenant de deux ou plusieurs tables\).  Pour plus d'informations, consultez [Recordset : création d'une jointure \(ODBC\)](../../data/odbc/recordset-performing-a-join-odbc.md).  
  
-   Lier dynamiquement les colonnes de données.  Cette opération est moins courante que la paramétrisation.  Pour plus d'informations, consultez [Recordset : liaison dynamique des colonnes de données \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
 Pour des informations plus détaillées sur RFX, consultez [Record Field Exchange : fonctionnement de RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 Les rubriques suivantes décrivent en détail l'utilisation des objets Recordset :  
  
-   [Record Field Exchange : utilisation de RFX](../../data/odbc/record-field-exchange-using-rfx.md)  
  
-   [Record Field Exchange : utilisation des fonctions RFX](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)  
  
-   [Record Field Exchange : fonctionnement de RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)  
  
## Voir aussi  
 [ODBC \(Open Database Connectivity\)](../../data/odbc/open-database-connectivity-odbc.md)   
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [MFC ODBC, consommation](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [Prise en charge des bases de données, Assistant Application MFC](../../mfc/reference/database-support-mfc-application-wizard.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)