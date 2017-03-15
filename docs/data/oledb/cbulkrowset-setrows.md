---
title: "CBulkRowset::SetRows | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CBulkRowset.SetRows"
  - "CBulkRowset::SetRows"
  - "CBulkRowset<TAccessor>.SetRows"
  - "ATL.CBulkRowset<TAccessor>.SetRows"
  - "CBulkRowset<TAccessor>::SetRows"
  - "ATL::CBulkRowset<TAccessor>::SetRows"
  - "ATL::CBulkRowset::SetRows"
  - "CBulkRowset.SetRows"
  - "SetRows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetRows (méthode)"
ms.assetid: 7e92312a-bfd0-4c24-a799-62bef663f28e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CBulkRowset::SetRows
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit le nombre de descripteurs de ligne extraits par chaque appel.  
  
## Syntaxe  
  
```  
  
      void SetRows(  
   DBROWCOUNT nRows   
) throw( );  
```  
  
#### Paramètres  
 `nRows`  
 \[in\] la nouvelle taille de l'ensemble de lignes \(nombre de lignes\).  
  
## Notes  
 Si vous appelez la fonction, elle doit être appelée avant que l'ensemble de lignes soit ouvert.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CBulkRowset, classe](../../data/oledb/cbulkrowset-class.md)