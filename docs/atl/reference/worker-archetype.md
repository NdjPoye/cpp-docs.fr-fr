---
title: "Worker Archetype | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Worker archetype"
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
caps.latest.revision: 16
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Worker Archetype
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les classes conformes à l'archétype *de travail* fournissent le code aux éléments de travail par processus mis en file d'attente sur un pool de threads.  
  
 **Implémentation**  
  
 Pour implémenter une classe conformes à cet archétype, la classe doit fournir les fonctionnalités suivantes :  
  
|Méthode|Description|  
|-------------|-----------------|  
|[Initialize](../Topic/WorkerArchetype::Initialize.md)|Appelé pour initialiser l'objet de travail avant toutes les demandes sont passés à [exécutez](../Topic/WorkerArchetype::Execute.md).|  
|[Execute](../Topic/WorkerArchetype::Execute.md)|Appelé pour traiter un élément de travail.|  
|[Terminer](../Topic/WorkerArchetype::Terminate.md)|Appelée pour uninitialize les requêtes d'objet de travail après que tous ont été passés à [exécutez](../Topic/WorkerArchetype::Execute.md).|  
  
|Typedef|Description|  
|-------------|-----------------|  
|[RequestType](../Topic/WorkerArchetype::RequestType.md)|Un typedef pour le type d'élément de travail qui peut être traité par la classe de travail.|  
  
 Recherche *de travail* typiques d'une classe ressemble à ceci :  
  
 [!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/CPP/worker-archetype_1.cpp)]  
  
 **Implémentations existantes**  
  
 Ces classes sont conformes à cet archétype :  
  
|Classe|Description|  
|------------|-----------------|  
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|Accepte les demandes du pool de threads et les transmet à un objet de travail créé et détruit pour chaque demande.|  
  
 **Utilisation**  
  
 Ces paramètres de modèle s'attendent à ce que la classe est conforme à cet archétype :  
  
|Nom de paramètre|Utilisé par|  
|----------------------|-----------------|  
|*Ouvrier*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|  
|*Ouvrier*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|  
  
## Configuration requise  
 **Header:** atlutil.h  
  
## Voir aussi  
 [Archetypes](../../atl/reference/atl-archetypes.md)   
 [Concepts](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md)