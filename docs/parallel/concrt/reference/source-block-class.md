---
title: "source_block, classe | Microsoft Docs"
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
  - "agents/concurrency::source_block"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "source_block (classe)"
ms.assetid: fbdd4146-e8d0-42e8-b714-fe633f69ffbf
caps.latest.revision: 20
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# source_block, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe `source_block` est une classe de base abstraite pour les blocs source uniquement.  La classe fournit une fonctionnalité basique de gestion des liaisons et vérifie les erreurs courantes.  
  
## Syntaxe  
  
```  
template<  
   class _TargetLinkRegistry,  
   class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>  
>  
class source_block : public ISource<typename _TargetLinkRegistry::type::type>;  
```  
  
#### Paramètres  
 `_TargetLinkRegistry`  
 Registre de liens à utiliser pour contenir les liens cibles.  
  
 `_MessageProcessorType`  
 Type de processeur pour le traitement du message.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`target_iterator`|Itérateur pour parcourir les cibles connectées.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[source\_block::source\_block, constructeur](../Topic/source_block::source_block%20Constructor.md)|Construit un objet `source_block`.|  
|[source\_block::~source\_block, destructeur](../Topic/source_block::~source_block%20Destructor.md)|Détruit l'objet `source_block`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[source\_block::accept, méthode](../Topic/source_block::accept%20Method.md)|Accepte un message qui a été transmis par cet objet `source_block`, en transférant la propriété à l'appelant.|  
|[source\_block::acquire\_ref, méthode](../Topic/source_block::acquire_ref%20Method.md)|Acquiert un décompte de références sur cet objet `source_block`, pour empêcher la suppression.|  
|[source\_block::consume, méthode](../Topic/source_block::consume%20Method.md)|Consomme un message offert précédemment par cet objet `source_block` et réservé avec succès par la cible, en transférant la propriété à l'appelant.|  
|[source\_block::link\_target, méthode](../Topic/source_block::link_target%20Method.md)|Lie un bloc cible à cet objet `source_block`.|  
|[source\_block::release, méthode](../Topic/source_block::release%20Method.md)|Libère une réservation de message réussie précédente.|  
|[source\_block::release\_ref, méthode](../Topic/source_block::release_ref%20Method.md)|Libère un nombre de références sur cet objet `source_block`.|  
|[source\_block::reserve, méthode](../Topic/source_block::reserve%20Method.md)|Réserve un message précédemment offert par cet objet `source_block`.|  
|[source\_block::unlink\_target, méthode](../Topic/source_block::unlink_target%20Method.md)|Dissocie un bloc cible de cet objet `source_block`.|  
|[source\_block::unlink\_targets, méthode](../Topic/source_block::unlink_targets%20Method.md)|Dissocie tous les blocs cibles de cet objet `source_block`. \(Substitue [ISource::unlink\_targets](../Topic/ISource::unlink_targets%20Method.md).\)|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[source\_block::accept\_message, méthode](../Topic/source_block::accept_message%20Method.md)|En cas de substitution dans une classe dérivée, accepte un message offert par la source.  Les blocs de messages doivent substituer cette méthode pour valider le `_MsgId` et retourner un message.|  
|[source\_block::async\_send, méthode](../Topic/source_block::async_send%20Method.md)|Place les messages en file d'attente et démarre une tâche de propagation de façon asynchrone, si cela n'a pas déjà été fait|  
|[source\_block::consume\_message, méthode](../Topic/source_block::consume_message%20Method.md)|En cas de substitution dans une classe dérivée, consomme un message qui était précédemment réservé.|  
|[source\_block::enable\_batched\_processing, méthode](../Topic/source_block::enable_batched_processing%20Method.md)|Permet de traiter en lots pour ce bloc.|  
|[source\_block::initialize\_source, méthode](../Topic/source_block::initialize_source%20Method.md)|Initialise le `message_propagator` dans ce `source_block`.|  
|[source\_block::link\_target\_notification, méthode](../Topic/source_block::link_target_notification%20Method.md)|Rappel qui notifie qu'une nouvelle cible a été liée à cet objet `source_block`.|  
|[source\_block::process\_input\_messages, méthode](../Topic/source_block::process_input_messages%20Method.md)|Messages d'entrée du processus.  Ce n'est utile que pour les blocs de propagateur, qui dérive de bloc source|  
|[source\_block::propagate\_output\_messages, méthode](../Topic/source_block::propagate_output_messages%20Method.md)|Messages de propagation aux cibles.|  
|[source\_block::propagate\_to\_any\_targets, méthode](../Topic/source_block::propagate_to_any_targets%20Method.md)|En cas de substitution dans une classe dérivée, propage le message donné une à cible liée particulière ou à toutes.  C'est la routine de propagation principale pour les blocs de messages.|  
|[source\_block::release\_message, méthode](../Topic/source_block::release_message%20Method.md)|En cas de substitution dans une classe dérivée, émet une réservation de message précédente.|  
|[source\_block::remove\_targets, méthode](../Topic/source_block::remove_targets%20Method.md)|Supprime tous les liens cibles de ce bloc source.  Doit être appelé à partir du destructeur.|  
|[source\_block::reserve\_message, méthode](../Topic/source_block::reserve_message%20Method.md)|En cas de substitution dans une classe dérivée, réserve un message précédemment offert par cet objet `source_block`.|  
|[source\_block::resume\_propagation, méthode](../Topic/source_block::resume_propagation%20Method.md)|En cas de substitution dans une classe dérivée, continue la propagation après qu'une réservation a été émise.|  
|[source\_block::sync\_send, méthode](../Topic/source_block::sync_send%20Method.md)|Met en file d'attente de façon synchrone des messages et démarre une tâche de propagation, si cela n'a pas déjà été fait.|  
|[source\_block::unlink\_target\_notification, méthode](../Topic/source_block::unlink_target_notification%20Method.md)|Rappel qui notifie qu'une cible a été dissociée de cet objet `source_block`.|  
|[source\_block::wait\_for\_outstanding\_async\_sends, méthode](../Topic/source_block::wait_for_outstanding_async_sends%20Method.md)|Attend que toutes les propagations asynchrones soient terminées.  Cette attente de rotation spécifique au propagateur est utilisée dans les destructeurs de blocs de messages pour veiller à ce que toutes les propagations asynchrones aient le temps de se terminer avant de détruire le bloc.|  
  
## Notes  
 Les blocs de messages doivent dériver de ce bloc pour tirer parti de la gestion et synchronisation de liens et fournies par cette classe.  
  
## Hiérarchie d'héritage  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 `source_block`  
  
## Configuration requise  
 **En\-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [ISource, classe](../../../parallel/concrt/reference/isource-class.md)