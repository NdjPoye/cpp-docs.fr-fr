---
title: "CRowset::CRowset | Microsoft Docs"
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
  - "CRowset<TAccessor>::CRowset"
  - "CRowset.CRowset"
  - "ATL::CRowset::CRowset"
  - "ATL::CRowset<TAccessor>::CRowset"
  - "ATL.CRowset.CRowset"
  - "CRowset"
  - "CRowset<TAccessor>.CRowset"
  - "CRowset::CRowset"
  - "ATL.CRowset<TAccessor>.CRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRowset (classe), constructeur"
ms.assetid: 1c6f72e2-f4f4-48dc-957e-038ae8914ba7
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::CRowset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée un nouvel objet `CRowset` et l'associe \(éventuellement\) avec une interface [IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx) fournie en tant que paramètre.  
  
## Syntaxe  
  
```  
  
      CRowset( );   
CRowset(  
   IRowset* pRowset   
);  
```  
  
#### Paramètres  
 `pRowset`  
 \[in\] Un pointeur vers une interface `IRowset` à associer à cette classe.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CRowset, classe](../../data/oledb/crowset-class.md)