---
title: "IRowsetInfoImpl::GetSpecification | Microsoft Docs"
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
  - "IRowsetInfoImpl::GetSpecification"
  - "ATL.IRowsetInfoImpl.GetSpecification"
  - "IRowsetInfoImpl.GetSpecification"
  - "GetSpecification"
  - "ATL::IRowsetInfoImpl::GetSpecification"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetSpecification (méthode)"
ms.assetid: 8e14289d-9cca-4df7-a9e0-f4ef03c61e30
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetInfoImpl::GetSpecification
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne un pointeur d'interface sur l'objet \(commande ou session\) qui a créé ce jeu de lignes.  
  
## Syntaxe  
  
```  
  
      STDMETHOD ( GetSpecification )(  
   REFIID riid,  
   IUnknown** ppSpecification   
);  
```  
  
#### Paramètres  
 See [IRowsetInfo::GetSpecification](https://msdn.microsoft.com/en-us/library/ms716746.aspx) in the *OLE DB Programmer's Reference*.  
  
## Notes  
 Use this method with [IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md) to retrieve properties from the data source object.  
  
## Configuration requise  
 **Header:** atldb.h  
  
## Voir aussi  
 [IRowsetInfoImpl, classe](../../data/oledb/irowsetinfoimpl-class.md)   
 [IRowsetInfoImpl::GetReferencedRowset](../../data/oledb/irowsetinfoimpl-getreferencedrowset.md)   
 [IRowsetInfoImpl::GetProperties](../../data/oledb/irowsetinfoimpl-getproperties.md)