---
title: "COLUMN_ENTRY_PS_LENGTH_STATUS | Microsoft Docs"
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
  - "COLUMN_ENTRY_PS_LENGTH_STATUS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_ENTRY_PS_LENGTH_STATUS (macro)"
ms.assetid: 04291671-329d-4974-b04e-36ef3f037787
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COLUMN_ENTRY_PS_LENGTH_STATUS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une liaison entre l'ensemble de lignes et une colonne spécifique dans la base de données.  
  
## Syntaxe  
  
```  
  
COLUMN_ENTRY_PS_LENGTH_STATUS(  
nOrdinal  
,   
nPrecision  
,   
nScale  
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
  
 `nPrecision`  
 \[in\] La précision maximale de la colonne que vous souhaitez lier.  
  
 `nScale`  
 \[in\] L'échelle de la colonne que vous souhaitez lier.  
  
 `data`  
 \[in\] Le membre de données correspondant dans l'article utilisateur.  
  
 *length*  
 \[in\] La variable à lier à la longueur de la colonne.  
  
 *status*  
 \[in\] la variable à lier à l'état de la colonne.  
  
## Notes  
 Vous permet de spécifier la précision et l'échelle de la colonne que vous souhaitez lier.  Utilisez la macro lorsque vous voulez prendre en charge les variables de longueur et d'état.  C'est utilisé dans les endroits suivants :  
  
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
 [COLUMN\_ENTRY\_LENGTH](../../data/oledb/column-entry-length.md)   
 [COLUMN\_ENTRY\_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH](../../data/oledb/column-entry-ps-length.md)   
 [COLUMN\_ENTRY\_LENGTH\_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN\_ENTRY\_STATUS](../../data/oledb/column-entry-status.md)   
 [COLUMN\_ENTRY\_PS\_STATUS](../../data/oledb/column-entry-ps-status.md)   
 [END\_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)