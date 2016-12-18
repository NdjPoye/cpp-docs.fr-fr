---
title: "message_processor, classe | Microsoft Docs"
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
  - "agents/concurrency::message_processor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "message_processor (classe)"
ms.assetid: 23afb052-daa7-44ed-bf24-d2513db748da
caps.latest.revision: 16
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# message_processor, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe `message_processor` est la classe de base abstraite pour le traitement d'objets `message`.  Il n'y a aucune garantie sur le classement des messages.  
  
## Syntaxe  
  
```  
template<  
   class _Type  
>  
class message_processor;  
```  
  
#### Paramètres  
 `_Type`  
 Le type de données de la charge utile dans les messages gérés par cet objet `message_processor`.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`type`|Alias de type pour `_Type`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[message\_processor::async\_send, méthode](../Topic/message_processor::async_send%20Method.md)|En cas de substitution dans une classe dérivée, place de façon asynchrone des messages dans le bloc.|  
|[message\_processor::sync\_send, méthode](../Topic/message_processor::sync_send%20Method.md)|En cas de substitution dans une classe dérivée, place de façon synchrone des messages dans le bloc.|  
|[message\_processor::wait, méthode](../Topic/message_processor::wait%20Method.md)|En cas de substitution dans une classe dérivée, attend que toutes les opérations asynchrones se terminent.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[message\_processor::process\_incoming\_message, méthode](../Topic/message_processor::process_incoming_message%20Method.md)|En cas de substitution dans une classe dérivée, exécute le traitement de transfert des messages dans le bloc.  Appelé à chaque fois qu'un nouveau message est ajouté et que la file d'attente se trouve être vide.|  
  
## Hiérarchie d'héritage  
 `message_processor`  
  
## Configuration requise  
 **En\-tête :** agents.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [ordered\_message\_processor, classe](../../../parallel/concrt/reference/ordered-message-processor-class.md)