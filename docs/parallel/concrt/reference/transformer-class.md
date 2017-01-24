---
title: "Classe transformer | Microsoft Docs"
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
  - "agents/concurrency::transformer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "transformer (classe)"
ms.assetid: eea71925-7043-4a92-bfd4-dbc0ece5d081
caps.latest.revision: 22
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe transformer
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Un bloc de messagerie `transformer` est un `propagator_block` ordonné, multi\-sources, à cible unique qui peut accepter des messages d'un type et stocker un nombre illimité de messages d'un type différent.  
  
## Syntaxe  
  
```  
template<  
   class _Input,  
   class _Output  
>  
class transformer : public propagator_block<single_link_registry<ITarget<_Output>>, multi_link_registry<ISource<_Input>>>;  
```  
  
#### Paramètres  
 `_Input`  
 Le type de charge utile des messages acceptés par la mémoire tampon.  
  
 `_Output`  
 Le type de charge utile des messages stockés et propagés à l'extérieur par la mémoire tampon.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[transformer::transformer, constructeur](../Topic/transformer::transformer%20Constructor.md)|Surchargé.  Construit un bloc de messagerie `transformer`.|  
|[transformer::~transformer, destructeur](../Topic/transformer::~transformer%20Destructor.md)|Détruit le bloc de messagerie `transformer`.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[transformer::accept\_message, méthode](../Topic/transformer::accept_message%20Method.md)|Accepte un message qui a été transmis par ce bloc de messagerie `transformer`, en transférant la propriété à l'appelant.|  
|[transformer::consume\_message, méthode](../Topic/transformer::consume_message%20Method.md)|Consomme un message offert précédemment par le `transformer` et réservé par la cible, en transférant la propriété à l'appelant.|  
|[transformer::link\_target\_notification, méthode](../Topic/transformer::link_target_notification%20Method.md)|Rappel qui notifie qu'une nouvelle cible a été liée à ce bloc de messagerie `transformer`.|  
|[transformer::propagate\_message, méthode](../Topic/transformer::propagate_message%20Method.md)|Passe un message de façon asynchrone d'un bloc `ISource` à ce bloc de messagerie `transformer`.  Il est appelé par la méthode `propagate`, en cas d'appel par un bloc source.|  
|[transformer::propagate\_to\_any\_targets, méthode](../Topic/transformer::propagate_to_any_targets%20Method.md)|Exécute la fonction transformer sur les messages d'entrée.|  
|[transformer::release\_message, méthode](../Topic/transformer::release_message%20Method.md)|Libère une réservation de message précédente. \(Substitue [source\_block::release\_message](../Topic/source_block::release_message%20Method.md).\)|  
|[transformer::reserve\_message, méthode](../Topic/transformer::reserve_message%20Method.md)|Réserve un message précédemment offert par ce bloc de messagerie `transformer`. \(Substitue [source\_block::reserve\_message](../Topic/source_block::reserve_message%20Method.md).\)|  
|[transformer::resume\_propagation, méthode](../Topic/transformer::resume_propagation%20Method.md)|Reprend la propagation après qu'une réservation a été libérée. \(Substitue [source\_block::resume\_propagation](../Topic/source_block::resume_propagation%20Method.md).\)|  
|[transformer::send\_message, méthode](../Topic/transformer::send_message%20Method.md)|Passe de façon synchrone un message du bloc `ISource` au bloc de messagerie `transformer`.  Il est appelé par la méthode `send`, en cas d'appel par un bloc source.|  
|[transformer::supports\_anonymous\_source, méthode](../Topic/transformer::supports_anonymous_source%20Method.md)|Remplace la méthode `supports_anonymous_source` pour indiquer que le bloc peut recevoir des messages proposés par une source qui n'est pas liée. \(Remplace [ITarget::supports\_anonymous\_source](../Topic/ITarget::supports_anonymous_source%20Method.md)\).|  
  
## Notes  
 Pour plus d'informations, consultez [Blocs de messages asynchrones](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Hiérarchie d'héritage  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [source\_block](../../../parallel/concrt/reference/source-block-class.md)  
  
 [propagator\_block](../../../parallel/concrt/reference/propagator-block-class.md)  
  
 `transformer`  
  
## Configuration requise  
 **En\-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [call, classe](../../../parallel/concrt/reference/call-class.md)