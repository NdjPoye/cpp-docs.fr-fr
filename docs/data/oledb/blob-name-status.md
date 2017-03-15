---
title: "BLOB_NAME_STATUS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BLOB_NAME_STATUS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BLOB_NAME_STATUS (macro)"
ms.assetid: 4564e4a0-8e5e-436a-bd1e-012d2a1b8642
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# BLOB_NAME_STATUS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisé avec `BEGIN_COLUMN_MAP` et `END_COLUMN_MAP` pour lier un grand objet binaire \([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)\).  Similaire à [BLOB\_NAME](../../data/oledb/blob-name.md), sauf que la macro obtient également l'état de la colonne de données BLOB.  
  
## Syntaxe  
  
```  
  
BLOB_NAME_STATUS(  
pszName  
,   
IID  
,   
flags  
,   
data  
, status )  
```  
  
#### Paramètres  
 `pszName`  
 \[in\] Un pointeur sur le nom de colonne.  Le nom doit être une chaîne Unicode.  Vous pouvez y parvenir en mettant un « L » devant le nom, par exemple : `L"MyColumn"`.  
  
 *IID*  
 \[in\] interface GUID, tel que **IDD\_ISequentialStream**, utilisée pour récupérer le BLOB.  
  
 `flags`  
 \[in\] indicateurs de mode de stockage tels qu'ils sont définis par le modèle de stockage structuré OLE \(par exemple, **STGM\_READ**\).  
  
 `data`  
 \[in\] Le membre de données correspondant dans le registre d'utilisateur.  
  
 *status*  
 \[out\] Le statut du champ BLOB.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB\_NAME](../../data/oledb/blob-name.md)   
 [BLOB\_NAME\_LENGTH](../../data/oledb/blob-name-length.md)   
 [BLOB\_NAME\_LENGTH\_STATUS](../../data/oledb/blob-name-length-status.md)