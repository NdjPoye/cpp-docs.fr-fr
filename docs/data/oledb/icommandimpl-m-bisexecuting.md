---
title: "ICommandImpl::m_bIsExecuting | Microsoft Docs"
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
  - "ICommandImpl.m_bIsExecuting"
  - "ATL::ICommandImpl::m_bIsExecuting"
  - "m_bIsExecuting"
  - "ATL.ICommandImpl.m_bIsExecuting"
  - "ICommandImpl::m_bIsExecuting"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_bIsExecuting"
ms.assetid: 1e152164-514c-4116-88a3-16984af99991
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ICommandImpl::m_bIsExecuting
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Indique si la commande est actuellement en cours d'exécution.  
  
## Syntaxe  
  
```  
  
unsigned m_bIsExecuting:1;  
  
```  
  
## Notes  
 La méthode **Exécuter** de la classe de commande peut définir cette variable sur **true**.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [ICommandImpl, classe](../../data/oledb/icommandimpl-class.md)   
 [ICommandImpl::m\_bCancelWhenExecuting](../../data/oledb/icommandimpl-m-bcancelwhenexecuting.md)