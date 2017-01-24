---
title: "Classe choice | Microsoft Docs"
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
  - "agents/concurrency::choice"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "choice (classe)"
ms.assetid: 4157a539-d5c2-4161-b1ab-536ce2888397
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe choice
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

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
|[choice::choice, constructeur](#choice__choice_constructor)|Surchargé. Construit un bloc de messagerie `choice` .|  
|[choice :: ~ choice, destructeur](#choice___dtorchoice_destructor)|Détruit le `choice` bloc de messagerie.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[choice::Accept, méthode](#choice__accept_method)|Accepte un message qui a été transmis par ce `choice` bloc, en transférant la propriété à l’appelant.|  
|[choice::acquire_ref, méthode](#choice__acquire_ref_method)|Acquiert un décompte de références sur ce `choice` bloc de messagerie, pour empêcher la suppression.|  
|[choice::consume, méthode](#choice__consume_method)|Consomme un message précédemment offert par ce `choice` bloc de messagerie et réservé avec succès par la cible, en transférant la propriété à l’appelant.|  
|[choice::has_value, méthode](#choice__has_value_method)|Vérifie si cette `choice` bloc de messagerie a encore été initialisé avec une valeur.|  
|[choice::index, méthode](#choice__index_method)|Retourne un index dans le `tuple` représentant l’élément sélectionné par le `choice` bloc de messagerie.|  
|[choice::link_target, méthode](#choice__link_target_method)|Lie un bloc cible à ce `choice` bloc de messagerie.|  
|[choice::Release, méthode](#choice__release_method)|Libère une réservation de message réussie précédente.|  
|[choice::release_ref, méthode](#choice__release_ref_method)|Libère un décompte de références sur ce `choice` bloc de messagerie.|  
|[choice::RESERVE, méthode](#choice__reserve_method)|Réserve un message précédemment offert par ce `choice` bloc de messagerie.|  
|[choice::unlink_target, méthode](#choice__unlink_target_method)|Dissocie un bloc cible de ce `choice` bloc de messagerie.|  
|[choice::unlink_targets, méthode](#choice__unlink_targets_method)|Dissocie toutes les cibles de ce `choice` bloc de messagerie. (Substitue [ISource::unlink_targets](../../../parallel/concrt/reference/isource-class.md#isource__unlink_targets_method).)|  
|[choice::value, méthode](#choice__value_method)|Obtient le message dont l’index a été sélectionnée par le `choice` bloc de messagerie.|  
  
## <a name="remarks"></a>Notes  
 Le bloc de choix garantit que seul des messages entrants est consommé.  
  
 Pour plus d’informations, consultez la page [des blocs de messages asynchrones](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 `choice`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-namechoiceacceptmethoda-choiceaccept-method"></a><a name="choice__accept_method"></a>  choice::Accept, méthode  
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
  
##  <a name="a-namechoiceacquirerefmethoda-choiceacquireref-method"></a><a name="choice__acquire_ref_method"></a>  choice::acquire_ref, méthode  
 Acquiert un décompte de références sur ce `choice` bloc de messagerie, pour empêcher la suppression.  
  
```  
virtual void acquire_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PTarget`  
 Pointeur vers le bloc cible qui appelle cette méthode.  
  
### <a name="remarks"></a>Notes  
 Cette méthode est appelée par un `ITarget` objet lié à cette source pendant la `link_target` méthode.  
  
##  <a name="a-namechoicechoiceconstructora-choicechoice-constructor"></a><a name="choice__choice_constructor"></a>  choice::choice, constructeur  
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
  
### <a name="remarks"></a>Notes  
 Le runtime utilise le planificateur par défaut si vous ne spécifiez pas les paramètres `_PScheduler` ou `_PScheduleGroup` .  
  
 La construction du déplacement ne s’exécute pas en présence d’un verrou, ce qui signifie que c’est à l’utilisateur de s’assurer qu’il n’y a pas de tâches non activables en vol au moment du déplacement. Sinon, de nombreuses courses peuvent se produire, ce qui aboutit à des exceptions ou à un état incohérent.  
  
##  <a name="a-namechoicedtorchoicedestructora-choicechoice-destructor"></a><a name="choice___dtorchoice_destructor"></a>  choice :: ~ choice, destructeur  
 Détruit le `choice` bloc de messagerie.  
  
```  
~choice();
```  
  
##  <a name="a-namechoiceconsumemethoda-choiceconsume-method"></a><a name="choice__consume_method"></a>  choice::consume, méthode  
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
  
##  <a name="a-namechoicehasvaluemethoda-choicehasvalue-method"></a><a name="choice__has_value_method"></a>  choice::has_value, méthode  
 Vérifie si cette `choice` bloc de messagerie a encore été initialisé avec une valeur.  
  
```  
bool has_value() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true` Si le bloc a reçu une valeur, `false` dans le cas contraire.  
  
##  <a name="a-namechoiceindexmethoda-choiceindex-method"></a><a name="choice__index_method"></a>  choice::index, méthode  
 Retourne un index dans le `tuple` représentant l’élément sélectionné par le `choice` bloc de messagerie.  
  
```  
size_t index();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Index des messages.  
  
### <a name="remarks"></a>Notes  
 Charge utile de message peut être extraite à l’aide de la `get` méthode.  
  
##  <a name="a-namechoicelinktargetmethoda-choicelinktarget-method"></a><a name="choice__link_target_method"></a>  choice::link_target, méthode  
 Lie un bloc cible à ce `choice` bloc de messagerie.  
  
```  
virtual void link_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PTarget`  
 Un pointeur vers une `ITarget` à lier à ce bloc `choice` bloc de messagerie.  
  
##  <a name="a-namechoicereleasemethoda-choicerelease-method"></a><a name="choice__release_method"></a>  choice::Release, méthode  
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
  
##  <a name="a-namechoicereleaserefmethoda-choicereleaseref-method"></a><a name="choice__release_ref_method"></a>  choice::release_ref, méthode  
 Libère un décompte de références sur ce `choice` bloc de messagerie.  
  
```  
virtual void release_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PTarget`  
 Pointeur vers le bloc cible qui appelle cette méthode.  
  
### <a name="remarks"></a>Notes  
 Cette méthode est appelée par un `ITarget` objet dissocié de cette source. Le bloc source est autorisé à libérer les ressources réservées pour le bloc cible.  
  
##  <a name="a-namechoicereservemethoda-choicereserve-method"></a><a name="choice__reserve_method"></a>  choice::RESERVE, méthode  
 Réserve un message précédemment offert par ce `choice` bloc de messagerie.  
  
```  
virtual bool reserve(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de le `message` de l’objet en cours de réservation.  
  
 `_PTarget`  
 Un pointeur vers le bloc cible qui appelle la `reserve` méthode.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` Si le message a été réservé, `false` dans le cas contraire. Les réservations peuvent échouer pour de nombreuses raisons, notamment : le message a été déjà réservé ou accepté par une autre cible, la source pourrait refuser des réservations et ainsi de suite.  
  
### <a name="remarks"></a>Notes  
 Après avoir appelé `reserve`, si elle réussit, vous devez appeler `consume` ou `release` pour accepter ou renoncer à la possession du message, respectivement.  
  
##  <a name="a-namechoiceunlinktargetmethoda-choiceunlinktarget-method"></a><a name="choice__unlink_target_method"></a>  choice::unlink_target, méthode  
 Dissocie un bloc cible de ce `choice` bloc de messagerie.  
  
```  
virtual void unlink_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PTarget`  
 Un pointeur vers une `ITarget` à dissocier de ce bloc `choice` bloc de messagerie.  
  
##  <a name="a-namechoiceunlinktargetsmethoda-choiceunlinktargets-method"></a><a name="choice__unlink_targets_method"></a>  choice::unlink_targets, méthode  
 Dissocie toutes les cibles de ce `choice` bloc de messagerie.  
  
```  
virtual void unlink_targets();
```  
  
### <a name="remarks"></a>Notes  
 Cette méthode ne doit pas être appelée à partir du destructeur parce que le destructeur pour interne `single_assignment` bloc annulera la liaison correctement.  
  
##  <a name="a-namechoicevaluemethoda-choicevalue-method"></a><a name="choice__value_method"></a>  choice::value, méthode  
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
 [accès concurrentiel Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Join, classe](../../../parallel/concrt/reference/join-class.md)   
 [Classe single_assignment](../../../parallel/concrt/reference/single-assignment-class.md)
