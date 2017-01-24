---
title: "CThreadPool Class | Microsoft Docs"
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
  - "ATL.CThreadPool"
  - "ATL::CThreadPool"
  - "CThreadPool"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CThreadPool class"
ms.assetid: 06683718-01b9-413c-9481-2dc1734ec70f
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CThreadPool Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit un pool de threads de travail qui traitent une file d'attente des éléments de travail.  
  
## Syntaxe  
  
```  
  
      template <  
   class Worker,  
   class ThreadTraits = DefaultThreadTraits  
>  
class CThreadPool :  
   public IThreadPoolConfig  
```  
  
#### Paramètres  
 *ouvrier*  
 La classe conformes à [archétype de travail](../../atl/reference/worker-archetype.md) fournissant le code celle utilisée à des éléments de travail par processus mis en file d'attente sur le pool de threads.  
  
 `ThreadTraits`  
 La classe fournissant la fonction utilisée pour créer des threads dans le pool.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CThreadPool::CThreadPool](../Topic/CThreadPool::CThreadPool.md)|Le constructeur pour le pool de threads.|  
|[CThreadPool::~CThreadPool](../Topic/CThreadPool::~CThreadPool.md)|Le destructeur du pool de threads.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CThreadPool::AddRef](../Topic/CThreadPool::AddRef.md)|Implémentation de `IUnknown::AddRef`.|  
|[CThreadPool::GetNumThreads](../Topic/CThreadPool::GetNumThreads.md)|Appelez cette méthode pour obtenir le nombre de threads dans le pool.|  
|[CThreadPool::GetQueueHandle](../Topic/CThreadPool::GetQueueHandle.md)|Appelez cette méthode pour obtenir le handle du port de terminaison d'E\/S utilisé aux éléments de travail de file d'attente.|  
|[CThreadPool::GetSize](../Topic/CThreadPool::GetSize.md)|Appelez cette méthode pour obtenir le nombre de threads dans le pool.|  
|[CThreadPool::GetTimeout](../Topic/CThreadPool::GetTimeout.md)|Appelez cette méthode pour obtenir le temps maximum en millisecondes que le pool de threads attend un thread s'arrête.|  
|[CThreadPool::Initialize](../Topic/CThreadPool::Initialize.md)|Appelez cette méthode pour initialiser le pool de threads.|  
|[CThreadPool::QueryInterface](../Topic/CThreadPool::QueryInterface.md)|Implémentation d' **IUnknown::QueryInterface**.|  
|[CThreadPool::QueueRequest](../Topic/CThreadPool::QueueRequest.md)|Appelez cette méthode pour mettre en file d'attente un élément de travail à gérer par un thread du pool.|  
|[CThreadPool::Release](../Topic/CThreadPool::Release.md)|Implémentation de `IUnknown::Release`.|  
|[CThreadPool::SetSize](../Topic/CThreadPool::SetSize.md)|Appelez cette méthode pour définir le nombre de threads dans le pool.|  
|[CThreadPool::SetTimeout](../Topic/CThreadPool::SetTimeout.md)|Appelez cette méthode pour définir le temps maximum en millisecondes que le pool de threads attend un thread s'arrête.|  
|[CThreadPool::Shutdown](../Topic/CThreadPool::Shutdown.md)|Appelez cette méthode pour arrêter le pool de threads.|  
  
## Notes  
 Les threads du pool sont créés et détruits lorsque le pool est initialisé, redimensionné, ou désactivé.  Une instance *d'ouvrier* de classe est créée sur la pile de chaque thread de travail dans le pool.  Chaque instance vivra pour la durée de vie du thread.  
  
 Immédiatement après la création d'un thread, Worker::`Initialize` sera invité à l'objet associé à ce thread.  Juste avant la destruction d'un thread, Worker::`Terminate` est appelé.  Les deux méthodes doivent accepter un argument de **void\*** .  La valeur de cet argument est passé au pool de threads via le paramètre d' `pvWorkerParam` de [CThreadPool::Initialize](../Topic/CThreadPool::Initialize.md).  
  
 Lorsqu'il existe des éléments de travail dans la file d'attente et les threads de travail disponibles pour le travail, un thread de travail supprime un élément la file d'attente et appelle la méthode de **Exécuter***d'objet de travail* de ce thread.  Trois éléments sont alors passés à la méthode : l'élément de la file d'attente, de même `pvWorkerParam` passé à Worker::`Initialize` et à Worker::`Terminate`, et d'un pointeur vers la structure d' [OVERLAPPED](http://msdn.microsoft.com/library/windows/desktop/ms684342) utilisée pour la file d'attente de ports de terminaison d'E\/S.  
  
 La classe *de travail* déclare le type des éléments qui seront mises en file d'attente sur le pool de threads en fournissant un typedef, Worker::`RequestType`.  Ce type doit être capable de le cast vers et à partir de **ULONG\_PTR**.  
  
 Un exemple d'une classe *de travail* est [CNonStatelessWorker Class](../../atl/reference/cnonstatelessworker-class.md).  
  
## Hiérarchie d'héritage  
 `IUnknown`  
  
 [IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)  
  
 `CThreadPool`  
  
## Configuration requise  
 **Header:** atlutil.h  
  
## Voir aussi  
 [IThreadPoolConfig Interface](../../atl/reference/ithreadpoolconfig-interface.md)   
 [DefaultThreadTraits](../Topic/DefaultThreadTraits.md)   
 [Classes](../../atl/reference/atl-classes.md)