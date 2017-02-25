---
title: "ordered_message_processor, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::ordered_message_processor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ordered_message_processor (classe)"
ms.assetid: 787adfb7-7f79-4a70-864a-80e3b64088cd
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# ordered_message_processor, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Un `ordered_message_processor` est un `message_processor` qui permet aux blocs de messages de traiter les messages dans l'ordre dans lequel ils ont été reçus.  
  
## Syntaxe  
  
```  
template<  
   class _Type  
>  
class ordered_message_processor : public message_processor<_Type>;  
```  
  
#### Paramètres  
 `_Type`  
 Le type de charge utile des messages gérés par le processeur.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`type`|Alias de type pour `_Type`.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[ordered\_message\_processor::ordered\_message\_processor, constructeur](../Topic/ordered_message_processor::ordered_message_processor%20Constructor.md)|Construit un objet `ordered_message_processor`.|  
|[ordered\_message\_processor::~ordered\_message\_processor, destructeur](../Topic/ordered_message_processor::~ordered_message_processor%20Destructor.md)|Détruit l'objet `ordered_message_processor`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[ordered\_message\_processor::async\_send, méthode](../Topic/ordered_message_processor::async_send%20Method.md)|Place les messages en file d'attente et démarre une tâche de traitement de façon asynchrone, si cela n'a pas déjà été fait. \(Substitue [message\_processor::async\_send](../Topic/message_processor::async_send%20Method.md).\)|  
|[ordered\_message\_processor::initialize, méthode](../Topic/ordered_message_processor::initialize%20Method.md)|Initialise l'objet `ordered_message_processor` avec la fonction de rappel, le planificateur et le groupe de planification appropriés.|  
|[ordered\_message\_processor::initialize\_batched\_processing, méthode](../Topic/ordered_message_processor::initialize_batched_processing%20Method.md)|Initialise le traitement des messages en lots|  
|[ordered\_message\_processor::sync\_send, méthode](../Topic/ordered_message_processor::sync_send%20Method.md)|Met en file d'attente de façon synchrone des messages et démarre une tâche de traitement, si cela n'a pas déjà été fait. \(Substitue [message\_processor::sync\_send](../Topic/message_processor::sync_send%20Method.md).\)|  
|[ordered\_message\_processor::wait, méthode](../Topic/ordered_message_processor::wait%20Method.md)|Attente de rotation spécifique au processeur utilisée dans les destructeurs de blocs de messages pour s'assurer que toutes les tâches de traitement asynchrone ont le temps de finir avant la destruction du bloc. \(Substitue [message\_processor::wait](../Topic/message_processor::wait%20Method.md).\)|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[ordered\_message\_processor::process\_incoming\_message, méthode](../Topic/ordered_message_processor::process_incoming_message%20Method.md)|Fonction de traitement appelée de façon asynchrone.  Il retire les messages de la file d'attente et commence à les traiter. \(Substitue [message\_processor::process\_incoming\_message](../Topic/message_processor::process_incoming_message%20Method.md).\)|  
  
## Hiérarchie d'héritage  
 [message\_processor](../../../parallel/concrt/reference/message-processor-class.md)  
  
 `ordered_message_processor`  
  
## Configuration requise  
 **En\-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)