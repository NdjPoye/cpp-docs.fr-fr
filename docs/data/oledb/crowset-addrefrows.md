---
title: "CRowset::AddRefRows | Microsoft Docs"
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
  - "CRowset<TAccessor>.AddRefRows"
  - "CRowset.AddRefRows"
  - "ATL.CRowset.AddRefRows"
  - "AddRefRows"
  - "CRowset::AddRefRows"
  - "CRowset<TAccessor>::AddRefRows"
  - "ATL::CRowset::AddRefRows"
  - "ATL.CRowset<TAccessor>.AddRefRows"
  - "ATL::CRowset<TAccessor>::AddRefRows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddRefRows (méthode)"
ms.assetid: 590b5a24-870f-4c42-b0c8-28491f368a82
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::AddRefRows
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelle [IRowset::AddRefRows](https://msdn.microsoft.com/en-us/library/ms719619.aspx) pour incrémenter \(par un\) nombre de références associé à la poignée de ligne actuelle.  
  
## Syntaxe  
  
```  
  
HRESULT AddRefRows( ) throw( );  
  
```  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 Cette méthode incrémente le nombre de références de la poignée de ligne actuelle.  Appelle [ReleaseRows](../../data/oledb/crowset-releaserows.md) pour décrémenter le nombre.  Les lignes renvoyées par les méthodes de déplacement ont un nombre de références d'un.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CRowset, classe](../../data/oledb/crowset-class.md)   
 [CRowset::ReleaseRows](../../data/oledb/crowset-releaserows.md)