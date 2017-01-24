---
title: "CSyncObject Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSyncObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSyncObject class"
  - "classes de synchronisation, CSyncObject"
ms.assetid: c62ea6eb-a17b-4e01-aed4-321fc435a5f4
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSyncObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une classe virtuelle pure qui fournit des fonctionnalités communes aux objets de synchronisation dans Win32.  
  
## Syntaxe  
  
```  
class CSyncObject : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSyncObject::CSyncObject](../Topic/CSyncObject::CSyncObject.md)|Construit un objet `CSyncObject`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSyncObject::Lock](../Topic/CSyncObject::Lock.md)|Accède à l'objet de synchronisation.|  
|[CSyncObject::Unlock](../Topic/CSyncObject::Unlock.md)|Accède à l'objet de synchronisation.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSyncObject::operator HANDLE](../Topic/CSyncObject::operator%20HANDLE.md)|Permet d'accéder à l'objet de synchronisation.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSyncObject::m\_hObject](../Topic/CSyncObject::m_hObject.md)|Le handle vers l'objet de synchronisation sous\-jacent.|  
  
## Notes  
 La bibliothèque MFC fournit plusieurs classes dérivées d' `CSyncObject`.  Ce sont [CEvent](../../mfc/reference/cevent-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), et [CSemaphore](../../mfc/reference/csemaphore-class.md).  
  
 Pour plus d'informations sur l'utilisation des objets de synchronisation, consultez l'article [Multithreading : Comment utiliser les classes de synchronisation](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CSyncObject`  
  
## Configuration requise  
 **Header:** afxmt.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)