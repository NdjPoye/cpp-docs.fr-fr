---
title: "BEGIN_COLUMN_MAP | Microsoft Docs"
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
  - "BEGIN_COLUMN_MAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BEGIN_COLUMN_MAP (macro)"
ms.assetid: d6ffe633-e0da-4e33-8faa-f7f259d05420
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# BEGIN_COLUMN_MAP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Marque le début d’une entrée de mappage de colonnes.  
  
## Syntaxe  
  
```  
  
BEGIN_COLUMN_MAP(  
x  
 )  
  
```  
  
#### Paramètres  
 *x*  
 \[in\] Nom de la classe d’enregistrement utilisateur dérivée de `CAccessor`.  
  
## Notes  
 Cette macro est utilisée dans le cas d’un seul accesseur sur un ensemble de lignes. Si vous avez plusieurs accesseurs sur un ensemble de lignes, utilisez [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md).  
  
 La macro `BEGIN_COLUMN_MAP` se termine avec la macro `END_COLUMN_MAP`. Cette macro est utilisée quand un seul accesseur est obligatoire dans l’enregistrement utilisateur.  
  
 Les colonnes correspondent aux champs de l’ensemble de lignes à lier.  
  
## Exemple  
 Voici un exemple de mappage de colonnes et de paramètres :  
  
 [!CODE [NVC_OLEDB_Consumer#16](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#16)]  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN\_ENTRY\_EX](../../data/oledb/column-entry-ex.md)