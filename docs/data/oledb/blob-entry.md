---
title: "BLOB_ENTRY | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BLOB_ENTRY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BLOB_ENTRY (macro)"
ms.assetid: 89e40678-0869-49ed-b502-0fa2630a9081
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# BLOB_ENTRY
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Used with `BEGIN_COLUMN_MAP` and `END_COLUMN_MAP` to bind a binary large object \([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)\).  
  
## Syntaxe  
  
```  
  
BLOB_ENTRY(  
nOrdinal  
,  
 IID  
,   
flags  
,   
data  
 )  
  
```  
  
#### Paramètres  
 `nOrdinal`  
 \[in\] The column number.  
  
 *IID*  
 \[in\] Interface GUID, such as **IDD\_ISequentialStream**, used to retrieve the BLOB.  
  
 `flags`  
 \[in\] Storage\-mode flags as defined by the OLE Structured Storage model \(for example, **STGM\_READ**\).  
  
 `data`  
 \[in\] The corresponding data member in the user record.  
  
## Exemple  
 See [How Can I Retrieve a BLOB?](../../data/oledb/retrieving-a-blob.md).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB\_ENTRY\_LENGTH](../../data/oledb/blob-entry-length.md)   
 [BLOB\_ENTRY\_LENGTH\_STATUS](../../data/oledb/blob-entry-length-status.md)   
 [BLOB\_ENTRY\_STATUS](../../data/oledb/blob-entry-status.md)