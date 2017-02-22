---
title: "CNonStatelessWorker Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CNonStatelessWorker<Worker>"
  - "ATL::CNonStatelessWorker"
  - "ATL.CNonStatelessWorker"
  - "CNonStatelessWorker"
  - "ATL::CNonStatelessWorker<Worker>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CNonStatelessWorker class"
ms.assetid: d00936c6-9e7d-49fb-b87d-417b963367d1
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CNonStatelessWorker Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Accepte les demandes d'un pool de threads et les transmet à un objet de travail créé et détruit à chaque requête.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template <  
class Worker  
>  
class CNonStatelessWorker  
```  
  
#### Paramètres  
 *ouvrier*  
 Une classe de threads de travail conformes à [archétype de travail](../../atl/reference/worker-archetype.md) approprié pour gérer les demandes a mis en file d'attente sur [CThreadPool](../../atl/reference/cthreadpool-class.md).  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CNonStatelessWorker::RequestType](../Topic/CNonStatelessWorker::RequestType.md)|Implémentation de [WorkerArchetype::RequestType](../Topic/WorkerArchetype::RequestType.md).|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CNonStatelessWorker::Execute](../Topic/CNonStatelessWorker::Execute.md)|Implémentation de [WorkerArchetype::Execute](../Topic/WorkerArchetype::Execute.md).|  
|[CNonStatelessWorker::Initialize](../Topic/CNonStatelessWorker::Initialize.md)|Implémentation de [WorkerArchetype::Initialize](../Topic/WorkerArchetype::Initialize.md).|  
|[CNonStatelessWorker::Terminate](../Topic/CNonStatelessWorker::Terminate.md)|Implémentation de [WorkerArchetype::Terminate](../Topic/WorkerArchetype::Terminate.md).|  
  
## Notes  
 Cette classe est un thread de travail simple à utiliser avec [CThreadPool](../../atl/reference/cthreadpool-class.md).  Cette classe ne fournit aucune fonction de gestion des demandes de ses propres.  À la place, il instancie une instance *d'ouvrier* par demande et délègue l'implémentation de ses méthodes à cette instance.  
  
 L'avantage de cette classe est qu'il offre un moyen pratique de modifier le modèle d'état pour les classes existantes de threads de travail.  `CThreadPool` crée un ouvrier unique pour la durée de vie du thread, si l'état HOLD de travail de classe, il contiendra sur plusieurs demandes.  En encapsulant simplement cette classe dans le modèle d' `CNonStatelessWorker` avant de l'utiliser avec `CThreadPool`, la durée de vie de l'ouvrier et l'état qu'elle se maintient est limitée à une requête unique.  
  
## Configuration requise  
 **Header:** atlutil.h  
  
## Voir aussi  
 [CThreadPool Class](../../atl/reference/cthreadpool-class.md)   
 [Worker Archetype](../../atl/reference/worker-archetype.md)   
 [Classes](../../atl/reference/atl-classes.md)