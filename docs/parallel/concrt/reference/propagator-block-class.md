---
title: "propagator_block, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::propagator_block"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "propagator_block (classe)"
ms.assetid: 86aa75fd-eda5-42aa-aadf-25c0c1c9742d
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# propagator_block, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe `propagator_block` est une classe de base abstraite pour les blocs de messages qui sont à la fois une source et une cible.  Il combine les fonctionnalités des classes `target_block` et `source_block`.  
  
## Syntaxe  
  
```  
template<  
   class _TargetLinkRegistry,  
   class _SourceLinkRegistry,  
   class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>  
>  
class propagator_block : public source_block<_TargetLinkRegistry, _MessageProcessorType>, public ITarget<typename _SourceLinkRegistry::type::source_type>;  
```  
  
#### Paramètres  
 `_TargetLinkRegistry`  
 Registre de liens à utiliser pour contenir les liens cibles.  
  
 `_SourceLinkRegistry`  
 Registre de liens à utiliser pour contenir les liens source.  
  
 `_MessageProcessorType`  
 Type de processeur pour le traitement du message.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`source_iterator`|Type de l'itérateur pour `source_link_manager` pour ce `propagator_block`.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[propagator\_block::propagator\_block, constructeur](../Topic/propagator_block::propagator_block%20Constructor.md)|Construit un objet `propagator_block`.|  
|[propagator\_block::~propagator\_block, destructeur](../Topic/propagator_block::~propagator_block%20Destructor.md)|Détruit un objet `propagator_block`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[propagator\_block::propagate, méthode](../Topic/propagator_block::propagate%20Method.md)|Passe un message de façon asynchrone d'un bloc source à ce bloc cible.|  
|[propagator\_block::send, méthode](../Topic/propagator_block::send%20Method.md)|Démarre de façon synchrone un message de ce bloc.  Appelé par un bloc `ISource`.  Lorsque cette fonction se termine, le message est déjà propagé dans le bloc.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[propagator\_block::decline\_incoming\_messages, méthode](../Topic/propagator_block::decline_incoming_messages%20Method.md)|Indique au bloc que les nouveaux messages doivent être refusés.|  
|[propagator\_block::initialize\_source\_and\_target, méthode](../Topic/propagator_block::initialize_source_and_target%20Method.md)|Initialise l'objet de base.  Spécifiquement, l'objet `message_processor` doit être initialisé.|  
|[propagator\_block::link\_source, méthode](../Topic/propagator_block::link_source%20Method.md)|Lie un bloc source spécifié à cet objet `propagator_block`.|  
|[propagator\_block::process\_input\_messages, méthode](../Topic/propagator_block::process_input_messages%20Method.md)|Messages d'entrée du processus.  C'est uniquement utile pour les blocs de propagateur, qui dérivent de bloc source \(remplace [source\_block::process\_input\_messages](../Topic/source_block::process_input_messages%20Method.md).\)|  
|[propagator\_block::propagate\_message, méthode](../Topic/propagator_block::propagate_message%20Method.md)|En cas de substitution dans une classe dérivée, cette méthode passe de façon asynchrone un message d'un bloc `ISource` à cet objet `propagator_block`.  Il est appelé par la méthode `propagate`, en cas d'appel par un bloc source.|  
|[propagator\_block::register\_filter, méthode](../Topic/propagator_block::register_filter%20Method.md)|Inscrit une méthode de filtre qui sera appelée sur chaque message reçu.|  
|[propagator\_block::remove\_network\_links, méthode](../Topic/propagator_block::remove_network_links%20Method.md)|Supprime tous les liens de réseau source et cible de cet objet `propagator_block`.|  
|[propagator\_block::send\_message, méthode](../Topic/propagator_block::send_message%20Method.md)|En cas de substitution dans une classe dérivée, cette méthode passe de façon synchrone un message d'un bloc `ISource` à cet objet `propagator_block`.  Il est appelé par la méthode `send`, en cas d'appel par un bloc source.|  
|[propagator\_block::unlink\_source, méthode](../Topic/propagator_block::unlink_source%20Method.md)|Dissocie un bloc source spécifié de cet objet `propagator_block`.|  
|[propagator\_block::unlink\_sources, méthode](../Topic/propagator_block::unlink_sources%20Method.md)|Dissocie tous les blocs source de cet objet `propagator_block`. \(Substitue [ITarget::unlink\_sources](../Topic/ITarget::unlink_sources%20Method.md).\)|  
  
## Notes  
 Pour éviter l'héritage multiple, la classe `propagator_block` hérite de la classe `source_block` et de la classe abstraite `ITarget`.  La plupart des fonctionnalités de la classe `target_block` sont répliquées ici.  
  
## Hiérarchie d'héritage  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [source\_block](../../../parallel/concrt/reference/source-block-class.md)  
  
 `propagator_block`  
  
## Configuration requise  
 **En\-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [source\_block, classe](../../../parallel/concrt/reference/source-block-class.md)   
 [ITarget, classe](../../../parallel/concrt/reference/itarget-class.md)