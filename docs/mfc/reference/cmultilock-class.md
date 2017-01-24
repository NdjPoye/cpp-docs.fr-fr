---
title: "CMultiLock Class | Microsoft Docs"
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
  - "CMultiLock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMultiLock class"
  - "synchronization objects, contrôle d'accès"
ms.assetid: c5b7c78b-1f81-4387-b7dd-2c813c5b6b61
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMultiLock Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente le mécanisme de contrôle d'accès utilisé pour accéder aux ressources dans un programme multithread.  
  
## Syntaxe  
  
```  
class CMultiLock  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMultiLock::CMultiLock](../Topic/CMultiLock::CMultiLock.md)|Construit un objet `CMultiLock`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMultiLock::IsLocked](../Topic/CMultiLock::IsLocked.md)|Détermine si un objet de synchronisation spécifique dans le tableau est verrouillé.|  
|[CMultiLock::Lock](../Topic/CMultiLock::Lock.md)|Attentes du tableau d'objets de synchronisation.|  
|[CMultiLock::Unlock](../Topic/CMultiLock::Unlock.md)|Récupère tous les objets de synchronisation qui appartiennent.|  
  
## Notes  
 `CMultiLock` n'a pas de classe de base.  
  
 Pour utiliser les classes [CSemaphore](../../mfc/reference/csemaphore-class.md)de synchronisation, [CMutex](../../mfc/reference/cmutex-class.md), et [CEvent](../../mfc/reference/cevent-class.md), vous pouvez créer un objet de **CMultiLock** ou de [CSingleLock](../../mfc/reference/csinglelock-class.md) à l'attente sur et libérer l'objet de synchronisation.  Utilisez **CMultiLock** lorsqu'il existe plusieurs objets que vous pouvez utiliser à un moment donné.  Utilisez `CSingleLock` lorsque vous devez seulement attendre un objet à la fois.  
  
 Pour utiliser un objet de **CMultiLock** , créez d'abord un tableau des objets de synchronisation dans lequel vous souhaitez à l'attente.  Ensuite, appelez le constructeur de l'objet de **CMultiLock** à l'intérieur d'une fonction membre dans la classe de la ressource contrôlée.  Appelez la fonction membre de [Verrouillage](../Topic/CMultiLock::Lock.md) pour déterminer si une ressource est disponible \(signalé\).  Si l'un est le cas, passez le reste de la fonction membre.  Si aucune ressource n'est disponible, attendez une quantité spécifique de temps pour une ressource est libérée, ou retournez l'échec.  Après l'utilisation d'une ressource est terminé, soit d'appeler la fonction de [déverrouillez](../Topic/CMultiLock::Unlock.md) si l'objet de **CMultiLock** doit être utilisé de nouveau, ou autorisent l'objet de **CMultiLock** à détruire.  
  
 Les objets de**CMultiLock** sont très utiles lorsqu'un thread possède un grand nombre d'objets d' `CEvent` qu'il peut répondre.  Créez un tableau contenant tous les pointeurs d' `CEvent` , puis appelez `Lock`.  Cela fait attendre que le thread jusqu'à ce que l'une des événements soit signalé.  
  
 Pour plus d'informations sur l'utilisation des objets de **CMultiLock** , consultez l'article [Multithreading : Comment utiliser les classes de synchronisation](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## Hiérarchie d'héritage  
 `CMultiLock`  
  
## Configuration requise  
 **Header:** afxmt.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)