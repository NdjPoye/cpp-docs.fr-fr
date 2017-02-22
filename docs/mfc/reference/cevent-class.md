---
title: "CEvent Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CEvent"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CEvent class"
  - "classes de synchronisation, CEvent class"
  - "synchronization objects, event"
ms.assetid: df676042-ce27-4702-800a-e73ff4f44395
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CEvent Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente un événement, un objet de synchronisation qui permet à un thread d'informer les autres qu'un événement s'est produit.  
  
## Syntaxe  
  
```  
class CEvent : public CSyncObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CEvent::CEvent](../Topic/CEvent::CEvent.md)|Construit un objet `CEvent`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CEvent::PulseEvent](../Topic/CEvent::PulseEvent.md)|Place l'événement à des threads en attente disponibles signalé \(\), de versions, et aux ensembles l'événement à pas disponible \(non signalé\).|  
|[CEvent::ResetEvent](../Topic/CEvent::ResetEvent.md)|Place l'événement à pas disponible \(non signalé\).|  
|[CEvent::SetEvent](../Topic/CEvent::SetEvent.md)|Place l'événement à disponible \(signalé\) et aux versions tous les threads en attente.|  
|[CEvent::Unlock](../Topic/CEvent::Unlock.md)|Libère l'objet événement.|  
  
## Notes  
 Les événements sont utiles lorsqu'un thread doit savoir quand effectuer la tâche.  Par exemple, il doit annoncer un thread qui copie des données à une archive de données lorsque les nouvelles données sont disponibles.  À l'aide d'un objet d' `CEvent` pour indiquer à la copie thread lorsque les nouvelles données sont disponibles, le thread peut effectuer sa tâche dès que possible.  
  
 Les objets d'`CEvent` ont deux types : manuels et automatique.  
  
 Un objet automatique d' `CEvent` revient automatiquement à un état \(non disponible\) non signalé après avoir au moins un thread soit libéré.  Par défaut, un objet d' `CEvent` est automatique à moins que vous passer `TRUE` du paramètre d' `bManualReset` pendant la construction.  
  
 Un objet d' `CEvent` de manuel reste dans l'état défini par [SetEvent](../Topic/CEvent::SetEvent.md) ou [ResetEvent](../Topic/CEvent::ResetEvent.md) jusqu'à ce que l'autre fonction appelée.  Pour créer un objet manuel d' `CEvent` , exécutez `TRUE` du paramètre d' `bManualReset` pendant la construction.  
  
 Pour utiliser un objet d' `CEvent` , construisez l'objet d' `CEvent` lorsque nécessaire.  Spécifiez le nom de l'événement à attendre, et le spécifiez également que votre application doit initialement le propriétaire.  Vous pouvez ensuite accéder à l'événement lorsque le constructeur retourne.  Appelez [SetEvent](../Topic/CEvent::SetEvent.md) pour signaler \(rendre disponible\) l'objet événement puis appeler [déverrouillez](../Topic/CEvent::Unlock.md) lorsque vous avez terminé de l'accès à la ressource contrôlée.  
  
 Une autre méthode pour l'utilisation des objets d' `CEvent` consiste à ajouter une variable de type `CEvent` comme une donnée membre à la classe que vous souhaitez extraire.  Pendant la construction de l'objet contrôlé, appelez le constructeur de la donnée membre d' `CEvent` et le spécifier si l'événement est initialement signalé, et également type de specifythe d'objet événement à, le nom de l'événement \(s'il est utilisé au delà de les limites de processus\), et tous les attributs de sécurité vous souhaitez.  
  
 Pour accéder à une ressource contrôlée par un objet d' `CEvent` de cette manière, commencez par créer une variable de type [CSingleLock](../../mfc/reference/csinglelock-class.md) ou tapez [CMultiLock](../../mfc/reference/cmultilock-class.md) dans la méthode d'accès de votre ressource.  Appelez la méthode d' `Lock` d'objets lock \(par exemple, [CMultiLock::Lock](../Topic/CMultiLock::Lock.md)\).  À ce stade, votre thread accédera à la ressource attente, la ressource à libérer et accédera, ou attend la ressource à libérer, l'heure, et l'échec d'accéder à la ressource.  Dans tous les cas, la ressource a été accessible en mode thread\-safe.  Pour libérer les ressources, l'appel `SetEvent` pour signaler l'objet événement, puis pour utiliser la méthode d' `Unlock` d'objets lock \(par exemple, [CMultiLock::Unlock](../Topic/CMultiLock::Unlock.md)\), ou let l'objet lock blocage hors de portée.  
  
 Pour plus d'informations sur l'utilisation des objets d' `CEvent` , consultez [Multithreading : comment utiliser les classes de synchronisation](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## Exemple  
 [!code-cpp[NVC_MFC_Utilities#45](../../mfc/codesnippet/CPP/cevent-class_1.cpp)]  
  
 [!code-cpp[NVC_MFC_Utilities#46](../../mfc/codesnippet/CPP/cevent-class_2.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CEvent`  
  
## Configuration requise  
 **Header:** afxmt.h  
  
## Voir aussi  
 [CSyncObject Class](../../mfc/reference/csyncobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)