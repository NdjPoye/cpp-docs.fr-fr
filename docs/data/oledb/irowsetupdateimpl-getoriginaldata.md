---
title: "IRowsetUpdateImpl::GetOriginalData | Microsoft Docs"
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
  - "ATL.IRowsetUpdateImpl.GetOriginalData"
  - "IRowsetUpdateImpl.GetOriginalData"
  - "GetOriginalData"
  - "ATL::IRowsetUpdateImpl::GetOriginalData"
  - "IRowsetUpdateImpl::GetOriginalData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetOriginalData (méthode)"
ms.assetid: 7477b3b7-6b1b-49a7-8167-b34323f0fdcc
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetUpdateImpl::GetOriginalData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient les données récemment transmises ou obtenues de la source de données, en ignorant les modifications en attente.  
  
## Syntaxe  
  
```  
  
      STDMETHOD ( GetOriginalData )(  
   HROW hRow,  
   HACCESSOR hAccessor,  
   void* pData   
);  
```  
  
#### Paramètres  
 Voir [IRowsetUpdate::GetOriginalData](https://msdn.microsoft.com/en-us/library/ms709947.aspx) dans le *Guide de référence du programmeur OLE DB*.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IRowsetUpdateImpl, classe](../../data/oledb/irowsetupdateimpl-class.md)