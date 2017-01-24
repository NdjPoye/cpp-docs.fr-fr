---
title: "completion_future, classe | Microsoft Docs"
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
  - "amprt/Concurrency::completion_future"
dev_langs: 
  - "C++"
ms.assetid: 1303c62e-546d-4b02-a578-251ed3fc0b6b
caps.latest.revision: 8
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# completion_future, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Représente un futur correspondant à l'opération asynchrone C\+\+ AMP.  
  
## Syntaxe  
  
```  
class completion_future;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[completion\_future::completion\_future, constructeur](../Topic/completion_future::completion_future%20Constructor.md)|Initialise une nouvelle instance de la classe `completion_future`.|  
|[completion\_future::~completion\_future, destructeur](../Topic/completion_future::~completion_future%20Destructor.md)|Détruit l'objet `completion_future`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[completion\_future::get, méthode](../Topic/completion_future::get%20Method.md)|Attend la fin de l'opération asynchrone associée.|  
|[completion\_future::then, méthode](../Topic/completion_future::then%20Method.md)|Chaîne un objet de fonction de rappel à l'objet `completion_future` à exécuter lorsque l'opération asynchrone associée termine l'opération.|  
|[completion\_future::to\_task, méthode](../Topic/completion_future::to_task%20Method.md)|Retourne un objet `task` correspondant à l'opération asynchrone associée.|  
|[completion\_future::valid, méthode](../Topic/completion_future::valid%20Method.md)|Obtient une valeur booléenne qui indique si l'objet est associé à une opération asynchrone.|  
|[completion\_future::wait, méthode](../Topic/completion_future::wait%20Method.md)|Bloque jusqu'à ce que l'opération asynchrone associée se termine.|  
|[completion\_future::wait\_for, méthode](../Topic/completion_future::wait_for%20Method.md)|Bloque jusqu'à ce que l'opération asynchrone associée se termine ou que le délai spécifié par `_Rel_time` soit écoulé.|  
|[completion\_future::wait\_until, méthode](../Topic/completion_future::wait_until%20Method.md)|Bloque jusqu'à ce que l'opération asynchrone associée se termine ou jusqu'à que le temps en cours dépasse la valeur spécifiée par `_Abs_time`.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[Opérateur completion\_future::operator std::shared\_future\<void\>](../Topic/completion_future::operator%20std::shared_future%3Cvoid%3E%20Operator.md)|Convertit implicitement l'objet `completion_future` en un objet `std::shared_future`.|  
|[completion\_future::operator\=, opérateur](../Topic/completion_future::operator=%20Operator.md)|Copie le contenu de l'objet `completion_future` spécifié dans cet objet.|  
  
## Hiérarchie d'héritage  
 `completion_future`  
  
## Configuration requise  
 **En\-tête :** amprt.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [Concurrency, espace de noms \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)