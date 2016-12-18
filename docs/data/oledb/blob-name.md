---
title: "BLOB_NAME | Microsoft Docs"
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
  - "BLOB_NAME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BLOB_NAME (macro)"
ms.assetid: 757acd0d-946d-447d-937e-94ecd700ba38
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# BLOB_NAME
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisé avec `BEGIN_COLUMN_MAP` et `END_COLUMN_MAP` pour lier un grand objet binaire \([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)\).  Similaire à [BLOB\_ENTRY](../../data/oledb/blob-entry.md), sauf que la macro accepte un nom de colonne au lieu d'un numéro de colonne.  
  
## Syntaxe  
  
```  
  
BLOB_NAME(  
pszName  
,   
IID  
,   
flags  
,   
data )  
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
  
## Exemple  
 Voir [Comment puis\-je récupérer un objet BLOB ?](../../data/oledb/retrieving-a-blob.md).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB\_NAME\_LENGTH](../../data/oledb/blob-name-length.md)   
 [BLOB\_NAME\_LENGTH\_STATUS](../../data/oledb/blob-name-length-status.md)   
 [BLOB\_NAME\_STATUS](../../data/oledb/blob-name-status.md)