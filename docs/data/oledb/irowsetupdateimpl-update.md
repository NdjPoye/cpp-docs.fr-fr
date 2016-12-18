---
title: "IRowsetUpdateImpl::Update | Microsoft Docs"
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
  - "ATL::IRowsetUpdateImpl::Update"
  - "IRowsetUpdateImpl::Update"
  - "IRowsetUpdateImpl.Update"
  - "ATL.IRowsetUpdateImpl.Update"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Update (méthode)"
ms.assetid: 9ec6884d-aa9c-4871-a803-c048f162403c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetUpdateImpl::Update
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Transmet toutes les modifications apportées à la ligne depuis la dernière extraction ou mise à jour.  
  
## Syntaxe  
  
```  
  
      STDMETHOD ( Update )(  
   HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBCOUNTITEM* pcRows,  
   HROW** prgRows,  
   DBROWSTATUS** prgRowStatus   
);  
```  
  
#### Paramètres  
 `hReserved`  
 \[in\] correspond au paramètre de `hChapter` dans [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx).  
  
 Pour d'autres paramètres, consultez [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx) dans *OLE DB guide de référence du programmeur*.  
  
## Notes  
 Les modifications sont transmises en appelant [IRowsetChangeImpl::FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md).  Le consommateur doit appeler [CRowset::Update](../../data/oledb/crowset-update.md) pour que les modifications prennent effet.  Définissez *le prgRowstatus* avec une valeur appropriée comme décrit dans [États de ligne](https://msdn.microsoft.com/en-us/library/ms722752.aspx) dans *OLE DB guide de référence du programmeur*.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IRowsetUpdateImpl, classe](../../data/oledb/irowsetupdateimpl-class.md)