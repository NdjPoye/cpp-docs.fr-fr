---
title: "Fonctions Record Field Exchange (RFX) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO (Data Access Objects), échange de champs d’enregistrements (DFX)"
  - "ODBC, fonctions d’échange de données RFX en bloc"
  - "RFX (échange de champs d’enregistrements), classes ODBC"
  - "DFX (échange de champs d’enregistrements DAO), fonctions d’échange de données"
  - "DFX (fonctions)"
  - "fonctions RFX en bloc"
  - "processus DFX (échange de champs d’enregistrements DAO)"
  - "RFX (échange de champs d’enregistrements), classes DAO"
  - "ODBC, RFX"
  - "RFX (échange de champs d’enregistrements), fonctions d’échange de données"
  - "RFX (échange de champs d’enregistrements)"
ms.assetid: 6e4c5c1c-acb7-4c18-bf51-bf7959a696cd
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Fonctions Record Field Exchange (RFX)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique répertorie les fonctions d’échange de champs d’enregistrements \([RFX](#_mfc_rfx_functions_.28.odbc.29), [RFX en bloc](#_mfc_bulk_rfx_functions_.28.odbc.29) et [DFX](#_mfc_dfx_functions_.28.dao.29)\) permettant d’automatiser le transfert de données entre un objet recordset et sa source de données et d’effectuer d’autres opérations sur les données.  
  
 Si vous utilisez les classes ODBC et que vous avez implémenté l’extraction de lignes en bloc, vous devez remplacer manuellement la fonction membre `DoBulkFieldExchange` de `CRecordset` en appelant les fonctions RFX en bloc pour chaque membre de données correspondant à une colonne de source de données.  
  
 Si vous n’avez pas implémenté l’extraction de lignes en bloc dans les classes ODBC, ou si vous utilisez les classes DAO, ClassWizard remplace la fonction membre `DoFieldExchange` de `CRecordset` ou `CDaoRecordset` en appelant les fonctions RFX \(pour les classes ODBC\) ou les fonctions DFX \(pour les classes DAO\) pour chaque membre de données de champ de votre recordset.  
  
 Les fonctions d’échange de champs d’enregistrements transfèrent des données chaque fois que l’infrastructure appelle `DoFieldExchange` ou `DoBulkFieldExchange`. Chaque fonction transfère un type de données spécifique.  
  
 Pour plus d’informations sur l’utilisation de ces fonctions, consultez les articles [Record Field Exchange : fonctionnement de RFX \(ODBC\)](../../data/odbc/record-field-exchange-how-rfx-works.md). Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Pour les colonnes de données que vous liez dynamiquement, vous pouvez aussi appeler les fonctions RFX et DFX par vous\-même, comme expliqué dans les articles [Recordset : liaison dynamique des colonnes de données \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md). Par ailleurs, vous pouvez écrire vos propres routines RFX ou DFX personnalisées, comme l’explique la Note technique [43](../../mfc/tn043-rfx-routines.md) \(pour ODBC\) et la Note technique [53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) \(pour DAO\).  
  
 Pour obtenir un exemple de fonctions RFX et RFX en bloc telles qu’elles apparaissent dans les fonctions `DoFieldExchange` et `DoBulkFieldExchange`, consultez [RFX\_Text](../Topic/RFX_Text.md) et [RFX\_Text\_Bulk](../Topic/RFX_Text_Bulk.md). Les fonctions DFX sont très similaires aux fonctions RFX.  
  
### Fonctions RFX \(ODBC\)  
  
|||  
|-|-|  
|[RFX\_Binary](../Topic/RFX_Binary.md)|Transfère les tableaux d’octets de type [CByteArray](../../mfc/reference/cbytearray-class.md).|  
|[RFX\_Bool](../Topic/RFX_Bool.md)|Transfère les données de type Boolean.|  
|[RFX\_Byte](../Topic/RFX_Byte.md)|Transfère un seul octet de données.|  
|[RFX\_Date](../Topic/RFX_Date.md)|Transfère les données d’heure et de date à l’aide de [CTime](../../atl-mfc-shared/reference/ctime-class.md) ou **TIMESTAMP\_STRUCT**.|  
|[RFX\_Double](../Topic/RFX_Double.md)|Transfère les données de type Float double précision.|  
|[RFX\_Int](../Topic/RFX_Int.md)|Transfère les données de type Integer.|  
|[RFX\_Long](../Topic/RFX_Long.md)|Transfère les données de type Long Integer.|  
|[RFX\_LongBinary](../Topic/RFX_LongBinary.md)|Transfère les données BLOB avec un objet de la classe [CLongBinary](../../mfc/reference/clongbinary-class.md).|  
|[RFX\_Single](../Topic/RFX_Single.md)|Transfère les données de type Float.|  
|[RFX\_Text](../Topic/RFX_Text.md)|Transfère les données de type String.|  
  
### Fonctions RFX en bloc \(ODBC\)  
  
|||  
|-|-|  
|[RFX\_Binary\_Bulk](../Topic/RFX_Binary_Bulk.md)|Transfère les tableaux de données de type Byte.|  
|[RFX\_Bool\_Bulk](../Topic/RFX_Bool_Bulk.md)|Transfère les tableaux de données de type Boolean.|  
|[RFX\_Byte\_Bulk](../Topic/RFX_Byte_Bulk.md)|Transfère les tableaux d’octets uniques.|  
|[RFX\_Date\_Bulk](../Topic/RFX_Date_Bulk.md)|Transfère les tableaux de données de type **TIMESTAMP\_STRUCT**.|  
|[RFX\_Double\_Bulk](../Topic/RFX_Double_Bulk.md)|Transfère les tableaux de données à virgule flottante double précision.|  
|[RFX\_Int\_Bulk](../Topic/RFX_Int_Bulk.md)|Transfère les tableaux de données de type Integer.|  
|[RFX\_Long\_Bulk](../Topic/RFX_Long_Bulk.md)|Transfère les tableaux de données de type Long Integer.|  
|[RFX\_Single\_Bulk](../Topic/RFX_Single_Bulk.md)|Transfère les tableaux de données à virgule flottante.|  
|[RFX\_Text\_Bulk](../Topic/RFX_Text_Bulk.md)|Transfère les tableaux de données de type **LPSTR**.|  
  
### Fonctions DFX \(DAO\)  
  
|||  
|-|-|  
|[DFX\_Binary](../Topic/DFX_Binary.md)|Transfère les tableaux d’octets de type [CByteArray](../../mfc/reference/cbytearray-class.md).|  
|[DFX\_Bool](../Topic/DFX_Bool.md)|Transfère les données de type Boolean.|  
|[DFX\_Byte](../Topic/DFX_Byte.md)|Transfère un seul octet de données.|  
|[DFX\_Currency](../Topic/DFX_Currency.md)|Transfère les données de devise de type [COleCurrency](../../mfc/reference/colecurrency-class.md).|  
|[DFX\_DateTime](../Topic/DFX_DateTime.md)|Transfère les données de date et d’heure de type [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md).|  
|[DFX\_Double](../Topic/DFX_Double.md)|Transfère les données de type Float double précision.|  
|[DFX\_Long](../Topic/DFX_Long.md)|Transfère les données de type Long Integer.|  
|[DFX\_LongBinary](../Topic/DFX_LongBinary.md)|Transfère les données BLOB avec un objet de la classe `CLongBinary`. Pour DAO, il est recommandé d’utiliser plutôt [DFX\_Binary](../Topic/DFX_Binary.md).|  
|[DFX\_Short](../Topic/DFX_Short.md)|Transfère les données de type Short Integer.|  
|[DFX\_Single](../Topic/DFX_Single.md)|Transfère les données de type Float.|  
|[DFX\_Text](../Topic/DFX_Text.md)|Transfère les données de type String.|  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)   
 [CRecordset::DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md)   
 [CRecordset::DoBulkFieldExchange](../Topic/CRecordset::DoBulkFieldExchange.md)   
 [CDaoRecordset::DoFieldExchange](../Topic/CDaoRecordset::DoFieldExchange.md)