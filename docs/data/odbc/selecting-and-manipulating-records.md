---
title: "S&#233;lection et manipulation d&#39;enregistrements | Microsoft Docs"
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
  - "ODBC (recordsets), sélectionner des enregistrements"
  - "sélection des enregistrements, classes ODBC MFC"
  - "enregistrements, sélectionner"
ms.assetid: 7f0b3a4a-9941-4475-a612-9ec8d15b7691
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# S&#233;lection et manipulation d&#39;enregistrements
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Normalement, lorsque vous sélectionnez des enregistrements dans une source de données à l'aide d'une instruction SQL **SELECT**, vous obtenez un jeu de résultats, un recordset d'une table ou d'une requête.  Avec les classes de base de données, vous utilisez un objet recordset pour sélectionner et accéder à ce jeu de résultats.  C'est un objet d'une classe spécifique à l'application que vous dérivez de la classe [CRecordset](../../mfc/reference/crecordset-class.md).  Lorsque vous définissez une classe de recordset, vous spécifiez la source de données à laquelle elle sera associée, la table à utiliser et les colonnes de la table.  L'Assistant Création d'applications MFC ou **Ajout de classes** \(décrit dans [Ajout d'un consommateur ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)\) crée une classe avec une connexion à une source de données spécifique.  Les Assistants écrivent la fonction membre [GetDefaultSQL](../Topic/CRecordset::GetDefaultSQL.md) de la classe `CRecordset` pour retourner le nom de la table.  Pour plus d'informations sur l'utilisation des Assistants pour créer des classes de recordsets, consultez [Prise en charge des bases de données, Assistant Application MFC](../../mfc/reference/database-support-mfc-application-wizard.md) et [Ajout d'un consommateur ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md).  
  
 Lorsque vous utilisez un objet [CRecordset](../../mfc/reference/crecordset-class.md) lors de l'exécution, vous pouvez :  
  
-   examiner les champs de données de l'enregistrement en cours ;  
  
-   filtrer ou trier le recordset ;  
  
-   personnaliser l'instruction SQL **SELECT** par défaut ;  
  
-   visualiser successivement les enregistrements sélectionnés ;  
  
-   ajouter, mettre à jour ou supprimer des enregistrements \(si la source de données et le recordset sont tous deux modifiables\) ;  
  
-   tester si le recordset permet d'effectuer de nouvelles requêtes et actualiser le contenu du recordset.  
  
 Lorsque vous avez terminé d'utiliser l'objet Recordset, fermez\-le et détruisez\-le.  Pour plus d'informations sur les recordsets, consultez [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md).  
  
## Voir aussi  
 [ODBC et MFC](../../data/odbc/odbc-and-mfc.md)