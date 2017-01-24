---
title: "COLUMN_NAME_EX | Microsoft Docs"
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
  - "COLUMN_NAME_EX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_NAME_EX (macro)"
ms.assetid: 4f916a85-f6ae-464a-9cbe-0a56dbb274a6
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COLUMN_NAME_EX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une liaison sur l'ensemble de lignes à une colonne spécifique dans l'ensemble de lignes.  Similaire à [COLUMN\_NAME](../../data/oledb/column-name.md), sauf que la macro prend également le type de données, la taille, la précision, l'échelle, la taille de la colonne, et l'état de la colonne.  
  
## Syntaxe  
  
```  
  
COLUMN_NAME_EX(  
pszName  
,   
wType  
,   
nLength  
,   
nPrecision  
,   
nScale  
,   
data  
,   
length  
,   
status )  
```  
  
#### Paramètres  
 `pszName`  
 \[in\] Un pointeur sur le nom de colonne.  Le nom doit être une chaîne Unicode.  Vous pouvez y parvenir en mettant un « L » devant le nom, par exemple : `L"MyColumn"`.  
  
 `wType`  
 \[in\] Les données du type  
  
 `nLength`  
 \[in\] Taille en octets des données.  
  
 `nPrecision`  
 \[in\] La précision maximale à utiliser lors de l'obtention de données et `wType` est `DBTYPE_NUMERIC`.  Sinon, ce paramètre est ignoré.  
  
 `nScale`  
 \[in\] l'échelle à utiliser lors de l'obtention de données et `wType` est `DBTYPE_NUMERIC` ou **DBTYPE\_DECIMAL**.  
  
 `data`  
 \[in\] Le membre de données correspondant dans le registre d'utilisateur.  
  
 *length*  
 \[in\] La variable à lier à la longueur de la colonne.  
  
 *status*  
 \[in\] La variable à lier à l'état de la colonne.  
  
## Notes  
 Voir [COLUMN\_NAME](../../data/oledb/column-name.md) pour plus d'informations sur où les macros de **COLUMN\_NAME\_\*** sont utilisées.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN\_NAME](../../data/oledb/column-name.md)   
 [COLUMN\_NAME\_LENGTH](../../data/oledb/column-name-length.md)   
 [COLUMN\_NAME\_LENGTH\_STATUS](../../data/oledb/column-name-length-status.md)   
 [COLUMN\_NAME\_STATUS](../../data/oledb/column-name-status.md)   
 [COLUMN\_NAME\_PS](../../data/oledb/column-name-ps.md)   
 [COLUMN\_NAME\_PS\_LENGTH](../../data/oledb/column-name-ps-length.md)   
 [COLUMN\_NAME\_PS\_STATUS](../../data/oledb/column-name-ps-status.md)   
 [COLUMN\_NAME\_PS\_LENGTH\_STATUS](../../data/oledb/column-name-ps-length-status.md)   
 [COLUMN\_NAME\_TYPE](../../data/oledb/column-name-type.md)   
 [COLUMN\_NAME\_TYPE\_PS](../../data/oledb/column-name-type-ps.md)   
 [COLUMN\_NAME\_TYPE\_SIZE](../../data/oledb/column-name-type-size.md)   
 [COLUMN\_NAME\_TYPE\_STATUS](../../data/oledb/column-name-type-status.md)