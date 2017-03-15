---
title: "ISessionPropertiesImpl::SetProperties | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ISessionPropertiesImpl.SetProperties"
  - "SetProperties"
  - "ISessionPropertiesImpl::SetProperties"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetProperties (méthode)"
ms.assetid: 2e1219ed-0e1e-460e-84d6-031acfbfd3d2
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# ISessionPropertiesImpl::SetProperties
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit les propriétés du groupe de propriétés de **DBPROPSET\_SESSION**.  
  
## Syntaxe  
  
```  
  
      STDMETHOD(SetProperties)(   
   ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]    
);  
```  
  
#### Paramètres  
 Consultez [ISessionProperties::SetProperties](https://msdn.microsoft.com/en-us/library/ms714405.aspx) dans le *Guide de référence du programmeur OLE DB*.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [ISessionPropertiesImpl, classe](../../data/oledb/isessionpropertiesimpl-class.md)   
 [ISessionPropertiesImpl::GetProperties](../../data/oledb/isessionpropertiesimpl-getproperties.md)