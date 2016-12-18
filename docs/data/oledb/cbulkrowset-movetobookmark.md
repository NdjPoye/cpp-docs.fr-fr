---
title: "CBulkRowset::MoveToBookmark | Microsoft Docs"
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
  - "CBulkRowset<TAccessor>::MoveToBookmark"
  - "CBulkRowset.MoveToBookmark"
  - "MoveToBookmark"
  - "ATL.CBulkRowset.MoveToBookmark"
  - "CBulkRowset::MoveToBookmark"
  - "ATL::CBulkRowset<TAccessor>::MoveToBookmark"
  - "ATL::CBulkRowset::MoveToBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveToBookmark (méthode)"
ms.assetid: 76aab025-819e-4ecd-ae0a-d8d3fb2d2099
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBulkRowset::MoveToBookmark
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Extrait la ligne marquée par un signet ou la ligne à un nombre de lignes spécifié de ce signet \(`lSkip`\).  
  
## Syntaxe  
  
```  
  
      HRESULT MoveToBookmark(  
   const CBookmarkBase& bookmark,  
   DBCOUNTITEM lSkip = 0   
) throw( );  
```  
  
#### Paramètres  
 `bookmark`  
 \[in\] d'Un signet qui marque l'emplacement à partir duquel vous souhaitez extraire des données.  
  
 `lSkip`  
 \[in\] nombre de nombre de lignes du signet à la ligne cible.  Si `lSkip` vaut zéro, la première ligne extraite est la ligne marquée par le signet.  Si `lSkip` est 1, la première ligne extraite est la ligne après la ligne marquée par le signet.  Si `lSkip` vaut \-1, la première ligne extraite est la ligne avant la ligne marquée par le signet.  
  
## Valeur de retour  
 Consultez [IRowset::GetData](https://msdn.microsoft.com/en-us/library/ms716988.aspx) dans le *Guide du Programmeur OLE DB*.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CBulkRowset, classe](../../data/oledb/cbulkrowset-class.md)