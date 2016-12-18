---
title: "COLUMN_ENTRY | Microsoft Docs"
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
  - "COLUMN_ENTRY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_ENTRY (macro)"
ms.assetid: a10aef29-6d70-49ec-b572-5b5c4abe1b46
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COLUMN_ENTRY
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une liaison entre l'ensemble de lignes et une colonne spécifique dans l'ensemble de lignes.  
  
## Syntaxe  
  
```  
  
COLUMN_ENTRY(  
nOrdinal  
,   
data  
 )  
  
```  
  
#### Paramètres  
 Consultez [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) dans le *Guide de référence pour programmeur OLE DB*.  
  
 `nOrdinal`  
 \[in\] Le numéro de colonne.  
  
 `data`  
 \[in\] Le membre de données correspondant dans l'article utilisateur.  
  
## Notes  
 La macro `COLUMN_ENTRY` est utilisée dans les emplacements suivants :  
  
-   Entre les macros [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md) et [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md).  
  
-   Entre [DEBUT\_ACCESSEUR](../../data/oledb/begin-accessor.md) et les macros [FIN\_ACCESSEUR](../../data/oledb/end-accessor.md).  
  
-   Entre les macros [BEGIN\_PARAM\_MAP](../../data/oledb/begin-param-map.md) et [END\_PARAM\_MAP](../../data/oledb/end-param-map.md).  
  
## Exemple  
 Consultez les exemples dans les rubriques macro, [DEBUT\_COLONNE\_MAPPAGE](../../data/oledb/begin-column-map.md) et [DEBUT\_ACCESSOIRE\_MAPPAGE](../../data/oledb/begin-accessor-map.md).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN\_ENTRY\_EX](../../data/oledb/column-entry-ex.md)   
 [COLUMN\_ENTRY\_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH](../../data/oledb/column-entry-ps-length.md)   
 [COLUMN\_ENTRY\_LENGTH](../../data/oledb/column-entry-length.md)   
 [COLUMN\_ENTRY\_LENGTH\_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH\_STATUS](../../data/oledb/column-entry-ps-length-status.md)   
 [COLUMN\_ENTRY\_STATUS](../../data/oledb/column-entry-status.md)   
 [COLUMN\_ENTRY\_PS\_STATUS](../../data/oledb/column-entry-ps-status.md)   
 [COLUMN\_ENTRY\_TYPE](../../data/oledb/column-entry-type.md)   
 [COLUMN\_ENTRY\_TYPE\_SIZE](../../data/oledb/column-entry-type-size.md)   
 [END\_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)