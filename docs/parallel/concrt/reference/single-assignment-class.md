---
title: "Classe single_assignment | Microsoft Docs"
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
  - "agents/concurrency::single_assignment"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "single_assignment (classe)"
ms.assetid: ccc34728-8de9-4e07-b83d-a36a58d9d2b9
caps.latest.revision: 21
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe single_assignment
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Un bloc de messagerie `single_assignment` est un `propagator_block` de cible multiple, de source multiple et classé capable de stocker un `message` unique, écrit une seule fois.  
  
## Syntaxe  
  
```  
template<  
   class _Type  
>  
class single_assignment : public propagator_block<multi_link_registry<ITarget<_Type>>, multi_link_registry<ISource<_Type>>>;  
```  
  
#### Paramètres  
 `_Type`  
 Le type de charge utile du message stocké et propagé par la mémoire tampon.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[single\_assignment::single\_assignment, constructeur](../Topic/single_assignment::single_assignment%20Constructor.md)|Surchargé.  Construit un bloc de messagerie `single_assignment`.|  
|[single\_assignment::~single\_assignment, destructeur](../Topic/single_assignment::~single_assignment%20Destructor.md)|Détruit le bloc de messagerie `single_assignment`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[single\_assignment::has\_value, méthode](../Topic/single_assignment::has_value%20Method.md)|Vérifie si ce bloc de messagerie `single_assignment` a déjà été initialisé avec une valeur.|  
|[single\_assignment::value, méthode](../Topic/single_assignment::value%20Method.md)|Obtient une référence pour la charge utile actuelle du message qui est stocké dans le bloc de messagerie `single_assignment`.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[single\_assignment::accept\_message, méthode](../Topic/single_assignment::accept_message%20Method.md)|Accepte un message qui a été transmis par ce bloc de messagerie `single_assignment`, en retournant une copie du message à l'appelant.|  
|[single\_assignment::consume\_message, méthode](../Topic/single_assignment::consume_message%20Method.md)|Consomme un message offert précédemment par le `single_assignment` et réservé par la cible, en retournant une copie du message à l'appelant.|  
|[single\_assignment::link\_target\_notification, méthode](../Topic/single_assignment::link_target_notification%20Method.md)|Rappel qui notifie qu'une nouvelle cible a été liée à ce bloc de messagerie `single_assignment`.|  
|[single\_assignment::propagate\_message, méthode](../Topic/single_assignment::propagate_message%20Method.md)|Passe un message de façon asynchrone d'un bloc `ISource` à ce bloc de messagerie `single_assignment`.  Il est appelé par la méthode `propagate`, en cas d'appel par un bloc source.|  
|[single\_assignment::propagate\_to\_any\_targets, méthode](../Topic/single_assignment::propagate_to_any_targets%20Method.md)|Place le `message``_PMessage` dans ce bloc de messagerie `single_assignment` et l'offres à toutes les cibles liées.|  
|[single\_assignment::release\_message, méthode](../Topic/single_assignment::release_message%20Method.md)|Libère une réservation de message précédente. \(Substitue [source\_block::release\_message](../Topic/source_block::release_message%20Method.md).\)|  
|[single\_assignment::reserve\_message, méthode](../Topic/single_assignment::reserve_message%20Method.md)|Réserve un message précédemment offert par ce bloc de messagerie `single_assignment`. \(Substitue [source\_block::reserve\_message](../Topic/source_block::reserve_message%20Method.md).\)|  
|[single\_assignment::resume\_propagation, méthode](../Topic/single_assignment::resume_propagation%20Method.md)|Reprend la propagation après qu'une réservation a été libérée. \(Substitue [source\_block::resume\_propagation](../Topic/source_block::resume_propagation%20Method.md).\)|  
|[single\_assignment::send\_message, méthode](../Topic/single_assignment::send_message%20Method.md)|Passe de façon synchrone un message du bloc `ISource` au bloc de messagerie `single_assignment`.  Il est appelé par la méthode `send`, en cas d'appel par un bloc source.|  
  
## Notes  
 Un bloc de messagerie `single_assignment` propage des copies de son message vers chaque cible.  
  
 Pour plus d'informations, consultez [Blocs de messages asynchrones](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Hiérarchie d'héritage  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [source\_block](../../../parallel/concrt/reference/source-block-class.md)  
  
 [propagator\_block](../../../parallel/concrt/reference/propagator-block-class.md)  
  
 `single_assignment`  
  
## Configuration requise  
 **En\-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Classe overwrite\_buffer](../../../parallel/concrt/reference/overwrite-buffer-class.md)   
 [Classe unbounded\_buffer](../Topic/unbounded_buffer%20Class.md)