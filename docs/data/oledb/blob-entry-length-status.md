---
title: "BLOB_ENTRY_LENGTH_STATUS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BLOB_ENTRY_LENGTH_STATUS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BLOB_ENTRY_LENGTH_STATUS (macro)"
ms.assetid: 09da67de-421b-4853-9a26-760e38324502
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# BLOB_ENTRY_LENGTH_STATUS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisé avec `BEGIN_COLUMN_MAP` ou `END_COLUMN_MAP` pour lier un grand objet binaire \([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)\).  Similaire à [BLOB\_ENTRY](../../data/oledb/blob-entry.md), sauf que la macro obtient également la longueur et l'état de la colonne BLOB.  
  
## Syntaxe  
  
```  
  
BLOB_ENTRY_LENGTH_STATUS(  
nOrdinal  
,   
IID  
,   
flags  
,   
data  
, length, status )  
```  
  
#### Paramètres  
 `nOrdinal`  
 \[in\] Le numéro de colonne.  
  
 *IID*  
 \[in\] interface GUID, tel que **IDD\_ISequentialStream**, utilisé pour récupérer l'objet BLOB.  
  
 `flags`  
 \[in\] indicateurs de mode de stockage tels qu'ils sont définis par le modèle de stockage structuré OLE \(par exemple, **STGM\_READ**\).  
  
 `data`  
 \[in\] Le membre de données correspondant dans l'article utilisateur.  
  
 *length*  
 \[out\] longueur réelle \(en octets\) de la colonne BLOB.  
  
 *status*  
 \[out\] l'état de la colonne de données BLOB.  
  
## Exemple  
 Voir [Comment puis\-je récupérer un objet BLOB ?](../../data/oledb/retrieving-a-blob.md).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB\_ENTRY](../../data/oledb/blob-entry.md)   
 [BLOB\_ENTRY\_LENGTH](../../data/oledb/blob-entry-length.md)   
 [BLOB\_ENTRY\_STATUS](../../data/oledb/blob-entry-status.md)