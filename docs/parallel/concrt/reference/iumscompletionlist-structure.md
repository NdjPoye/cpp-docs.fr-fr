---
title: "IUMSCompletionList, structure | Microsoft Docs"
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
  - "concrtrm/concurrency::IUMSCompletionList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IUMSCompletionList (structure)"
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IUMSCompletionList, structure
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Représente une liste de saisie semi\-automatique UMS.  Lorsqu'un thread UMS se bloque, le contexte de planification désigné du planificateur est distribué afin de décider quoi planifier sur la racine de processeur virtuel sous\-jacente pendant que le thread d'origine est bloqué.  Lorsque le thread d'origine se débloque, le système d'exploitation le met en file d'attente dans la liste de saisie semi\-automatique qui est accessible via cette interface.  Le planificateur peut interroger la liste de saisie semi\-automatique sur le contexte de planification désigné ou tout autre emplacement sur lequel il recherche du travail.  
  
## Syntaxe  
  
```  
struct IUMSCompletionList;  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IUMSCompletionList::GetUnblockNotifications, méthode](../Topic/IUMSCompletionList::GetUnblockNotifications%20Method.md)|Récupère une chaîne d'interfaces `IUMSUnblockNotification` qui représentent des contextes d'exécution dont les proxys de thread associés se sont débloqués depuis le dernier appel de la méthode.|  
  
## Notes  
 Un planificateur doit être extraordinairement prudent concernant les actions à exécuter après avoir utilisé cette interface pour enlever de la file d'attente des éléments de la liste de saisie semi\-automatique.  Les éléments doivent être placés dans la liste de contextes exécutables du planificateur et être généralement accessible dès que possible.  Il est tout à fait possible que l'un des éléments retirés de la file d'attente ait reçu la propriété d'un verrou arbitraire.  Le planificateur ne peut pas passer d'appels de fonction arbitraires qui peuvent se bloquer entre l'appel de sortie des éléments de la file d'attente et le positionnement de ces éléments dans une liste généralement accessible depuis le planificateur.  
  
## Hiérarchie d'héritage  
 `IUMSCompletionList`  
  
## Configuration requise  
 **En\-tête :** concrtrm.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IUMSScheduler, structure](../../../parallel/concrt/reference/iumsscheduler-structure.md)   
 [IUMSUnblockNotification, structure](../../../parallel/concrt/reference/iumsunblocknotification-structure.md)