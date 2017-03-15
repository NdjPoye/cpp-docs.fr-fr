---
title: "IRowsetCreatorImpl, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::IRowsetCreatorImpl"
  - "ATL.IRowsetCreatorImpl"
  - "ATL::IRowsetCreatorImpl<T>"
  - "ATL.IRowsetCreatorImpl<T>"
  - "IRowsetCreatorImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetCreatorImpl (classe)"
ms.assetid: 92cc950f-7978-4754-8d9a-defa63867d82
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# IRowsetCreatorImpl, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Performs the same functions as `IObjectWithSite` but also enables the OLE DB properties **DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS**.  
  
## Syntaxe  
  
```  
template < class T >  
class ATL_NO_VTABLE IRowsetCreatorImpl   
   : public IObjectWithSiteImpl< T >  
```  
  
#### Paramètres  
 `T`  
 A class derived from **IRowsetCreator**.  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[SetSite](../../data/oledb/irowsetcreatorimpl-setsite.md)|Sets the site that contains the rowset object.|  
  
## Notes  
 This class inherits from [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) and overrides [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869).  When a provider command or session object creates a rowset, it calls `QueryInterface` on the rowset object looking for `IObjectWithSite` and calls `SetSite` passing the rowset object's **IUnkown** interface as the site interface.  
  
## Configuration requise  
 **Header:** atldb.h  
  
## Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)