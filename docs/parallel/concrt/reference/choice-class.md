---
title: Classe Choice | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::choice
dev_langs:
- C++
helpviewer_keywords:
- choice class
ms.assetid: 4157a539-d5c2-4161-b1ab-536ce2888397
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
ms.openlocfilehash: 1ee8fe2197a41ad2abc14e24c372f808bdbc16d0
ms.lasthandoff: 02/24/2017

---
# <a name="choice-class"></a>Classe choice
Un bloc de messagerie `choice` est un bloc à plusieurs sources et à cible unique qui représente une interaction de flux de contrôle avec un jeu de sources. Le bloc choice attend que l'une des multiples sources produise un message et propage l'index de la source qui a généré le message.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<
    class T  
>  
class choice: public ISource<size_t>;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Un `tuple`-en fonction du type qui représente les charges utiles des sources d’entrée.  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`type`|Alias de type pour `T`.|  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[choix de constructeur](#ctor)|Surchargé. Construit un bloc de messagerie `choice` .|  
|[~ choice, destructeur](#dtor)|Détruit le `choice` bloc de messagerie.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Accept (méthode)](#accept)|Accepte un message qui a été transmis par ce `choice` bloc, en transférant la propriété à l’appelant.|  
|[acquire_ref (méthode)](#acquire_ref)|Acquiert un décompte de références sur ce `choice` bloc de messagerie, pour empêcher la suppression.|  
|[consume (méthode)](#consume)|Consomme un message précédemment offert par ce `choice` bloc de messagerie et réservé avec succès par la cible, en transférant la propriété à l’appelant.|  
|[has_value (méthode)](#has_value)|Vérifie si cette `choice` bloc de messagerie a encore été initialisé avec une valeur.|  
|[index (méthode)](#index)|Retourne un index dans le `tuple` représentant l’élément sélectionné par le `choice` bloc de messagerie.|  
|[link_target (méthode)](#link_target)|Lie un bloc cible à ce `choice` bloc de messagerie.|  
|[Release (méthode)](#release)|Libère une réservation de message réussie précédente.|  
|[release_ref (méthode)](#release_ref)|Libère un décompte de références sur ce `choice` bloc de messagerie.|  
|[RESERVE (méthode)](#reserve)|Réserve un message précédemment offert par ce `choice` bloc de messagerie.|  
|[unlink_target (méthode)](#unlink_target)|Dissocie un bloc cible de ce `choice` bloc de messagerie.|  
|[unlink_targets (méthode)](#unlink_targets)|Dissocie toutes les cibles de ce `choice` bloc de messagerie. (Substitue [ISource::unlink_targets](isource-class.md#unlink_targets).)|  
|[valeur (méthode)](#value)|Obtient le message dont l’index a été sélectionnée par le `choice` bloc de messagerie.|  
  
## <a name="remarks"></a>Remarques  
 Le bloc de choix garantit que seul des messages entrants est consommé.  
  
 Pour plus d’informations, consultez [blocs de messages asynchrones](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [ISource](isource-class.md)  
  
 `choice`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-nameaccepta-accept"></a><a name="accept"></a>accepter 

 Accepte un message qui a été transmis par ce `choice` bloc, en transférant la propriété à l’appelant.  
  
```  
virtual message<size_t>* accept(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de l’offerte `message` objet.  
  
 `_PTarget`  
 Un pointeur vers le bloc cible qui appelle la `accept` méthode.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers le message dont l’appelant est désormais propriétaire.  
  
##  <a name="a-nameacquirerefa-acquireref"></a><a name="acquire_ref"></a>acquire_ref 

 Acquiert un décompte de références sur ce `choice` bloc de messagerie, pour empêcher la suppression.  
  
```  
virtual void acquire_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PTarget`  
 Pointeur vers le bloc cible qui appelle cette méthode.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode est appelée par une `ITarget` objet lié à cette source pendant la `link_target` méthode.  
  
##  <a name="a-namectora-choice"></a><a name="ctor"></a>choix 

 Construit un bloc de messagerie `choice` .  
  
```  
explicit choice(
    T _Tuple);

 
choice(
    Scheduler& _PScheduler,  
    T _Tuple);

 
choice(
    ScheduleGroup& _PScheduleGroup,  
    T _Tuple);

 
choice(
    choice&& _Choice);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Tuple`  
 `tuple` de sources pour choice.  
  
 `_PScheduler`  
 Objet `Scheduler` dans lequel la tâche de propagation du bloc de messagerie `choice` est planifiée.  
  
 `_PScheduleGroup`  
 Objet `ScheduleGroup` dans lequel la tâche de propagation du bloc de messagerie `choice` est planifiée. L’objet `Scheduler` utilisé est suggéré par le groupe de planification.  
  
 `_Choice`  
 Bloc de messagerie `choice` à partir duquel la copie est effectuée. Notez que l’objet d'origine est orphelin, ce qui en fait un constructeur de déplacement.  
  
### <a name="remarks"></a>Remarques  
 Le runtime utilise le planificateur par défaut si vous ne spécifiez pas les paramètres `_PScheduler` ou `_PScheduleGroup` .  
  
 La construction du déplacement ne s’exécute pas en présence d’un verrou, ce qui signifie que c’est à l’utilisateur de s’assurer qu’il n’y a pas de tâches non activables en vol au moment du déplacement. Sinon, de nombreuses courses peuvent se produire, ce qui aboutit à des exceptions ou à un état incohérent.  
  
##  <a name="a-namedtora-choice"></a><a name="dtor"></a>~ choix 

 Détruit le `choice` bloc de messagerie.  
  
```  
~choice();
```  
  
##  <a name="a-nameconsumea-consume"></a><a name="consume"></a>consommer 

 Consomme un message précédemment offert par ce `choice` bloc de messagerie et réservé avec succès par la cible, en transférant la propriété à l’appelant.  
  
```  
virtual message<size_t>* consume(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de réservée `message` objet.  
  
 `_PTarget`  
 Un pointeur vers le bloc cible qui appelle la `consume` méthode.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le `message` que l’appelant est désormais propriétaire de l’objet.  
  
### <a name="remarks"></a>Notes  
 Le `consume` méthode est similaire à `accept`, mais doit toujours être précédé par un appel à `reserve` qui a retourné `true`.  
  
##  <a name="a-namehasvaluea-hasvalue"></a><a name="has_value"></a>has_value 

 Vérifie si cette `choice` bloc de messagerie a encore été initialisé avec une valeur.  
  
```  
bool has_value() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le bloc a reçu une valeur, `false` dans le cas contraire.  
  
##  <a name="a-nameindexa-index"></a><a name="index"></a>index 

 Retourne un index dans le `tuple` représentant l’élément sélectionné par le `choice` bloc de messagerie.  
  
```  
size_t index();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Index des messages.  
  
### <a name="remarks"></a>Notes  
 Charge utile de message peut être extraite à l’aide de la `get` méthode.  
  
##  <a name="a-namelinktargeta-linktarget"></a><a name="link_target"></a>link_target 

 Lie un bloc cible à ce `choice` bloc de messagerie.  
  
```  
virtual void link_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PTarget`  
 Un pointeur vers un `ITarget` à lier à ce bloc `choice` bloc de messagerie.  
  
##  <a name="a-namereleasea-release"></a><a name="release"></a>version 

 Libère une réservation de message réussie précédente.  
  
```  
virtual void release(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de la `message` libéré de l’objet.  
  
 `_PTarget`  
 Un pointeur vers le bloc cible qui appelle la `release` méthode.  
  
##  <a name="a-namereleaserefa-releaseref"></a><a name="release_ref"></a>release_ref 

 Libère un décompte de références sur ce `choice` bloc de messagerie.  
  
```  
virtual void release_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PTarget`  
 Pointeur vers le bloc cible qui appelle cette méthode.  
  
### <a name="remarks"></a>Notes  
 Cette méthode est appelée par un `ITarget` objet dissocié de cette source. Le bloc source est autorisé à libérer les ressources réservées pour le bloc cible.  
  
##  <a name="a-namereservea-reserve"></a><a name="reserve"></a>réserve 

 Réserve un message précédemment offert par ce `choice` bloc de messagerie.  
  
```  
virtual bool reserve(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de la `message` de l’objet en cours de réservation.  
  
 `_PTarget`  
 Un pointeur vers le bloc cible qui appelle la `reserve` méthode.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le message a été réservé, `false` dans le cas contraire. Les réservations peuvent échouer pour de nombreuses raisons, notamment : le message a été déjà réservé ou accepté par une autre cible, la source pourrait refuser des réservations et ainsi de suite.  
  
### <a name="remarks"></a>Remarques  
 Après avoir appelé `reserve`, si elle réussit, vous devez appeler `consume` ou `release` pour accepter ou renoncer à la possession du message, respectivement.  
  
##  <a name="a-nameunlinktargeta-unlinktarget"></a><a name="unlink_target"></a>unlink_target 

 Dissocie un bloc cible de ce `choice` bloc de messagerie.  
  
```  
virtual void unlink_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PTarget`  
 Un pointeur vers un `ITarget` à dissocier de ce bloc `choice` bloc de messagerie.  
  
##  <a name="a-nameunlinktargetsa-unlinktargets"></a><a name="unlink_targets"></a>unlink_targets 

 Dissocie toutes les cibles de ce `choice` bloc de messagerie.  
  
```  
virtual void unlink_targets();
```  
  
### <a name="remarks"></a>Notes  
 Cette méthode ne doit pas être appelée à partir du destructeur parce que le destructeur pour interne `single_assignment` bloc annulera la liaison correctement.  
  
##  <a name="a-namevaluea-value"></a><a name="value"></a>valeur 

 Obtient le message dont l’index a été sélectionnée par le `choice` bloc de messagerie.  
  
```  
template <
    typename _Payload_type  
>  
_Payload_type const& value();
```  
  
### <a name="parameters"></a>Paramètres  
 `_Payload_type`  
 Type de charge utile de message.  
  
### <a name="return-value"></a>Valeur de retour  
 La charge utile du message.  
  
### <a name="remarks"></a>Notes  
 Car un `choice` bloc de messagerie peut prendre les entrées avec des types de charge utile différentes, vous devez spécifier le type de la charge utile au point de récupération. Vous pouvez déterminer le type selon le résultat de la `index` méthode.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [Join, classe](join-class.md)   
 [Classe single_assignment](single-assignment-class.md)

