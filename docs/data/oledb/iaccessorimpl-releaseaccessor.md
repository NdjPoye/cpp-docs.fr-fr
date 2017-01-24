---
title: "IAccessorImpl::ReleaseAccessor | Microsoft Docs"
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
  - "ReleaseAccessor"
  - "IAccessorImpl::ReleaseAccessor"
  - "ATL.IAccessorImpl.ReleaseAccessor"
  - "ATL::IAccessorImpl::ReleaseAccessor"
  - "IAccessorImpl.ReleaseAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseAccessor (méthode)"
ms.assetid: 1526e360-bd9c-4ecd-967e-5afdd7506d2a
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IAccessorImpl::ReleaseAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Libère un accesseur.  
  
## Syntaxe  
  
```  
  
      STDMETHOD(ReleaseAccessor)(  
   HACCESSOR hAccessor,  
   DBREFCOUNT* pcRefCount   
);  
```  
  
#### Paramètres  
 Consultez [IAccessor::ReleaseAccessor](https://msdn.microsoft.com/en-us/library/ms719717.aspx) dans le *Guide de référence pour programmeur OLE DB*.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IAccessorImpl, classe](../../data/oledb/iaccessorimpl-class.md)   
 [IAccessorImpl::CreateAccessor](../../data/oledb/iaccessorimpl-createaccessor.md)   
 [IAccessorImpl::AddRefAccessor](../../data/oledb/iaccessorimpl-addrefaccessor.md)