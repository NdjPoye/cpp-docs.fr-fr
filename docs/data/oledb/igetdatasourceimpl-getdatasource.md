---
title: "IGetDataSourceImpl::GetDataSource | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetDataSource"
  - "IGetDataSourceImpl.GetDataSource"
  - "IGetDataSourceImpl::GetDataSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetDataSource (méthode)"
ms.assetid: b70995d2-b951-452e-a2d4-fb3eb085886e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IGetDataSourceImpl::GetDataSource
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne un pointeur d'interface sur l'objet de source de données qui a créé la session.  
  
## Syntaxe  
  
```  
  
      STDMETHOD(GetDataSource)(   
   REFIID riid,   
   IUnknown ** ppDataSource    
);  
```  
  
#### Paramètres  
 Consultez le [IGetDataSource::GetDataSource](https://msdn.microsoft.com/en-us/library/ms725443.aspx) dans le *Guide de référence du programmeur OLE DB*.  
  
## Notes  
 Utile si vous devez accéder aux propriétés de l'objet source de données.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IGetDataSourceImpl, classe](../../data/oledb/igetdatasourceimpl-class.md)