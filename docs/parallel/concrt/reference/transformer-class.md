---
title: Classe transformer | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::transformer
dev_langs:
- C++
helpviewer_keywords:
- transformer class
ms.assetid: eea71925-7043-4a92-bfd4-dbc0ece5d081
caps.latest.revision: 22
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
ms.openlocfilehash: a857a88e33c023ee10db338b658b6652ae0e1a0c
ms.lasthandoff: 02/24/2017

---
# <a name="transformer-class"></a>Classe transformer
Un bloc de messagerie `transformer` est un `propagator_block` à cible unique, à sources multiples et classé qui peut accepter des messages d'un type et est capable de stocker un nombre illimité de messages d'un type différent.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class _Input, class _Output>
class transformer : public propagator_block<single_link_registry<ITarget<_Output>>,
    multi_link_registry<ISource<_Input>>>;
```   
  
#### <a name="parameters"></a>Paramètres  
 `_Input`  
 Type de charge utile des messages acceptés par la mémoire tampon.  
  
 `_Output`  
 Type de charge utile des messages stockés et propagés par la mémoire tampon.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[Constructeur de la classe transformer](#ctor)|Surchargé. Construit un `transformer` bloc de messagerie.|  
|[~ transformer, destructeur](#dtor)|Détruit le `transformer` bloc de messagerie.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[accept_message (méthode)](#accept_message)|Accepte un message qui a été transmis par ce `transformer` messagerie bloc, en transférant la propriété à l’appelant.|  
|[consume_message (méthode)](#consume_message)|Consomme un message précédemment offert par le `transformer` et réservé par la cible, en transférant la propriété à l’appelant.|  
|[link_target_notification (méthode)](#link_target_notification)|Rappel qui notifie qu’une nouvelle cible a été liée à ce `transformer` bloc de messagerie.|  
|[propagate_message (méthode)](#propagate_message)|Passe de façon asynchrone un message à partir d’un `ISource` à ce bloc `transformer` bloc de messagerie. Il est appelé par le `propagate` la méthode appelée par un bloc source.|  
|[propagate_to_any_targets (méthode)](#propagate_to_any_targets)|Exécute la fonction de transformateur sur les messages d’entrée.|  
|[release_message (méthode)](#release_message)|Libère une réservation de message précédente. (Substitue [source_block::release_message](source-block-class.md#release_message).)|  
|[reserve_message (méthode)](#reserve_message)|Réserve un message précédemment offert par ce `transformer` bloc de messagerie. (Substitue [source_block::reserve_message](source-block-class.md#reserve_message).)|  
|[resume_propagation (méthode)](#resume_propagation)|Reprend la propagation après qu’une réservation a été libérée. (Substitue [source_block::resume_propagation](source-block-class.md#resume_propagation).)|  
|[send_message (méthode)](#send_message)|Passe de façon synchrone un message à partir d’un `ISource` à ce bloc `transformer` bloc de messagerie. Il est appelé par le `send` la méthode appelée par un bloc source.|  
|[supports_anonymous_source (méthode)](#supports_anonymous_source)|Remplace la `supports_anonymous_source` méthode pour indiquer que ce bloc peut accepter des messages offerts par une source qui n’est pas liée. (Substitue [ITarget::supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|  
  
## <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [blocs de messages asynchrones](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [ISource](isource-class.md)  
  
 [ITarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 [propagator_block](propagator-block-class.md)  
  
 `transformer`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-nameacceptmessagea-acceptmessage"></a><a name="accept_message"></a>accept_message 

 Accepte un message qui a été transmis par ce `transformer` messagerie bloc, en transférant la propriété à l’appelant.  
  
```
virtual message<_Output>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de l’offerte `message` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le `message` que l’appelant est désormais propriétaire de l’objet.  
  
##  <a name="a-nameconsumemessagea-consumemessage"></a><a name="consume_message"></a>consume_message 

 Consomme un message précédemment offert par le `transformer` et réservé par la cible, en transférant la propriété à l’appelant.  
  
```
virtual message<_Output>* consume_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de la `message` de l’objet en cours de consommation.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le `message` que l’appelant est désormais propriétaire de l’objet.  
  
### <a name="remarks"></a>Remarques  
 Semblable à `accept`, mais est toujours précédé par un appel à `reserve`.  
  
##  <a name="a-namelinktargetnotificationa-linktargetnotification"></a><a name="link_target_notification"></a>link_target_notification 

 Rappel qui notifie qu’une nouvelle cible a été liée à ce `transformer` bloc de messagerie.  
  
```
virtual void link_target_notification(_Inout_ ITarget<_Output> *);
```  
  
##  <a name="a-namepropagatemessagea-propagatemessage"></a><a name="propagate_message"></a>propagate_message 

 Passe de façon asynchrone un message à partir d’un `ISource` à ce bloc `transformer` bloc de messagerie. Il est appelé par le `propagate` la méthode appelée par un bloc source.  
  
```
virtual message_status propagate_message(
    _Inout_ message<_Input>* _PMessage,
    _Inout_ ISource<_Input>* _PSource);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PMessage`  
 Pointeur vers l'objet `message`.  
  
 `_PSource`  
 Pointeur vers le bloc source qui transmet le message.  
  
### <a name="return-value"></a>Valeur de retour  
 A [message_status](concurrency-namespace-enums.md) indication de ce que la cible a décidé de faire avec ce message.  
  
##  <a name="a-namepropagatetoanytargetsa-propagatetoanytargets"></a><a name="propagate_to_any_targets"></a>propagate_to_any_targets 

 Exécute la fonction de transformateur sur les messages d’entrée.  
  
```
virtual void propagate_to_any_targets(_Inout_opt_ message<_Output> *);
```  
  
##  <a name="a-namereleasemessagea-releasemessage"></a><a name="release_message"></a>release_message 

 Libère une réservation de message précédente.  
  
```
virtual void release_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de la `message` libéré de l’objet.  
  
##  <a name="a-namereservemessagea-reservemessage"></a><a name="reserve_message"></a>reserve_message 

 Réserve un message précédemment offert par ce `transformer` bloc de messagerie.  
  
```
virtual bool reserve_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de la `message` de l’objet en cours de réservation.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le message a été réservé, `false` dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 Après avoir `reserve` est appelée, si elle retourne `true`, `consume` ou `release` doit être appelé pour accepter ou libérer la propriété du message.  
  
##  <a name="a-nameresumepropagationa-resumepropagation"></a><a name="resume_propagation"></a>resume_propagation 

 Reprend la propagation après qu’une réservation a été libérée.  
  
```
virtual void resume_propagation();
```  
  
##  <a name="a-namesendmessagea-sendmessage"></a><a name="send_message"></a>send_message 

 Passe de façon synchrone un message à partir d’un `ISource` à ce bloc `transformer` bloc de messagerie. Il est appelé par le `send` la méthode appelée par un bloc source.  
  
```
virtual message_status send_message(
    _Inout_ message<_Input>* _PMessage,
    _Inout_ ISource<_Input>* _PSource);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PMessage`  
 Pointeur vers l'objet `message`.  
  
 `_PSource`  
 Pointeur vers le bloc source qui transmet le message.  
  
### <a name="return-value"></a>Valeur de retour  
 A [message_status](concurrency-namespace-enums.md) indication de ce que la cible a décidé de faire avec ce message.  
  
##  <a name="a-namesupportsanonymoussourcea-supportsanonymoussource"></a><a name="supports_anonymous_source"></a>supports_anonymous_source 

 Remplace la `supports_anonymous_source` méthode pour indiquer que ce bloc peut accepter des messages offerts par une source qui n’est pas liée.  
  
```
virtual bool supports_anonymous_source();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Étant donné que le bloc ne pas reporter des messages transmis.  
  
##  <a name="a-namectora-transformer"></a><a name="ctor"></a>classe transformer 

 Construit un `transformer` bloc de messagerie.  
  
```
transformer(
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget = NULL);

transformer(
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget,
    filter_method const& _Filter);

transformer(
    Scheduler& _PScheduler,
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget = NULL);

transformer(
    Scheduler& _PScheduler,
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget,
    filter_method const& _Filter);

transformer(
    ScheduleGroup& _PScheduleGroup,
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget = NULL);

transformer(
    ScheduleGroup& _PScheduleGroup,
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget,
    filter_method const& _Filter);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Func`  
 Une fonction qui sera appelée pour chaque message accepté.  
  
 `_PTarget`  
 Pointeur vers un bloc cible à lier avec le transformateur.  
  
 `_Filter`  
 Fonction de filtre qui détermine si les messages transmis doivent être acceptés.  
  
 `_PScheduler`  
 Le `Scheduler` objet dans lequel la tâche de propagation pour le `transformer` bloc de messagerie est planifiée.  
  
 `_PScheduleGroup`  
 Le `ScheduleGroup` objet dans lequel la tâche de propagation pour le `transformer` bloc de messagerie est planifiée. L’objet `Scheduler` utilisé est suggéré par le groupe de planification.  
  
### <a name="remarks"></a>Remarques  
 Le runtime utilise le planificateur par défaut si vous ne spécifiez pas les paramètres `_PScheduler` ou `_PScheduleGroup` .  
  
 Le type `_Transform_method` est un functor avec la signature `_Output (_Input const &)` qui est appelé par ce `transformer` bloc de messagerie pour traiter un message.  
  
 Le type `filter_method` est un functor avec la signature `bool (_Input const &)` qui est appelé par ce `transformer` bloc de messagerie afin de déterminer si elle doit accepter un message proposé.  
  
##  <a name="a-namedtora-transformer"></a><a name="dtor"></a>~ transformer 

 Détruit le `transformer` bloc de messagerie.  
  
```
~transformer();
```  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [Call, classe](call-class.md)

