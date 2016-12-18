---
title: "IUMSUnblockNotification, structure | Microsoft Docs"
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
  - "concrtrm/concurrency::IUMSUnblockNotification"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IUMSUnblockNotification (structure)"
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IUMSUnblockNotification, structure
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Représente une notification du Gestionnaire de ressources informant qu'un proxy de thread bloqué ayant déclenché un retour au contexte de planification désigné du planificateur est maintenant débloqué et prêt à être planifié.  Cette interface n'est pas valide une fois le contexte d'exécution associé du proxy de thread, retourné par la méthode `GetContext`, est replanifié.  
  
## Syntaxe  
  
```  
struct IUMSUnblockNotification;  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IUMSUnblockNotification::GetContext, méthode](../Topic/IUMSUnblockNotification::GetContext%20Method.md)|Retourne l'interface `IExecutionContext` pour le contexte d'exécution associé au proxy de thread qui s'est débloqué.  Une fois cette méthode retournée et le contexte d'exécution sous\-jacent replanifié via un appel à la méthode `IThreadProxy::SwitchTo`, cette interface n'est plus valide.|  
|[IUMSUnblockNotification::GetNextUnblockNotification, méthode](../Topic/IUMSUnblockNotification::GetNextUnblockNotification%20Method.md)|Retourne l'interface `IUMSUnblockNotification` suivante dans la chaîne retournée par la méthode `IUMSCompletionList::GetUnblockNotifications`.|  
  
## Hiérarchie d'héritage  
 `IUMSUnblockNotification`  
  
## Configuration requise  
 **En\-tête :** concrtrm.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IUMSScheduler, structure](../../../parallel/concrt/reference/iumsscheduler-structure.md)   
 [IUMSCompletionList, structure](../../../parallel/concrt/reference/iumscompletionlist-structure.md)