---
title: "IRowsetImpl::RestartPosition | Microsoft Docs"
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
  - "ATL.IRowsetImpl.RestartPosition"
  - "IRowsetImpl::RestartPosition"
  - "RestartPosition"
  - "ATL::IRowsetImpl::RestartPosition"
  - "IRowsetImpl.RestartPosition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RestartPosition (méthode)"
ms.assetid: 14de66ef-8d2c-4404-adb6-3f6c74ac6cf1
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetImpl::RestartPosition
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Replace la prochaine position d'extraction dans sa position initiale ; autrement dit, sa position quand l'ensemble de lignes a été créé la première fois.  
  
## Syntaxe  
  
```  
  
      STDMETHOD( RestartPosition )(  
   HCHAPTER /* hReserved */   
);  
```  
  
#### Paramètres  
 Consultez [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx) dans le *Guide de référence du programmeur OLE DB*.  
  
## Notes  
 La position d'un ensemble de lignes n'est pas définie tant que **GetNextRow** est appelé.  Vous pouvez déplacer vers l'arrière dans un rowet en appelant [RestartPosition](#vcrefirowsetimplrestartposition) puis en extrayant ou en défilant vers l'arrière.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IRowsetImpl, classe](../../data/oledb/irowsetimpl-class.md)