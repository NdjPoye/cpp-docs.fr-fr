---
title: "CDBPropIDSet::SetGUID | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDBPropIDSet.SetGUID"
  - "ATL::CDBPropIDSet::SetGUID"
  - "SetGUID"
  - "ATL.CDBPropIDSet.SetGUID"
  - "CDBPropIDSet::SetGUID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetGUID (méthode)"
ms.assetid: 8dd0f3bf-1490-4d53-9063-322b8d821bbe
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDBPropIDSet::SetGUID
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sets the GUID field in the **DBPROPIDSET** structure.  
  
## Syntaxe  
  
```  
  
      void SetGUID(   
   const GUID& guid    
) throw( );  
```  
  
#### Paramètres  
 `guid`  
 \[in\] A GUID used to set the **guidPropertySet** field of the [DBPROPIDSET](https://msdn.microsoft.com/en-us/library/ms717981.aspx) structure.  
  
## Notes  
 This field can be set by the [constructor](../../data/oledb/cdbpropidset-cdbpropidset.md) as well.  Call this function if you use the default constructor for this class.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDBPropIDSet, classe](../../data/oledb/cdbpropidset-class.md)