---
title: "Classe timer | Microsoft Docs"
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
  - "agents/concurrency::timer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "timer (classe)"
ms.assetid: 4f4dea51-de9f-40f9-93f5-dd724c567b49
caps.latest.revision: 21
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe timer
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Un bloc de messagerie `timer` est un `source_block` à cible unique capable d'envoyer un message à sa cible après qu'une période spécifiée s'est écoulée ou à intervalles spécifiques.  
  
## Syntaxe  
  
```  
template<  
   class _Type  
>  
class timer : public Concurrency::details::_Timer, public source_block<single_link_registry<ITarget<_Type>>>;  
```  
  
#### Paramètres  
 `_Type`  
 Le type de charge utile des messages de sortie de ce bloc.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[timer::timer, constructeur](../Topic/timer::timer%20Constructor.md)|Surchargé.  Construit un bloc de messagerie `timer` qui déclenchera un message donné après un intervalle spécifié.|  
|[timer::~timer, destructeur](../Topic/timer::~timer%20Destructor.md)|Détruit un bloc de messagerie `timer`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[timer::pause, méthode](../Topic/timer::pause%20Method.md)|Arrête le bloc de messagerie `timer`.  S'il s'agit d'un bloc de messagerie `timer` répété, il peut être redémarré avec un appel `start()` suivant.  Pour les minuteries non répétitives, l'effet est identique à celui d'un appel `stop`.|  
|[timer::start, méthode](../Topic/timer::start%20Method.md)|Démarre le bloc de messagerie `timer`.  À l'issue du nombre spécifié de millisecondes après cet appel, la valeur spécifiée sera propagée en aval comme `message`.|  
|[timer::stop, méthode](../Topic/timer::stop%20Method.md)|Arrête le bloc de messagerie `timer`.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[timer::accept\_message, méthode](../Topic/timer::accept_message%20Method.md)|Accepte un message qui a été transmis par ce bloc de messagerie `timer`, en transférant la propriété à l'appelant.|  
|[timer::consume\_message, méthode](../Topic/timer::consume_message%20Method.md)|Consomme un message offert précédemment par le `timer` et réservé par la cible, en transférant la propriété à l'appelant.|  
|[timer::link\_target\_notification, méthode](../Topic/timer::link_target_notification%20Method.md)|Rappel qui notifie qu'une nouvelle cible a été liée à ce bloc de messagerie `timer`.|  
|[timer::propagate\_to\_any\_targets, méthode](../Topic/timer::propagate_to_any_targets%20Method.md)|Essaie d'offrir le message produit par le bloc `timer` à toutes les cibles liées.|  
|[timer::release\_message, méthode](../Topic/timer::release_message%20Method.md)|Libère une réservation de message précédente. \(Substitue [source\_block::release\_message](../Topic/source_block::release_message%20Method.md).\)|  
|[timer::reserve\_message, méthode](../Topic/timer::reserve_message%20Method.md)|Réserve un message précédemment offert par ce bloc de messagerie `timer`. \(Substitue [source\_block::reserve\_message](../Topic/source_block::reserve_message%20Method.md).\)|  
|[timer::resume\_propagation, méthode](../Topic/timer::resume_propagation%20Method.md)|Reprend la propagation après qu'une réservation a été libérée. \(Substitue [source\_block::resume\_propagation](../Topic/source_block::resume_propagation%20Method.md).\)|  
  
## Notes  
 Pour plus d'informations, consultez [Blocs de messages asynchrones](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Hiérarchie d'héritage  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [source\_block](../../../parallel/concrt/reference/source-block-class.md)  
  
 `timer`  
  
## Configuration requise  
 **En\-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)