---
title: "Classe overwrite_buffer | Microsoft Docs"
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
  - "agents/concurrency::overwrite_buffer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "overwrite_buffer (classe)"
ms.assetid: 5cc428fe-3697-419c-9fb2-78f6181c9293
caps.latest.revision: 22
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe overwrite_buffer
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Un bloc de messagerie `overwrite_buffer` est un `propagator_block` ordonné, multi\-sources et multi\-cibles capable de stocker un seul message la fois.  Les nouveaux messages remplacent ceux précédemment maintenus.  
  
## Syntaxe  
  
```  
template<  
   class _Type  
>  
class overwrite_buffer : public propagator_block<multi_link_registry<ITarget<_Type>>, multi_link_registry<ISource<_Type>>>;  
```  
  
#### Paramètres  
 `_Type`  
 Le type de charge utile des messages stockés et propagés par la mémoire tampon.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[overwrite\_buffer::overwrite\_buffer, constructeur](../Topic/overwrite_buffer::overwrite_buffer%20Constructor.md)|Surchargé.  Construit un bloc de messagerie `overwrite_buffer`.|  
|[overwrite\_buffer::~overwrite\_buffer, destructeur](../Topic/overwrite_buffer::~overwrite_buffer%20Destructor.md)|Détruit le bloc de messagerie `overwrite_buffer`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[overwrite\_buffer::has\_value, méthode](../Topic/overwrite_buffer::has_value%20Method.md)|Vérifie si ce bloc de messagerie `overwrite_buffer` a déjà une valeur.|  
|[overwrite\_buffer::value, méthode](../Topic/overwrite_buffer::value%20Method.md)|Obtient une référence pour la charge utile actuelle du message qui est stocké dans le bloc de messagerie `overwrite_buffer`.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[overwrite\_buffer::accept\_message, méthode](../Topic/overwrite_buffer::accept_message%20Method.md)|Accepte un message qui a été transmis par ce bloc de messagerie `overwrite_buffer`, en retournant une copie du message à l'appelant.|  
|[overwrite\_buffer::consume\_message, méthode](../Topic/overwrite_buffer::consume_message%20Method.md)|Consomme un message offert précédemment par le bloc de messagerie `overwrite_buffer` et réservé par la cible, en retournant une copie du message à l'appelant.|  
|[overwrite\_buffer::link\_target\_notification, méthode](../Topic/overwrite_buffer::link_target_notification%20Method.md)|Rappel qui notifie qu'une nouvelle cible a été liée à ce bloc de messagerie `overwrite_buffer`.|  
|[overwrite\_buffer::propagate\_message, méthode](../Topic/overwrite_buffer::propagate_message%20Method.md)|Passe un message de façon asynchrone d'un bloc `ISource` à ce bloc de messagerie `overwrite_buffer`.  Il est appelé par la méthode `propagate`, en cas d'appel par un bloc source.|  
|[overwrite\_buffer::propagate\_to\_any\_targets, méthode](../Topic/overwrite_buffer::propagate_to_any_targets%20Method.md)|Place le `message``_PMessage` dans ce bloc de messagerie `overwrite_buffer` et l'offres à toutes les cibles liées.|  
|[overwrite\_buffer::release\_message, méthode](../Topic/overwrite_buffer::release_message%20Method.md)|Libère une réservation de message précédente. \(Substitue [source\_block::release\_message](../Topic/source_block::release_message%20Method.md).\)|  
|[overwrite\_buffer::reserve\_message, méthode](../Topic/overwrite_buffer::reserve_message%20Method.md)|Réserve un message précédemment offert par ce bloc de messagerie `overwrite_buffer`. \(Substitue [source\_block::reserve\_message](../Topic/source_block::reserve_message%20Method.md).\)|  
|[overwrite\_buffer::resume\_propagation, méthode](../Topic/overwrite_buffer::resume_propagation%20Method.md)|Reprend la propagation après qu'une réservation a été libérée. \(Substitue [source\_block::resume\_propagation](../Topic/source_block::resume_propagation%20Method.md).\)|  
|[overwrite\_buffer::send\_message, méthode](../Topic/overwrite_buffer::send_message%20Method.md)|Passe de façon synchrone un message du bloc `ISource` au bloc de messagerie `overwrite_buffer`.  Il est appelé par la méthode `send`, en cas d'appel par un bloc source.|  
|[overwrite\_buffer::supports\_anonymous\_source, méthode](../Topic/overwrite_buffer::supports_anonymous_source%20Method.md)|Remplace la méthode `supports_anonymous_source` pour indiquer que le bloc peut recevoir des messages proposés par une source qui n'est pas liée. \(Remplace [ITarget::supports\_anonymous\_source](../Topic/ITarget::supports_anonymous_source%20Method.md)\).|  
  
## Notes  
 Un bloc de messagerie `overwrite_buffer` propage des copies de son message stocké vers chacune de ses cibles.  
  
 Pour plus d'informations, consultez [Blocs de messages asynchrones](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Hiérarchie d'héritage  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [source\_block](../../../parallel/concrt/reference/source-block-class.md)  
  
 [propagator\_block](../../../parallel/concrt/reference/propagator-block-class.md)  
  
 `overwrite_buffer`  
  
## Configuration requise  
 **En\-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Classe unbounded\_buffer](../Topic/unbounded_buffer%20Class.md)   
 [Classe single\_assignment](../../../parallel/concrt/reference/single-assignment-class.md)