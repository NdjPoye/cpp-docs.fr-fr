---
title: "COLUMN_ENTRY_PS | Microsoft Docs"
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
  - "COLUMN_ENTRY_PS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_ENTRY_PS (macro)"
ms.assetid: 563c12b0-3376-49d5-a14f-aa68d1e63a7a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COLUMN_ENTRY_PS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une liaison sur l'ensemble de lignes à une colonne spécifique dans l'ensemble de lignes.  
  
## Syntaxe  
  
```  
  
COLUMN_ENTRY_PS(  
nOrdinal  
,   
nPrecision  
,   
nScale  
,   
data  
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
 \[in\] Le membre de données correspondant dans le registre d'utilisateur.  
  
## Notes  
 Vous permet de spécifier la précision et l'échelle de la colonne que vous souhaitez lier.  C'est utilisé dans les endroits suivants:  
  
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
 [COLUMN\_ENTRY\_PS\_LENGTH](../../data/oledb/column-entry-ps-length.md)   
 [COLUMN\_ENTRY\_LENGTH\_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH\_STATUS](../../data/oledb/column-entry-ps-length-status.md)   
 [COLUMN\_ENTRY\_STATUS](../../data/oledb/column-entry-status.md)   
 [COLUMN\_ENTRY\_PS\_STATUS](../../data/oledb/column-entry-ps-status.md)   
 [END\_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)