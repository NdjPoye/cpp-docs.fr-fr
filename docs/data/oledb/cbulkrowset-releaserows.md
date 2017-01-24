---
title: "CBulkRowset::ReleaseRows | Microsoft Docs"
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
  - "ReleaseRows"
  - "ATL.CBulkRowset<TAccessor>.ReleaseRows"
  - "ATL::CBulkRowset<TAccessor>::ReleaseRows"
  - "ATL.CBulkRowset.ReleaseRows"
  - "CBulkRowset<TAccessor>::ReleaseRows"
  - "ATL::CBulkRowset::ReleaseRows"
  - "CBulkRowset::ReleaseRows"
  - "CBulkRowset.ReleaseRows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseRows (méthode)"
ms.assetid: ba48aff3-0887-47ba-aed7-7ff28fa1c4a8
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBulkRowset::ReleaseRows
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelle [IRowset::ReleaseRows](https://msdn.microsoft.com/en-us/library/ms719771.aspx) pour décrémenter le nombre de références pour toutes les lignes actuellement récupérées de l'ensemble de lignes en bloc.  
  
## Syntaxe  
  
```  
  
HRESULT ReleaseRows( ) throw( );  
  
```  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CBulkRowset, classe](../../data/oledb/cbulkrowset-class.md)   
 [CBulkRowset::AddRefRows](../../data/oledb/cbulkrowset-addrefrows.md)