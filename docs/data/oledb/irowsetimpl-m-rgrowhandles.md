---
title: "IRowsetImpl::m_rgRowHandles | Microsoft Docs"
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
  - "IRowsetImpl::m_rgRowHandles"
  - "IRowsetImpl.m_rgRowHandles"
  - "m_rgRowHandles"
  - "ATL::IRowsetImpl::m_rgRowHandles"
  - "ATL.IRowsetImpl.m_rgRowHandles"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_rgRowHandles"
ms.assetid: d3c2578f-58c4-4301-bf59-cf101a523a95
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetImpl::m_rgRowHandles
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une carte des gestion en ligne actuellement contenues dans le fournisseur en réponse à `GetNextRows`.  
  
## Syntaxe  
  
```  
  
MapClass  
 m_rgRowHandles;  
  
```  
  
## Notes  
 Des gestion en ligne sont supprimées en appelant `ReleaseRows`.  Consultez la [Vue d'ensemble de IRowsetImpl](../../data/oledb/irowsetimpl-class.md) pour la définition *de MapClass*.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IRowsetImpl, classe](../../data/oledb/irowsetimpl-class.md)