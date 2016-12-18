---
title: "DispatchState, structure | Microsoft Docs"
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
  - "concrtrm/concurrency::DispatchState"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DispatchState (structure)"
ms.assetid: 8c52546e-1650-48a0-985f-7e4a0fc26a90
caps.latest.revision: 17
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DispatchState, structure
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La structure `DispatchState` est utilisée pour transférer l'état à la méthode `IExecutionContext::Dispatch`.  Il décrit les circonstances sous lesquelles la méthode `Dispatch` est appelée sur une interface `IExecutionContext`.  
  
## Syntaxe  
  
```  
struct DispatchState;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[DispatchState::DispatchState, constructeur](../Topic/DispatchState::DispatchState%20Constructor.md)|Construit un nouvel objet `DispatchState`.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[Données membres DispatchState::m\_dispatchStateSize](../Topic/DispatchState::m_dispatchStateSize%20Data%20Member.md)|Taille de cette structure, utilisée pour le contrôle de version.|  
|[Données membres DispatchState::m\_fIsPreviousContextAsynchronouslyBlocked](../Topic/DispatchState::m_fIsPreviousContextAsynchronouslyBlocked%20Data%20Member.md)|Indique si ce contexte a entré la méthode `Dispatch` parce que le contexte précédent s'est bloqué de façon asynchrone.  Cela est utilisé uniquement sur le contexte de planification UMS et est défini sur la valeur `0` pour tous les autres contextes d'exécution.|  
|[Données membres DispatchState::m\_reserved](../Topic/DispatchState::m_reserved%20Data%20Member.md)|Bits réservés pour le passage de futures informations.|  
  
## Hiérarchie d'héritage  
 `DispatchState`  
  
## Configuration requise  
 **En\-tête :** concrtrm.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IExecutionContext::Dispatch, méthode](../Topic/IExecutionContext::Dispatch%20Method.md)