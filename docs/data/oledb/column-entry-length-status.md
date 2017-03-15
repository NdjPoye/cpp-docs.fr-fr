---
title: "COLUMN_ENTRY_LENGTH_STATUS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COLUMN_ENTRY_LENGTH_STATUS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_ENTRY_LENGTH_STATUS (macro)"
ms.assetid: 6069967c-4665-462b-b822-1e6c22b5bee1
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# COLUMN_ENTRY_LENGTH_STATUS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une liaison entre l'ensemble des lignes et une colonne spécifique dans la base de données.  
  
## Syntaxe  
  
```  
  
COLUMN_ENTRY_LENGTH_STATUS(  
nOrdinal  
,   
data  
,   
length  
,   
status  
 )  
  
```  
  
#### Paramètres  
 Consultez [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) dans le *Guide de référence pour programmeur OLE DB*.  
  
 `nOrdinal`  
 \[in\] Le numéro de colonne.  
  
 `data`  
 \[in\] Le membre de données correspondant dans le registre d'utilisateur.  
  
 *length*  
 \[in\] La variable à lier à la longueur de la colonne.  
  
 *status*  
 \[in\] La variable à lier à l'état de la colonne.  
  
## Notes  
 Utilisez la macro lorsque vous voulez prendre en charge les variables de longueur et d'état.  C'est utilisé dans les endroits suivants:  
  
-   Entre les macros [COMMENCER\_COLONNE\_MAPPAGE](../../data/oledb/begin-column-map.md) et [FIN\_COLONNE\_MAPPAGE](../../data/oledb/end-column-map.md).  
  
-   Entre les macros [DEBUT\_ACCESSEUR](../../data/oledb/begin-accessor.md) et [FIN\_ACCESSEUR](../../data/oledb/end-accessor.md).  
  
-   Entre les macros [DEBUT\_PARAMETRES\_MAPPAGE](../../data/oledb/begin-param-map.md) et [FIN\_PARAMETRES\_MAPPAGE](../../data/oledb/end-param-map.md).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN\_ENTRY\_EX](../../data/oledb/column-entry-ex.md)   
 [COLUMN\_ENTRY\_LENGTH](../../data/oledb/column-entry-length.md)   
 [COLUMN\_ENTRY\_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH](../../data/oledb/column-entry-ps-length.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH\_STATUS](../../data/oledb/column-entry-ps-length-status.md)   
 [COLUMN\_ENTRY\_STATUS](../../data/oledb/column-entry-status.md)   
 [COLUMN\_ENTRY\_PS\_STATUS](../../data/oledb/column-entry-ps-status.md)   
 [END\_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)