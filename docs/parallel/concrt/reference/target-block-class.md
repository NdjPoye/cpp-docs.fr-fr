---
title: target_block, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::target_block
dev_langs:
- C++
helpviewer_keywords:
- target_block class
ms.assetid: 3ce181b4-b94a-4894-bf7b-64fc09821f9f
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 0137e95d0d5015fd2e8d18d85388c16ab25a2e9c
ms.lasthandoff: 02/24/2017

---
# <a name="targetblock-class"></a>target_block, classe
La classe `target_block` est une classe de base abstraite qui fournit une fonctionnalité de gestion des liens de base et une vérification des erreurs pour les blocs cibles uniquement.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _SourceLinkRegistry::type::source_type>>
class target_block : public ITarget<typename _SourceLinkRegistry::type::source_type>;
```  
  
#### <a name="parameters"></a>Paramètres  
 `_SourceLinkRegistry`  
 Registre de liens à utiliser pour contenir les liens source.  
  
 `_MessageProcessorType`  
 Le type de processeur pour le traitement du message.  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`source_iterator`|Le type de l’itérateur pour la `source_link_manager` pour ce `target_block` objet.|  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[target_block, constructeur](#ctor)|Construit un objet `target_block`.|  
|[~ target_block, destructeur](#dtor)|Détruit le `target_block` objet.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Propagate (méthode)](#propagate)|Passe de façon asynchrone un message à partir d’un bloc source à ce bloc cible.|  
|[Send (méthode)](#send)|Passe de façon synchrone un message à partir d’un bloc source à ce bloc cible.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[async_send (méthode)](#async_send)|Envoie de façon asynchrone un message pour traitement.|  
|[decline_incoming_messages (méthode)](#decline_incoming_messages)|Indique au bloc que les nouveaux messages doivent être refusées.|  
|[enable_batched_processing (méthode)](#enable_batched_processing)|Active les traités par lot de traitement pour ce bloc.|  
|[initialize_target (méthode)](#initialize_target)|Initialise l’objet de base. Plus précisément, le `message_processor` objet doit être initialisé.|  
|[link_source (méthode)](#link_source)|Lie un bloc source spécifié à ce `target_block` objet.|  
|[process_input_messages (méthode)](#process_input_messages)|Traite les messages sont reçus en tant qu’entrées.|  
|[process_message (méthode)](#process_message)|En cas de substitution dans une classe dérivée, traite un message accepté par ce `target_block` objet.|  
|[propagate_message (méthode)](#propagate_message)|En cas de substitution dans une classe dérivée, cette méthode passe de façon asynchrone un message à partir d’un `ISource` à ce bloc `target_block` objet. Il est appelé par le `propagate` la méthode appelée par un bloc source.|  
|[register_filter (méthode)](#register_filter)|Enregistre une méthode de filtre qui sera appelée sur chaque message reçu.|  
|[remove_sources (méthode)](#remove_sources)|Dissocie toutes les sources après avoir attendu pour les opérations d’envoi asynchrones en attente se terminent.|  
|[send_message (méthode)](#send_message)|En cas de substitution dans une classe dérivée, cette méthode passe de façon synchrone un message à partir d’un `ISource` à ce bloc `target_block` objet. Il est appelé par le `send` la méthode appelée par un bloc source.|  
|[sync_send (méthode)](#sync_send)|Envoyer de façon synchrone un message pour traitement.|  
|[unlink_source (méthode)](#unlink_source)|Dissocie un bloc source spécifié à partir de ce `target_block` objet.|  
|[unlink_sources (méthode)](#unlink_sources)|Dissocie tous les blocs de code source à partir de ce `target_block` objet. (Substitue [ITarget::unlink_sources](itarget-class.md#unlink_sources).)|  
|[wait_for_async_sends (méthode)](#wait_for_async_sends)|Attend que toutes les propagations asynchrones soient terminées.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [ITarget](itarget-class.md)  
  
 `target_block`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-nameasyncsenda-asyncsend"></a><a name="async_send"></a>async_send 

 Envoie de façon asynchrone un message pour traitement.  
  
```
void async_send(_Inout_opt_ message<_Source_type>* _PMessage);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PMessage`  
 Pointeur vers le message envoyé.  
  
##  <a name="a-namedeclineincomingmessagesa-declineincomingmessages"></a><a name="decline_incoming_messages"></a>decline_incoming_messages 

 Indique au bloc que les nouveaux messages doivent être refusées.  
  
```
void decline_incoming_messages();
```  
  
### <a name="remarks"></a>Remarques  
 Cette méthode est appelée par le destructeur pour vous assurer que les nouveaux messages sont refusés pendant que la destruction est en cours.  
  
##  <a name="a-nameenablebatchedprocessinga-enablebatchedprocessing"></a><a name="enable_batched_processing"></a>enable_batched_processing 

 Active les traités par lot de traitement pour ce bloc.  
  
```
void enable_batched_processing();
```  
  
##  <a name="a-nameinitializetargeta-initializetarget"></a><a name="initialize_target"></a>initialize_target 

 Initialise l’objet de base. Plus précisément, le `message_processor` objet doit être initialisé.  
  
```
void initialize_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PScheduler`  
 Planificateur à utiliser pour la planification des tâches.  
  
 `_PScheduleGroup`  
 Le groupe de planification à utiliser pour la planification des tâches.  
  
##  <a name="a-namelinksourcea-linksource"></a><a name="link_source"></a>link_source 

 Lie un bloc source spécifié à ce `target_block` objet.  
  
```
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PSource`  
 Un pointeur vers le `ISource` bloc qui doit être liée.  
  
### <a name="remarks"></a>Notes  
 Cette fonction ne doit pas être appelée directement sur un `target_block` objet. Les blocs doivent être connectés à l’aide de la `link_target` méthode sur `ISource` blocs, qui appelleront le `link_source` méthode sur la cible correspondante.  
  
##  <a name="a-nameprocessinputmessagesa-processinputmessages"></a><a name="process_input_messages"></a>process_input_messages 

 Traite les messages sont reçus en tant qu’entrées.  
  
```
virtual void process_input_messages(_Inout_ message<_Source_type>* _PMessage);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PMessage`  
  
##  <a name="a-nameprocessmessagea-processmessage"></a><a name="process_message"></a>process_message 

 En cas de substitution dans une classe dérivée, traite un message accepté par ce `target_block` objet.  
  
```
virtual void process_message(message<_Source_type> *);
```  
  
##  <a name="a-namepropagatea-propagate"></a><a name="propagate"></a>propager 

 Passe de façon asynchrone un message à partir d’un bloc source à ce bloc cible.  
  
```
virtual message_status propagate(
    _Inout_opt_ message<_Source_type>* _PMessage,
    _Inout_opt_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PMessage`  
 Pointeur vers l'objet `message`.  
  
 `_PSource`  
 Pointeur vers le bloc source qui transmet le message.  
  
### <a name="return-value"></a>Valeur de retour  
 A [message_status](concurrency-namespace-enums.md) indication de ce que la cible a décidé de faire avec ce message.  
  
### <a name="remarks"></a>Notes  
 La méthode lève un [invalid_argument](../../../standard-library/invalid-argument-class.md) exception si le `_PMessage` ou `_PSource` paramètre est `NULL`.  
  
##  <a name="a-namepropagatemessagea-propagatemessage"></a><a name="propagate_message"></a>propagate_message 

 En cas de substitution dans une classe dérivée, cette méthode passe de façon asynchrone un message à partir d’un `ISource` à ce bloc `target_block` objet. Il est appelé par le `propagate` la méthode appelée par un bloc source.  
  
```
virtual message_status propagate_message(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_PMessage`  
 Pointeur vers l'objet `message`.  
  
 `_PSource`  
 Pointeur vers le bloc source qui transmet le message.  
  
### <a name="return-value"></a>Valeur de retour  
 A [message_status](concurrency-namespace-enums.md) indication de ce que la cible a décidé de faire avec ce message.  
  
##  <a name="a-nameregisterfiltera-registerfilter"></a><a name="register_filter"></a>register_filter 

 Enregistre une méthode de filtre qui sera appelée sur chaque message reçu.  
  
```
void register_filter(filter_method const& _Filter);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Filter`  
 La méthode de filtrage.  
  
##  <a name="a-nameremovesourcesa-removesources"></a><a name="remove_sources"></a>remove_sources 

 Dissocie toutes les sources après avoir attendu pour les opérations d’envoi asynchrones en attente se terminent.  
  
```
void remove_sources();
```  
  
### <a name="remarks"></a>Notes  
 Tous les blocs cibles doivent appeler cette routine pour supprimer les sources dans leur destructeur.  
  
##  <a name="a-namesenda-send"></a><a name="send"></a>Envoyer 

 Passe de façon synchrone un message à partir d’un bloc source à ce bloc cible.  
  
```
virtual message_status send(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PMessage`  
 Pointeur vers l'objet `message`.  
  
 `_PSource`  
 Pointeur vers le bloc source qui transmet le message.  
  
### <a name="return-value"></a>Valeur de retour  
 A [message_status](concurrency-namespace-enums.md) indication de ce que la cible a décidé de faire avec ce message.  
  
### <a name="remarks"></a>Notes  
 La méthode lève un [invalid_argument](../../../standard-library/invalid-argument-class.md) exception si le `_PMessage` ou `_PSource` paramètre est `NULL`.  
  
 À l’aide de la `send` méthode en dehors de l’émission de messages et pour propager des messages dans un réseau est dangereux et peut provoquer un interblocage.  
  
 Lorsque `send` est retournée, le message a déjà été accepté et transféré dans le bloc cible, ou il a été refusé par la cible.  
  
##  <a name="a-namesendmessagea-sendmessage"></a><a name="send_message"></a>send_message 

 En cas de substitution dans une classe dérivée, cette méthode passe de façon synchrone un message à partir d’un `ISource` à ce bloc `target_block` objet. Il est appelé par le `send` la méthode appelée par un bloc source.  
  
```
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```  
  
### <a name="return-value"></a>Valeur de retour  
 A [message_status](concurrency-namespace-enums.md) indication de ce que la cible a décidé de faire avec ce message.  
  
### <a name="remarks"></a>Notes  
 Par défaut, ce bloc retourne `declined` sauf substitution par une classe dérivée.  
  
##  <a name="a-namesyncsenda-syncsend"></a><a name="sync_send"></a>sync_send 

 Envoyer de façon synchrone un message pour traitement.  
  
```
void sync_send(_Inout_opt_ message<_Source_type>* _PMessage);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PMessage`  
 Pointeur vers le message envoyé.  
  
##  <a name="a-namectora-targetblock"></a><a name="ctor"></a>target_block 

 Construit un objet `target_block`.  
  
```
target_block();
```  
  
##  <a name="a-namedtora-targetblock"></a><a name="dtor"></a>~ target_block 

 Détruit le `target_block` objet.  
  
```
virtual ~target_block();
```  
  
##  <a name="a-nameunlinksourcea-unlinksource"></a><a name="unlink_source"></a>unlink_source 

 Dissocie un bloc source spécifié à partir de ce `target_block` objet.  
  
```
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PSource`  
 Un pointeur vers le `ISource` bloc qui doit être dissocié.  
  
##  <a name="a-nameunlinksourcesa-unlinksources"></a><a name="unlink_sources"></a>unlink_sources 

 Dissocie tous les blocs de code source à partir de ce `target_block` objet.  
  
```
virtual void unlink_sources();
```  
  
##  <a name="a-namewaitforasyncsendsa-waitforasyncsends"></a><a name="wait_for_async_sends"></a>wait_for_async_sends 

 Attend que toutes les propagations asynchrones soient terminées.  
  
```
void wait_for_async_sends();
```  
  
### <a name="remarks"></a>Remarques  
 Cette méthode est utilisée par les destructeurs de bloc de message pour vous assurer que toutes les opérations asynchrones ont eu le temps de terminer avant de détruire le bloc.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [ITarget, classe](itarget-class.md)

