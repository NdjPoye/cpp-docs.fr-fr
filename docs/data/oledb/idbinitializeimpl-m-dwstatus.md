---
title: "IDBInitializeImpl::m_dwStatus | Microsoft Docs"
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
  - "ATL::IDBInitializeImpl::m_dwStatus"
  - "IDBInitializeImpl.m_dwStatus"
  - "ATL.IDBInitializeImpl.m_dwStatus"
  - "IDBInitializeImpl::m_dwStatus"
  - "IDBInitializeImpl<T>::m_dwStatus"
  - "ATL.IDBInitializeImpl<T>.m_dwStatus"
  - "ATL::IDBInitializeImpl<T>::m_dwStatus"
  - "m_dwStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_dwStatus"
ms.assetid: 7621ccff-ca60-4b75-9c6a-c104bd0e2038
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDBInitializeImpl::m_dwStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Indicateurs de source de données.  
  
## Syntaxe  
  
```  
  
DWORD m_dwStatus;  
  
```  
  
## Notes  
 Ces indicateurs spécifient ou indiquent l'état des attributs pour l'objet source de données.  Contient une ou plus des valeurs suivantes `enum` :  
  
 `enum DATASOURCE_FLAGS {`  
  
 `DSF_MASK_INIT     = 0xFFFFF00F,`  
  
 `DSF_PERSIST_DIRTY = 0x00000001,`  
  
 `DSF_INITIALIZED   = 0x00000010,`  
  
 `};`  
  
|||  
|-|-|  
|**DSF\_MASK\_INIT**|Un masque pour permettre la restauration de l'état non initialisé.|  
|**DSF\_PERSIST\_DIRTY**|Définit si l'objet source de données requiert la persistance \(autrement dit, s'il y a eu des modifications\).|  
|**DSF\_INITIALIZED**|Définit si la source de données a été initialisée.|  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IDBInitializeImpl, classe](../../data/oledb/idbinitializeimpl-class.md)   
 [IDBInitializeImpl::IDBInitializeImpl](../../data/oledb/idbinitializeimpl-idbinitializeimpl.md)   
 [IDBInitializeImpl::Uninitialize](../../data/oledb/idbinitializeimpl-uninitialize.md)