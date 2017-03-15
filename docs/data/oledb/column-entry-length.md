---
title: "COLUMN_ENTRY_LENGTH | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COLUMN_ENTRY_LENGTH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_ENTRY_LENGTH (macro)"
ms.assetid: 1758babf-204c-4d1d-b82a-f9a607072e9a
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# COLUMN_ENTRY_LENGTH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une liaison entre l'ensemble de lignes et une colonne spécifique dans la base de données.  
  
## Syntaxe  
  
```  
  
COLUMN_ENTRY_LENGTH(  
nOrdinal  
,   
data  
,   
length  
 )  
  
```  
  
#### Paramètres  
 Consultez [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) dans le *Guide de référence pour programmeur OLE DB*.  
  
 `nOrdinal`  
 \[in\] nombre de colonne, en commençant par un.  Le signet correspond à la colonne zéro.  
  
 `data`  
 \[in\] le membre de données correspondant dans l'article utilisateur.  
  
 *length*  
 \[in\] la variable à lier à la longueur de la colonne.  
  
## Notes  
 La macro prend en charge la variable *de longueur*.  C'est utilisé dans les endroits suivants :  
  
-   Entre [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md) et les macros [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md).  
  
-   Entre [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md) et les macros [END\_ACCESSOR](../../data/oledb/end-accessor.md).  
  
-   Entre [BEGIN\_PARAM\_MAP](../../data/oledb/begin-param-map.md) et les macros [END\_PARAM\_MAP](../../data/oledb/end-param-map.md).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN\_ENTRY\_EX](../../data/oledb/column-entry-ex.md)   
 [COLUMN\_ENTRY\_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH](../../data/oledb/column-entry-ps-length.md)   
 [COLUMN\_ENTRY\_LENGTH\_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH\_STATUS](../../data/oledb/column-entry-ps-length-status.md)   
 [COLUMN\_ENTRY\_STATUS](../../data/oledb/column-entry-status.md)   
 [COLUMN\_ENTRY\_PS\_STATUS](../../data/oledb/column-entry-ps-status.md)   
 [END\_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)