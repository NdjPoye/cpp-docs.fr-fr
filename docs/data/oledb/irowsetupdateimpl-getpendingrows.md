---
title: "IRowsetUpdateImpl::GetPendingRows | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetUpdateImpl::GetPendingRows"
  - "GetPendingRows"
  - "IRowsetUpdateImpl.GetPendingRows"
  - "ATL::IRowsetUpdateImpl::GetPendingRows"
  - "ATL.IRowsetUpdateImpl.GetPendingRows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetPendingRows (méthode)"
ms.assetid: 2d1ef748-da6d-4184-98dc-096427358dfd
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetUpdateImpl::GetPendingRows
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne une liste de lignes avec des modifications en attente.  
  
## Syntaxe  
  
```  
  
      STDMETHOD ( GetPendingRows )(  
   HCHAPTER /* hReserved */,  
   DBPENDINGSTATUS dwRowStatus,  
   DBCOUNTITEM* pcPendingRows,  
   HROW** prgPendingRows,  
   DBPENDINGSTATUS** prgPendingStatus   
);  
```  
  
#### Paramètres  
 `hReserved`  
 \[in\] Correspond au paramètre de `hChapter` dans [IRowsetUpdate::GetPendingRows](https://msdn.microsoft.com/en-us/library/ms719626.aspx).  
  
 Pour d'autres paramètres, consultez [IRowsetUpdate::GetPendingRows](https://msdn.microsoft.com/en-us/library/ms719626.aspx) dans *OLE DB guide de référence du programmeur*.  
  
## Notes  
 Pour plus d'informations, consultez [IRowsetUpdate::GetPendingRows](https://msdn.microsoft.com/en-us/library/ms719626.aspx) dans le *Guide de référence du programmeur OLE DB*.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IRowsetUpdateImpl, classe](../../data/oledb/irowsetupdateimpl-class.md)