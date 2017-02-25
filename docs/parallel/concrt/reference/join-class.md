---
title: "join, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::join"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "join (classe)"
ms.assetid: d2217119-70a1-40b6-809f-c1c13a571c3f
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# join, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Un bloc de messagerie `join` est un `propagator_block` de cible unique, de source multiple et classé qui combine ensemble des messages de type `_Type` à partir de chacune de ses sources.  
  
## Syntaxe  
  
```  
template<  
   class _Type,  
   join_type _Jtype = non_greedy  
>  
class join : public propagator_block<single_link_registry<ITarget<std::vector<_Type>>>, multi_link_registry<ISource<_Type>>>;  
```  
  
#### Paramètres  
 `_Type`  
 Le type de charge utile des messages joints et propagés par le bloc.  
  
 `_Jtype`  
 Le genre de bloc `join` qui est `greedy` ou `non_greedy`  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[join::join, constructeur](../Topic/join::join%20Constructor.md)|Surchargé.  Construit un bloc de messagerie `join`.|  
|[join::~join, destructeur](../Topic/join::~join%20Destructor.md)|Détruit le bloc `join`.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[join::accept\_message, méthode](../Topic/join::accept_message%20Method.md)|Accepte un message qui a été transmis par ce bloc de messagerie `join`, en transférant la propriété à l'appelant.|  
|[join::consume\_message, méthode](../Topic/join::consume_message%20Method.md)|Consomme un message offert précédemment par le bloc de messagerie `join` et réservé par la cible, en transférant la propriété à l'appelant.|  
|[join::link\_target\_notification, méthode](../Topic/join::link_target_notification%20Method.md)|Rappel qui notifie qu'une nouvelle cible a été liée à ce bloc de messagerie `join`.|  
|[join::propagate\_message, méthode](../Topic/join::propagate_message%20Method.md)|Passe un message de façon asynchrone d'un bloc `ISource` à ce bloc de messagerie `join`.  Il est appelé par la méthode `propagate`, en cas d'appel par un bloc source.|  
|[join::propagate\_to\_any\_targets, méthode](../Topic/join::propagate_to_any_targets%20Method.md)|Construit un message de sortie contenant un message d'entrée de chaque source lorsqu'ils ont tous propagé un message.  Envoie ce message de sortie à chacune de ses cibles.|  
|[join::release\_message, méthode](../Topic/join::release_message%20Method.md)|Libère une réservation de message précédente. \(Substitue [source\_block::release\_message](../Topic/source_block::release_message%20Method.md).\)|  
|[join::reserve\_message, méthode](../Topic/join::reserve_message%20Method.md)|Réserve un message précédemment offert par ce bloc de messagerie `join`. \(Substitue [source\_block::reserve\_message](../Topic/source_block::reserve_message%20Method.md).\)|  
|[join::resume\_propagation, méthode](../Topic/join::resume_propagation%20Method.md)|Reprend la propagation après qu'une réservation a été libérée. \(Substitue [source\_block::resume\_propagation](../Topic/source_block::resume_propagation%20Method.md).\)|  
  
## Notes  
 Pour plus d'informations, consultez [Blocs de messages asynchrones](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Hiérarchie d'héritage  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [source\_block](../../../parallel/concrt/reference/source-block-class.md)  
  
 [propagator\_block](../../../parallel/concrt/reference/propagator-block-class.md)  
  
 `join`  
  
## Configuration requise  
 **En\-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Classe choice](../../../parallel/concrt/reference/choice-class.md)   
 [multitype\_join, classe](../../../parallel/concrt/reference/multitype-join-class.md)   
 [join\_type, énumération](../Topic/join_type%20Enumeration.md)