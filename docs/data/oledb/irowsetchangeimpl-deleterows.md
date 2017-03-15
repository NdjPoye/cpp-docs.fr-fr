---
title: "IRowsetChangeImpl::DeleteRows | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.IRowsetChangeImpl.DeleteRows"
  - "ATL::IRowsetChangeImpl::DeleteRows"
  - "IRowsetChangeImpl.DeleteRows"
  - "DeleteRows"
  - "IRowsetChangeImpl::DeleteRows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DeleteRows (méthode)"
ms.assetid: 462ad4f1-3b2a-4134-9733-be65708aa1d9
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IRowsetChangeImpl::DeleteRows
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Supprime des lignes de l'ensemble de lignes.  
  
## Syntaxe  
  
```  
  
      STDMETHOD ( DeleteRows )(  
   HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBROWSTATUS rgRowStatus[]   
);  
```  
  
#### Paramètres  
 Pour plus d'informations sur les curseurs, consultez le [IRowsetChange::DeleteRows](https://msdn.microsoft.com/en-us/library/ms724362.aspx) du *Guide de référence du programmeur OLE DB*.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IRowsetChangeImpl Class](../../data/oledb/irowsetchangeimpl-class.md)