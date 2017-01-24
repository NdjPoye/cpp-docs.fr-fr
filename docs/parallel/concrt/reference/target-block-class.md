---
title: "target_block, classe | Microsoft Docs"
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
  - "agents/concurrency::target_block"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "target_block (classe)"
ms.assetid: 3ce181b4-b94a-4894-bf7b-64fc09821f9f
caps.latest.revision: 21
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# target_block, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe `target_block` est une classe de base abstraite qui fournit des fonctionnalités de gestion des liens de base et vérifie les erreurs pour les blocs cibles uniquement.  
  
## Syntaxe  
  
```  
template<  
   class _SourceLinkRegistry,  
   class _MessageProcessorType = ordered_message_processor<typename _SourceLinkRegistry::type::source_type>  
>  
class target_block : public ITarget<typename _SourceLinkRegistry::type::source_type>;  
```  
  
#### Paramètres  
 `_SourceLinkRegistry`  
 Registre de liens à utiliser pour contenir les liens source.  
  
 `_MessageProcessorType`  
 Type de processeur pour le traitement du message.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`source_iterator`|Type de l'itérateur pour `source_link_manager` pour cet objet `target_block`.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[target\_block::target\_block, constructeur](../Topic/target_block::target_block%20Constructor.md)|Construit un objet `target_block`.|  
|[target\_block::~target\_block, destructeur](../Topic/target_block::~target_block%20Destructor.md)|Détruit l'objet `target_block`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[target\_block::propagate, méthode](../Topic/target_block::propagate%20Method.md)|Passe un message de façon asynchrone d'un bloc source à ce bloc cible.|  
|[target\_block::send, méthode](../Topic/target_block::send%20Method.md)|Passe de façon synchrone un message du bloc source au bloc cible.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[target\_block::async\_send, méthode](../Topic/target_block::async_send%20Method.md)|Envoie un message en traitement de façon asynchrone.|  
|[target\_block::decline\_incoming\_messages, méthode](../Topic/target_block::decline_incoming_messages%20Method.md)|Indique au bloc que les nouveaux messages doivent être refusés.|  
|[target\_block::enable\_batched\_processing, méthode](../Topic/target_block::enable_batched_processing%20Method.md)|Permet de traiter en lots pour ce bloc.|  
|[target\_block::initialize\_target, méthode](../Topic/target_block::initialize_target%20Method.md)|Initialise l'objet de base.  Spécifiquement, l'objet `message_processor` doit être initialisé.|  
|[target\_block::link\_source, méthode](../Topic/target_block::link_source%20Method.md)|Lie un bloc source spécifié à cet objet `target_block`.|  
|[target\_block::process\_input\_messages, méthode](../Topic/target_block::process_input_messages%20Method.md)|Traite les messages qui sont reçus comme entrées.|  
|[target\_block::process\_message, méthode](../Topic/target_block::process_message%20Method.md)|En cas de substitution dans une classe dérivée, traite un message qui a été accepté par cet objet `target_block`.|  
|[target\_block::propagate\_message, méthode](../Topic/target_block::propagate_message%20Method.md)|En cas de substitution dans une classe dérivée, cette méthode passe de façon asynchrone un message d'un bloc `ISource` à cet objet `target_block`.  Il est appelé par la méthode `propagate`, en cas d'appel par un bloc source.|  
|[target\_block::register\_filter, méthode](../Topic/target_block::register_filter%20Method.md)|Inscrit une méthode de filtre qui sera appelée sur chaque message reçu.|  
|[target\_block::remove\_sources, méthode](../Topic/target_block::remove_sources%20Method.md)|Dissocie toutes les sources après avoir attendu que les opérations d'envoi asynchrones en attente soient terminées.|  
|[target\_block::send\_message, méthode](../Topic/target_block::send_message%20Method.md)|En cas de substitution dans une classe dérivée, cette méthode passe de façon synchrone un message d'un bloc `ISource` à cet objet `target_block`.  Il est appelé par la méthode `send`, en cas d'appel par un bloc source.|  
|[target\_block::sync\_send, méthode](../Topic/target_block::sync_send%20Method.md)|Envoie un message de manière synchrone pour le traitement.|  
|[target\_block::unlink\_source, méthode](../Topic/target_block::unlink_source%20Method.md)|Dissocie un bloc source spécifié de cet objet `target_block`.|  
|[target\_block::unlink\_sources, méthode](../Topic/target_block::unlink_sources%20Method.md)|Dissocie tous les blocs source de cet objet `target_block`. \(Substitue [ITarget::unlink\_sources](../Topic/ITarget::unlink_sources%20Method.md).\)|  
|[target\_block::wait\_for\_async\_sends, méthode](../Topic/target_block::wait_for_async_sends%20Method.md)|Attend que toutes les propagations asynchrones soient terminées.|  
  
## Hiérarchie d'héritage  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 `target_block`  
  
## Configuration requise  
 **En\-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [ITarget, classe](../../../parallel/concrt/reference/itarget-class.md)