---
title: "Recordset&#160;: ajout global d&#39;enregistrements (ODBC) | Microsoft Docs"
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
  - "ajouts d'enregistrements en bloc aux recordsets"
  - "ODBC (recordsets), ajouter des enregistrements"
  - "recordsets, ajouter des enregistrements"
ms.assetid: 4685f656-14b9-4f10-a1c5-147b2b89a0b4
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset&#160;: ajout global d&#39;enregistrements (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique s'applique aux classes ODBC MFC.  
  
 La classe [CRecordset](../../mfc/reference/crecordset-class.md) MFC dispose d'une nouvelle optimisation qui améliore son efficacité quand vous ajoutez en bloc de nouveaux enregistrements à une table.  
  
> [!NOTE]
>  Cette rubrique s'applique aux objets dérivés de `CRecordset` dans lesquels l'extraction de lignes en bloc n'a pas été implémentée.  Si vous utilisez l'extraction de lignes en bloc, consultez [Recordset : extraction globale d'enregistrements \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Une nouvelle option du paramètre **dwOptions** de la fonction membre [CRecordset::Open](../Topic/CRecordset::Open.md), **optimizeBulkAdd**, améliore les performances lorsque vous ajoutez plusieurs enregistrements à la suite sans appeler **Requery** ou **Close**.  Seuls les champs « dirty » \(modifiés\) avant le premier appel de **Update** sont marqués comme « dirty » \(modifiés\) pour les appels suivants de `AddNew`\/**Update**.  
  
 Si vous utilisez les classes de base de données pour bénéficier de la fonction API ODBC **::SQLSetPos** lors de l'ajout, de la modification ou de la suppression d'enregistrements, cette optimisation est superflue.  
  
 Si la bibliothèque de curseurs ODBC est chargée ou que le pilote ODBC ne prend pas en charge l'ajout, la modification ou la suppression via **::SQLSetPos**, cette optimisation doit améliorer les performances de l'ajout en bloc.  Pour activer l'optimisation, définissez le paramètre **dwOptions** dans l'appel **Open** de votre recordset avec la valeur suivante :  
  
```  
appendOnly | optimizeBulkAdd  
```  
  
## Voir aussi  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset : ajout, modification et suppression d'enregistrements \(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)   
 [Recordset : verrouillage d'enregistrements \(ODBC\)](../../data/odbc/recordset-locking-records-odbc.md)