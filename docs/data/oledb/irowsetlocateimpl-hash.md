---
title: "IRowsetLocateImpl::Hash | Microsoft Docs"
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
  - "IRowsetLocateImpl::Hash"
  - "IRowsetLocateImpl.Hash"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Hash (méthode)"
ms.assetid: 7df4386d-80fb-4332-a85f-baae98cdc6e0
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetLocateImpl::Hash
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne des valeurs de hachage pour les signets spécifiés.  
  
## Syntaxe  
  
```  
  
      STDMETHOD ( Hash )(  
   HCHAPTER /* hReserved */,  
   DBBKMARK cbBookmarks,  
   const DBBKMARK* rgcbBookmarks[],  
   const BYTE* rgpBookmarks[],  
   DBHASHVALUE rgHashValues[],  
   DBROWSTATUS rgBookmarkStatus[]   
);  
```  
  
#### Paramètres  
 `hReserved`  
 \[in\] correspond au paramètre `hChapter` de [IRowsetLocate::Hash](https://msdn.microsoft.com/en-us/library/ms709697.aspx).  
  
 Pour d'autres paramètres, consultez [IRowsetUpdate::Hash](https://msdn.microsoft.com/en-us/library/ms709697.aspx) dans le *guide de référence du programmeur OLE DB*.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IRowsetLocateImpl, classe](../../data/oledb/irowsetlocateimpl-class.md)