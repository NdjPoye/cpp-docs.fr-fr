---
title: "CRowset::MoveToBookmark | Microsoft Docs"
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
  - "ATL::CRowset::MoveToBookmark"
  - "ATL::CRowset<TAccessor>::MoveToBookmark"
  - "ATL.CRowset.MoveToBookmark"
  - "ATL.CRowset<TAccessor>.MoveToBookmark"
  - "MoveToBookmark"
  - "CRowset::MoveToBookmark"
  - "CRowset.MoveToBookmark"
  - "CRowset<TAccessor>::MoveToBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveToBookmark (méthode)"
ms.assetid: 90124723-8daf-4692-ae2f-0db26b5db920
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::MoveToBookmark
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fetches the row marked by a bookmark or the row at a specified offset \(`lSkip`\) from that bookmark.  
  
## Syntaxe  
  
```  
  
      HRESULT MoveToBookmark(   
   const CBookmarkBase& bookmark,   
   LONG lSkip = 0    
) throw( );  
```  
  
#### Paramètres  
 `bookmark`  
 \[in\] A bookmark marking the location from which you want to fetch data.  
  
 `lSkip`  
 \[in\] The number count of rows from the bookmark to the target row.  If `lSkip` is zero, the first row fetched is the bookmarked row.  If `lSkip` is 1, the first row fetched is the row after the bookmarked row.  If `lSkip` is –1, the first row fetched is the row before the bookmarked row.  
  
## Valeur de retour  
 A standard `HRESULT`.  
  
## Notes  
 This method requires the optional interface `IRowsetLocate`, which might not be supported on all providers; if this is the case, the method returns **E\_NOINTERFACE**.  You must also set **DBPROP\_IRowsetLocate** to `VARIANT_TRUE` and set **DBPROP\_CANFETCHBACKWARDS** to `VARIANT_TRUE` before calling **Open** on the table or command containing the rowset.  
  
 For information about using bookmarks in consumers, see [Using Bookmarks](../../data/oledb/using-bookmarks.md).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CRowset, classe](../../data/oledb/crowset-class.md)   
 [CRowset::MoveNext](../../data/oledb/crowset-movenext.md)   
 [CRowset::MoveFirst](../../data/oledb/crowset-movefirst.md)   
 [IRowsetLocate::GetRowsAt](https://msdn.microsoft.com/en-us/library/ms723031.aspx)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)