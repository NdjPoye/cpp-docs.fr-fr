---
title: Classe single_assignment | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::single_assignment
dev_langs:
- C++
helpviewer_keywords:
- single_assignment class
ms.assetid: ccc34728-8de9-4e07-b83d-a36a58d9d2b9
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
ms.openlocfilehash: a2a500353b06219713c5d9f3e68f82b247c1604f
ms.lasthandoff: 02/24/2017

---
# <a name="singleassignment-class"></a>Classe single_assignment
Un bloc de messagerie `single_assignment` est un `propagator_block` à cibles multiples, à sources multiples et ordonné, capable de stocker un `message` unique écrit une seule fois.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class T>
class single_assignment : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Type de charge utile du message stocké et propagé par la mémoire tampon.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[single_assignment, constructeur](#ctor)|Surchargé. Construit un `single_assignment` bloc de messagerie.|  
|[~ single_assignment, destructeur](#dtor)|Détruit le `single_assignment` bloc de messagerie.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[has_value (méthode)](#has_value)|Vérifie si cette `single_assignment` bloc de messagerie a encore été initialisé avec une valeur.|  
|[valeur (méthode)](#value)|Obtient une référence à la charge utile actuelle du message qui est stocké dans le `single_assignment` bloc de messagerie.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[accept_message (méthode)](#accept_message)|Accepte un message qui a été transmis par ce `single_assignment` messagerie bloc, en retournant une copie du message à l’appelant.|  
|[consume_message (méthode)](#consume_message)|Consomme un message précédemment offert par le `single_assignment` et réservé par la cible, en retournant une copie du message à l’appelant.|  
|[link_target_notification (méthode)](#link_target_notification)|Rappel qui notifie qu’une nouvelle cible a été liée à ce `single_assignment` bloc de messagerie.|  
|[propagate_message (méthode)](#propagate_message)|Passe de façon asynchrone un message à partir d’un `ISource` à ce bloc `single_assignment` bloc de messagerie. Il est appelé par le `propagate` la méthode appelée par un bloc source.|  
|[propagate_to_any_targets (méthode)](#propagate_to_any_targets)|Place le `message``_PMessage` dans ce `single_assignment` bloc de messagerie et offre à toutes les cibles liées.|  
|[release_message (méthode)](#release_message)|Libère une réservation de message précédente. (Substitue [source_block::release_message](source-block-class.md#release_message).)|  
|[reserve_message (méthode)](#reserve_message)|Réserve un message précédemment offert par ce `single_assignment` bloc de messagerie. (Substitue [source_block::reserve_message](source-block-class.md#reserve_message).)|  
|[resume_propagation (méthode)](#resume_propagation)|Reprend la propagation après qu’une réservation a été libérée. (Substitue [source_block::resume_propagation](source-block-class.md#resume_propagation).)|  
|[send_message (méthode)](#send_message)|Passe de façon synchrone un message à partir d’un `ISource` à ce bloc `single_assignment` bloc de messagerie. Il est appelé par le `send` la méthode appelée par un bloc source.|  
  
## <a name="remarks"></a>Remarques  
 Un `single_assignment` bloc de messagerie propage des copies de son message vers chaque cible.  
  
 Pour plus d’informations, consultez [blocs de messages asynchrones](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [ISource](isource-class.md)  
  
 [ITarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 [propagator_block](propagator-block-class.md)  
  
 `single_assignment`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-nameacceptmessagea-acceptmessage"></a><a name="accept_message"></a>accept_message 

 Accepte un message qui a été transmis par ce `single_assignment` messagerie bloc, en retournant une copie du message à l’appelant.  
  
```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de l’offerte `message` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le `message` que l’appelant est désormais propriétaire de l’objet.  
  
### <a name="remarks"></a>Remarques  
 Le `single_assignment` messagerie bloc retourne des copies du message à ses cibles, au lieu de transférer la propriété du message actuellement détenu.  
  
##  <a name="a-nameconsumemessagea-consumemessage"></a><a name="consume_message"></a>consume_message 

 Consomme un message précédemment offert par le `single_assignment` et réservé par la cible, en retournant une copie du message à l’appelant.  
  
```
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de la `message` de l’objet en cours de consommation.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le `message` que l’appelant est désormais propriétaire de l’objet.  
  
### <a name="remarks"></a>Remarques  
 Semblable à `accept`, mais est toujours précédé par un appel à `reserve`.  
  
##  <a name="a-namehasvaluea-hasvalue"></a><a name="has_value"></a>has_value 

 Vérifie si cette `single_assignment` bloc de messagerie a encore été initialisé avec une valeur.  
  
```
bool has_value() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le bloc a reçu une valeur, `false` dans le cas contraire.  
  
##  <a name="a-namelinktargetnotificationa-linktargetnotification"></a><a name="link_target_notification"></a>link_target_notification 

 Rappel qui notifie qu’une nouvelle cible a été liée à ce `single_assignment` bloc de messagerie.  
  
```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PTarget`  
 Pointeur vers la cible récemment liée.  
  
##  <a name="a-namepropagatemessagea-propagatemessage"></a><a name="propagate_message"></a>propagate_message 

 Passe de façon asynchrone un message à partir d’un `ISource` à ce bloc `single_assignment` bloc de messagerie. Il est appelé par le `propagate` la méthode appelée par un bloc source.  
  
```
virtual message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PMessage`  
 Pointeur vers l'objet `message`.  
  
 `_PSource`  
 Pointeur vers le bloc source qui transmet le message.  
  
### <a name="return-value"></a>Valeur de retour  
 A [message_status](concurrency-namespace-enums.md) indication de ce que la cible a décidé de faire avec ce message.  
  
##  <a name="a-namepropagatetoanytargetsa-propagatetoanytargets"></a><a name="propagate_to_any_targets"></a>propagate_to_any_targets 

 Place le `message``_PMessage` dans ce `single_assignment` bloc de messagerie et offre à toutes les cibles liées.  
  
```
virtual void propagate_to_any_targets(_Inout_opt_ message<T>* _PMessage);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PMessage`  
 Un pointeur vers un `message` que ce `single_assignment` bloc de messagerie a pris la propriété.  
  
##  <a name="a-namereleasemessagea-releasemessage"></a><a name="release_message"></a>release_message 

 Libère une réservation de message précédente.  
  
```
virtual void release_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de la `message` libéré de l’objet.  
  
##  <a name="a-namereservemessagea-reservemessage"></a><a name="reserve_message"></a>reserve_message 

 Réserve un message précédemment offert par ce `single_assignment` bloc de messagerie.  
  
```
virtual bool reserve_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de la `message` de l’objet en cours de réservation.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le message a été réservé, `false` dans le cas contraire.  
  
### <a name="remarks"></a>Remarques  
 Après avoir `reserve` est appelée, si elle retourne `true`, `consume` ou `release` doit être appelé pour accepter ou libérer la propriété du message.  
  
##  <a name="a-nameresumepropagationa-resumepropagation"></a><a name="resume_propagation"></a>resume_propagation 

 Reprend la propagation après qu’une réservation a été libérée.  
  
```
virtual void resume_propagation();
```  
  
##  <a name="a-namesendmessagea-sendmessage"></a><a name="send_message"></a>send_message 

 Passe de façon synchrone un message à partir d’un `ISource` à ce bloc `single_assignment` bloc de messagerie. Il est appelé par le `send` la méthode appelée par un bloc source.  
  
```
virtual message_status send_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PMessage`  
 Pointeur vers l'objet `message`.  
  
 `_PSource`  
 Pointeur vers le bloc source qui transmet le message.  
  
### <a name="return-value"></a>Valeur de retour  
 A [message_status](concurrency-namespace-enums.md) indication de ce que la cible a décidé de faire avec ce message.  
  
##  <a name="a-namectora-singleassignment"></a><a name="ctor"></a>single_assignment 

 Construit un `single_assignment` bloc de messagerie.  
  
```
single_assignment();

single_assignment(
    filter_method const& _Filter);

single_assignment(
    Scheduler& _PScheduler);

single_assignment(
    Scheduler& _PScheduler,
    filter_method const& _Filter);

single_assignment(
    ScheduleGroup& _PScheduleGroup);

single_assignment(
    ScheduleGroup& _PScheduleGroup,
    filter_method const& _Filter);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Filter`  
 Fonction de filtre qui détermine si les messages transmis doivent être acceptés.  
  
 `_PScheduler`  
 Le `Scheduler` objet dans lequel la tâche de propagation pour le `single_assignment` bloc de messagerie est planifiée.  
  
 `_PScheduleGroup`  
 Le `ScheduleGroup` objet dans lequel la tâche de propagation pour le `single_assignment` bloc de messagerie est planifiée. L’objet `Scheduler` utilisé est suggéré par le groupe de planification.  
  
### <a name="remarks"></a>Remarques  
 Le runtime utilise le planificateur par défaut si vous ne spécifiez pas les paramètres `_PScheduler` ou `_PScheduleGroup` .  
  
 Le type `filter_method` est un functor avec la signature `bool (T const &)` qui est appelé par ce `single_assignment` bloc de messagerie afin de déterminer si elle doit accepter un message proposé.  
  
##  <a name="a-namedtora-singleassignment"></a><a name="dtor"></a>~ single_assignment 

 Détruit le `single_assignment` bloc de messagerie.  
  
```
~single_assignment();
```  
  
##  <a name="a-namevaluea-value"></a><a name="value"></a>valeur 

 Obtient une référence à la charge utile actuelle du message qui est stocké dans le `single_assignment` bloc de messagerie.  
  
```
T const& value();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La charge utile du message stocké.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode attend qu’un message arrive si aucun message n’est actuellement stocké dans le `single_assignment` bloc de messagerie.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [Classe overwrite_buffer](overwrite-buffer-class.md)   
 [Classe unbounded_buffer](unbounded-buffer-class.md)


