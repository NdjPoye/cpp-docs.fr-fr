---
title: "IGetDataSourceImpl, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IGetDataSourceImpl"
  - "ATL.IGetDataSourceImpl<T>"
  - "ATL.IGetDataSourceImpl"
  - "ATL::IGetDataSourceImpl"
  - "ATL::IGetDataSourceImpl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IGetDataSourceImpl (classe)"
ms.assetid: d63f3178-d663-4f01-8c09-8aab2dd6805a
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IGetDataSourceImpl, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Provides an implementation of the [IGetDataSource](https://msdn.microsoft.com/en-us/library/ms709721.aspx) object.  
  
## Syntaxe  
  
```  
template <class T>  
class ATL_NO_VTABLE IGetDataSourceImpl : public IGetDataSource  
```  
  
#### Paramètres  
 `T`  
 Your class, derived from `IGetDataSourceImpl`.  
  
## Membres  
  
### Interface Methods  
  
|||  
|-|-|  
|[GetDataSource](../../data/oledb/igetdatasourceimpl-getdatasource.md)|Returns an interface pointer on the data source object that created the session.|  
  
## Notes  
 This is a mandatory interface on the session for obtaining an interface pointer to the data source object.  
  
## Configuration requise  
 **Header:** atldb.h  
  
## Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)