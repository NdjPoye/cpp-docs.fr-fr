---
title: "CSingleLock Class | Microsoft Docs"
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
  - "CSingleLock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSingleLock class"
  - "synchronization objects, contrôle d'accès"
  - "threads (MFC), contrôle d'accès"
  - "threads (MFC), synchronisation"
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSingleLock Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente le mécanisme de contrôle d'accès utilisé dans le contrôle de l'accès à une ressource dans un programme multithread.  
  
## Syntaxe  
  
```  
  
class CSingleLock  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSingleLock::CSingleLock](../Topic/CSingleLock::CSingleLock.md)|Construit un objet `CSingleLock`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSingleLock::IsLocked](../Topic/CSingleLock::IsLocked.md)|Détermine si l'objet est verrouillé.|  
|[CSingleLock::Lock](../Topic/CSingleLock::Lock.md)|Attend sur un objet de synchronisation.|  
|[CSingleLock::Unlock](../Topic/CSingleLock::Unlock.md)|Récupère un objet de synchronisation.|  
  
## Notes  
 `CSingleLock` n'a pas de classe de base.  
  
 Pour utiliser les classes [CSemaphore](../../mfc/reference/csemaphore-class.md)de synchronisation, [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), et [CEvent](../../mfc/reference/cevent-class.md), vous devez créer `CSingleLock` ou l'objet de [CMultiLock](../../mfc/reference/cmultilock-class.md) à l'attente sur et libérer l'objet de synchronisation.  Utilisez `CSingleLock` lorsque vous devez seulement attendre un objet à la fois.  Utilisez **CMultiLock** lorsqu'il existe plusieurs objets que vous pouvez utiliser à un moment donné.  
  
 Pour utiliser un objet d' `CSingleLock` , appelez son constructeur dans une fonction membre dans la classe de la ressource contrôlée.  Appelez la fonction membre d' [IsLocked](../Topic/CSingleLock::IsLocked.md) pour déterminer si la ressource est disponible.  Si tel est le cas, passez le reste de la fonction membre.  Si la ressource n'est pas disponible, attendez une quantité spécifique de temps pour que la ressource est libérée, ou retournez l'échec.  Après l'utilisation de la ressource est terminé, soit d'appeler la fonction de [déverrouillez](../Topic/CSingleLock::Unlock.md) si l'objet d' `CSingleLock` doit être utilisé de nouveau, ou autorisent l'objet d' `CSingleLock` à détruire.  
  
 Les objets d'`CSingleLock` nécessitent la présence d'un objet dérivé de [CSyncObject](../../mfc/reference/csyncobject-class.md).  Il s'agit généralement une donnée membre de la classe de la ressource contrôlée.  Pour plus d'informations sur l'utilisation des objets d' `CSingleLock` , consultez l'article [Multithreading : Comment utiliser les classes de synchronisation](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## Hiérarchie d'héritage  
 `CSingleLock`  
  
## Configuration requise  
 **Header:** afxmt.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CMultiLock Class](../../mfc/reference/cmultilock-class.md)