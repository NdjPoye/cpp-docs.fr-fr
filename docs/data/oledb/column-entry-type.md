---
title: "COLUMN_ENTRY_TYPE | Microsoft Docs"
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
  - "COLUMN_ENTRY_TYPE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_ENTRY_TYPE (macro)"
ms.assetid: ac424261-ff6c-443b-a197-2cec8d78d738
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COLUMN_ENTRY_TYPE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une liaison à une colonne spécifique dans la base de données.  Prend en charge le paramètre de `type`.  
  
## Syntaxe  
  
```  
  
COLUMN_ENTRY_TYPE (  
nOrdinal  
,   
wType  
,   
data  
 )  
  
```  
  
#### Paramètres  
 `nOrdinal`  
 \[in\] Le numéro de colonne.  
  
 `wType`  
 \[in\] type de données de la colonne d'entrée.  
  
 `data`  
 \[in\] Le membre de données correspondant dans le registre d'utilisateur.  
  
## Notes  
 La macro est une variante spéciale de la macro de [COLUMN\_ENTRY](../../data/oledb/column-entry.md) qui fournit un moyen de spécifier le type de données.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)