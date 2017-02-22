---
title: "CWorkerThread Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CWorkerThread<ThreadTraits>"
  - "ATL::CWorkerThread"
  - "ATL.CWorkerThread"
  - "ATL.CWorkerThread<ThreadTraits>"
  - "CWorkerThread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWorkerThread class"
ms.assetid: be79a832-1345-4a36-a13e-a406cc65286f
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CWorkerThread Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe crée un thread de travail ou utilise existant, attend un ou plusieurs handles d'objet de noyau, puis exécute une fonction cliente spécifiée lorsque l'une des poignées est signalé.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template <  
class ThreadTraits= DefaultThreadTraits  
>  
class CWorkerThread  
```  
  
#### Paramètres  
 `ThreadTraits`  
 La classe fournissant la fonction de création de thread, telle que [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) ou [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md).  
  
## Membres  
  
### Structures protégées  
  
|Nom|Description|  
|---------|-----------------|  
|`WorkerClientEntry`||  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CWorkerThread::CWorkerThread](../Topic/CWorkerThread::CWorkerThread.md)|Le constructeur pour le thread de travail.|  
|[CWorkerThread::~CWorkerThread](../Topic/CWorkerThread::~CWorkerThread.md)|Le destructeur de le thread de travail.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CWorkerThread::AddHandle](../Topic/CWorkerThread::AddHandle.md)|Appelez cette méthode pour ajouter le handle d'un objet de type waitable à la liste mise à jour par le thread de travail.|  
|[CWorkerThread::AddTimer](../Topic/CWorkerThread::AddTimer.md)|Appelez cette méthode pour ajouter une minuterie waitable périodique à la liste mise à jour par le thread de travail.|  
|[CWorkerThread::GetThreadHandle](../Topic/CWorkerThread::GetThreadHandle.md)|Appelez cette méthode pour obtenir le handle du thread du thread de travail.|  
|[CWorkerThread::GetThreadId](../Topic/CWorkerThread::GetThreadId.md)|Appelez cette méthode pour obtenir l'ID de thread du thread de travail.|  
|[CWorkerThread::Initialize](../Topic/CWorkerThread::Initialize.md)|Appelez cette méthode pour démarrer le thread de travail.|  
|[CWorkerThread::RemoveHandle](../Topic/CWorkerThread::RemoveHandle.md)|Appelez cette méthode pour supprimer un handle de la liste d'objets de type waitable.|  
|[CWorkerThread::Shutdown](../Topic/CWorkerThread::Shutdown.md)|Appelez cette méthode pour arrêter le thread de travail.|  
  
## Notes  
  
### Pour utiliser CWorkerThread  
  
1.  Créez une instance de cette classe.  
  
2.  Appel [CWorkerThread::Initialize](../Topic/CWorkerThread::Initialize.md).  
  
3.  Appel [CWorkerThread::AddHandle](../Topic/CWorkerThread::AddHandle.md) avec le handle d'un objet de noyau et un pointeur vers une implémentation d' [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md).  
  
     \- ou \-  
  
     Appelez [CWorkerThread::AddTimer](../Topic/CWorkerThread::AddTimer.md) avec un pointeur vers une implémentation d' [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md).  
  
4.  Implémentez [IWorkerThreadClient::Execute](../Topic/IWorkerThreadClient::Execute.md) pour prendre une certaine mesure lorsque le handle ou la minuterie est signalé.  
  
5.  Pour supprimer un objet de la liste d'objets de type waitable, appelez [CWorkerThread::RemoveHandle](../Topic/CWorkerThread::RemoveHandle.md).  
  
6.  Pour terminer le thread, appelez [CWorkerThread::Shutdown](../Topic/CWorkerThread::Shutdown.md).  
  
## Configuration requise  
 **Header:** atlutil.h  
  
## Voir aussi  
 [DefaultThreadTraits](../Topic/DefaultThreadTraits.md)   
 [Classes](../../atl/reference/atl-classes.md)   
 [Multithreading : création de threads de travail](../../parallel/multithreading-creating-worker-threads.md)   
 [IWorkerThreadClient Interface](../../atl/reference/iworkerthreadclient-interface.md)