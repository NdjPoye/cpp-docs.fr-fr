---
title: "DeferrableEventArgs::InvokeAllFinished (m&#233;thode) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 86b45205-3edb-4134-9cd0-ed7a7b4c3b1a
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# DeferrableEventArgs::InvokeAllFinished (m&#233;thode)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Appelée pour indiquer que toutes les opérations de traitement d'un événement différé sont terminées.  
  
## Syntaxe  
  
```cpp  
void InvokeAllFinished()  
```  
  
## Notes  
 Vous devez appeler cette méthode après l'appel à [InvokeAll](../windows/eventsource-invokeall-method.md) par la source de l'événement.  L'appel à cette méthode empêche tout autre report et force l'exécution du gestionnaire d'achèvement en l'absence de report.  
  
 Pour obtenir un exemple de code, voir [DeferrableEventArgs, classe](../windows/deferrableeventargs-class.md).  
  
## Configuration requise  
 **En\-tête** : event.h  
  
 **Espace de noms** : Microsoft::WRL  
  
## Voir aussi  
 [DeferrableEventArgs, classe](../windows/deferrableeventargs-class.md)   
 [EventSource::InvokeAll, méthode](../windows/eventsource-invokeall-method.md)