---
title: "COLUMN_NAME_TYPE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COLUMN_NAME_TYPE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_NAME_TYPE (macro)"
ms.assetid: 815ace8f-8ec3-4ad7-a7a0-37fa8e4bc68c
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# COLUMN_NAME_TYPE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une liaison entre l'ensemble de lignes et une colonne spécifique dans l'ensemble de lignes.  Similaire à [COLUMN\_NAME](../../data/oledb/column-name.md), mais que la macro prend également en charge le type de données.  
  
## Syntaxe  
  
```  
  
COLUMN_NAME_TYPE(  
pszName  
,   
wType  
,   
data  
 )  
  
```  
  
#### Paramètres  
 `pszName`  
 \[in\] Un pointeur sur le nom de colonne.  Le nom doit être une chaîne Unicode.  Vous pouvez y parvenir en mettant un « L » devant le nom, par exemple : `L"MyColumn"`.  
  
 `wType`  
 \[in\] Les données du type  
  
 `data`  
 \[in\] Le membre de données correspondant dans l'article utilisateur.  
  
## Notes  
 Voir [NOM\_COLONNE](../../data/oledb/column-name.md) pour plus d'informations sur où les macros de **NOM\_COLONNE\_\*** sont utilisées.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN\_NAME](../../data/oledb/column-name.md)   
 [COLUMN\_NAME\_EX](../../data/oledb/column-name-ex.md)   
 [COLUMN\_NAME\_LENGTH](../../data/oledb/column-name-length.md)   
 [COLUMN\_NAME\_LENGTH\_STATUS](../../data/oledb/column-name-length-status.md)   
 [COLUMN\_NAME\_STATUS](../../data/oledb/column-name-status.md)   
 [COLUMN\_NAME\_PS](../../data/oledb/column-name-ps.md)   
 [COLUMN\_NAME\_PS\_LENGTH](../../data/oledb/column-name-ps-length.md)   
 [COLUMN\_NAME\_PS\_STATUS](../../data/oledb/column-name-ps-status.md)   
 [COLUMN\_NAME\_PS\_LENGTH\_STATUS](../../data/oledb/column-name-ps-length-status.md)   
 [COLUMN\_NAME\_TYPE\_PS](../../data/oledb/column-name-type-ps.md)   
 [COLUMN\_NAME\_TYPE\_SIZE](../../data/oledb/column-name-type-size.md)   
 [COLUMN\_NAME\_TYPE\_STATUS](../../data/oledb/column-name-type-status.md)