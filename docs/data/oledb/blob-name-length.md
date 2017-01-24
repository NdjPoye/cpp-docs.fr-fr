---
title: "BLOB_NAME_LENGTH | Microsoft Docs"
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
  - "BLOB_NAME_LENGTH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BLOB_NAME_LENGTH (macro)"
ms.assetid: 38150260-a127-486d-a7ab-0d01b731b6fd
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# BLOB_NAME_LENGTH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisé avec `BEGIN_COLUMN_MAP` et `END_COLUMN_MAP` pour lier un grand objet binaire \([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)\).  Similaire à [BLOB\_NAME](../../data/oledb/blob-name.md), mais cette macro obtient également la longueur en octets de la colonne de données BLOB.  
  
## Syntaxe  
  
```  
  
BLOB_NAME_LENGTH(  
pszName  
,   
IID  
,   
flags  
,   
data  
,   
length )  
```  
  
#### Paramètres  
 `pszName`  
 \[in\] Un pointeur sur le nom de colonne.  Le nom doit être une chaîne Unicode.  Vous pouvez y parvenir en mettant un « L » devant le nom, par exemple : `L"MyColumn"`.  
  
 *IID*  
 \[in\] interface GUID, tel que **IDD\_ISequentialStream**, utilisée pour récupérer le BLOB.  
  
 `flags`  
 \[in\] indicateurs de mode de stockage tels qu'ils sont définis par le modèle de stockage structuré OLE \(par exemple, **STGM\_READ**\).  
  
 `data`  
 \[in\] Le membre de données correspondant dans l'article utilisateur.  
  
 *length*  
 \[out\] longueur \(réelle\) en octets de la colonne BLOB.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB\_NAME](../../data/oledb/blob-name.md)   
 [BLOB\_NAME\_LENGTH\_STATUS](../../data/oledb/blob-name-length-status.md)   
 [BLOB\_NAME\_STATUS](../../data/oledb/blob-name-status.md)