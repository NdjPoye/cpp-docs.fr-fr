---
title: "IAccessorImpl::AddRefAccessor | Microsoft Docs"
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
  - "ATL::IAccessorImpl::AddRefAccessor"
  - "AddRefAccessor"
  - "IAccessorImpl::AddRefAccessor"
  - "IAccessorImpl.AddRefAccessor"
  - "ATL.IAccessorImpl.AddRefAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddRefAccessor (méthode)"
ms.assetid: 4c15392c-944b-4cbd-8cc7-2a5c2f308a70
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IAccessorImpl::AddRefAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ajoute un décompte de références à un accesseur existant.  
  
## Syntaxe  
  
```  
  
      STDMETHOD(AddRefAccessor)(  
   HACCESSOR hAccessor,  
   DBREFCOUNT* pcRefCount   
);  
```  
  
#### Paramètres  
 Pour plus d'informations sur les curseurs, consultez [IAccessor::AddRefAccessor](https://msdn.microsoft.com/en-us/library/ms714978.aspx) du *Guide de référence du programmeur OLE DB*.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IAccessorImpl, classe](../../data/oledb/iaccessorimpl-class.md)   
 [IAccessorImpl::CreateAccessor](../../data/oledb/iaccessorimpl-createaccessor.md)   
 [IAccessorImpl::ReleaseAccessor](../../data/oledb/iaccessorimpl-releaseaccessor.md)