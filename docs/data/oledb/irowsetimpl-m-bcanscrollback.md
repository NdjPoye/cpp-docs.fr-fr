---
title: "IRowsetImpl::m_bCanScrollBack | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetImpl::m_bCanScrollBack"
  - "ATL::IRowsetImpl::m_bCanScrollBack"
  - "IRowsetImpl.m_bCanScrollBack"
  - "ATL.IRowsetImpl.m_bCanScrollBack"
  - "m_bCanScrollBack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_bCanScrollBack"
ms.assetid: 69de3179-bf56-415e-935f-e98bcb34debe
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetImpl::m_bCanScrollBack
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Indique si un fournisseur peut faire défiler le curseur vers l'abonné.  
  
## Syntaxe  
  
```  
  
unsigned  m_bCanScrollBack:1;  
  
```  
  
## Notes  
 Lié à la propriété **DBPROP\_CANSCROLLBACKWARDS** du groupe **DBPROPSET\_ROWSET**.  Le fournisseur doit prendre en charge **DBPROP\_CANSCROLLBACKWARDS** pour que **m\_bCanFetchBackwards** soit vraie.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IRowsetImpl, classe](../../data/oledb/irowsetimpl-class.md)   
 [IRowsetImpl::m\_bCanFetchBack](../../data/oledb/irowsetimpl-m-bcanfetchback.md)