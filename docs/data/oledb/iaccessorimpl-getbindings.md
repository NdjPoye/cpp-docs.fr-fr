---
title: "IAccessorImpl::GetBindings | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IAccessorImpl.GetBindings"
  - "ATL::IAccessorImpl::GetBindings"
  - "IAccessorImpl::GetBindings"
  - "GetBindings"
  - "ATL.IAccessorImpl.GetBindings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetBindings (méthode)"
ms.assetid: eb550077-77ef-450b-89f1-a2930cee6ab8
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IAccessorImpl::GetBindings
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Returns the basic columns bindings from the consumer in an accessor.  
  
## Syntaxe  
  
```  
  
      STDMETHOD(GetBindings)(  
   HACCESSOR hAccessor,  
   DBACCESSORFLAGS* pdwAccessorFlags,  
   DBCOUNTITEM* pcBindings,  
   DBBINDING** prgBindings   
);  
```  
  
#### Paramètres  
 See [IAccessor::GetBindings](https://msdn.microsoft.com/en-us/library/ms721253.aspx) in the *OLE DB Programmer's Reference*.  
  
## Configuration requise  
 **Header:** atldb.h  
  
## Voir aussi  
 [IAccessorImpl, classe](../../data/oledb/iaccessorimpl-class.md)