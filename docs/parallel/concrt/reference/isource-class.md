---
title: ISource (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ISource
- AGENTS/concurrency::ISource
- AGENTS/concurrency::ISource::accept
- AGENTS/concurrency::ISource::acquire_ref
- AGENTS/concurrency::ISource::consume
- AGENTS/concurrency::ISource::link_target
- AGENTS/concurrency::ISource::release
- AGENTS/concurrency::ISource::release_ref
- AGENTS/concurrency::ISource::reserve
- AGENTS/concurrency::ISource::unlink_target
- AGENTS/concurrency::ISource::unlink_targets
dev_langs:
- C++
helpviewer_keywords:
- ISource class
ms.assetid: c7b73463-42f6-4dcc-801a-81379b12d35a
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: b5545f666dccb251152dc6c9a83101662848be1c
ms.contentlocale: fr-fr
ms.lasthandoff: 03/17/2017

---
# <a name="isource-class"></a>ISource, classe
La classe `ISource` est l'interface de tous les blocs sources. Les blocs sources propagent les messages aux blocs `ITarget`.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class T>
class ISource;
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Le type de données de la charge utile dans les messages produits par le bloc source.  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`source_type`|Alias de type pour `T`.|  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[~ ISource, destructeur](#dtor)|Détruit le `ISource` objet.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[accepter](#accept)|En cas de substitution dans une classe dérivée, accepte un message qui a été transmis par ce `ISource` bloc, en transférant la propriété à l’appelant.|  
|[acquire_ref](#acquire_ref)|En cas de substitution dans une classe dérivée, acquiert un décompte de références sur ce `ISource` bloc, pour empêcher la suppression.|  
|[consommer](#consume)|En cas de substitution dans une classe dérivée, consomme un message précédemment offert par ce `ISource` bloquer et réservé avec succès par la cible, en transférant la propriété à l’appelant.|  
|[link_target](#link_target)|En cas de substitution dans une classe dérivée, lie un bloc cible à ce `ISource` bloc.|  
|[release](#release)|En cas de substitution dans une classe dérivée, libère une réservation de message réussie précédente.|  
|[release_ref](#release_ref)|En cas de substitution dans une classe dérivée, libère un décompte de références sur ce `ISource` bloc.|  
|[reserve](#reserve)|En cas de substitution dans une classe dérivée, réserve un message précédemment offert par ce `ISource` bloc.|  
|[unlink_target](#unlink_target)|En cas de substitution dans une classe dérivée, dissocie un bloc cible de ce `ISource` bloquer, s’il était précédemment lié.|  
|[unlink_targets](#unlink_targets)|En cas de substitution dans une classe dérivée, dissocie tous les blocs cibles de cet `ISource` bloc.|  
  
## <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [blocs de messages asynchrones](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `ISource`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="accept"></a>accepter 

 En cas de substitution dans une classe dérivée, accepte un message qui a été transmis par ce `ISource` bloc, en transférant la propriété à l’appelant.  
  
```
virtual message<T>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de l’offerte `message` objet.  
  
 `_PTarget`  
 Un pointeur vers le bloc cible qui appelle la `accept` méthode.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers le message dont l’appelant est désormais propriétaire.  
  
### <a name="remarks"></a>Remarques  
 Le `accept` méthode est appelée par une cible pendant qu’un message est offert par ce `ISource` bloc. Le pointeur de message retourné peut être différent de celui passé dans le `propagate` procédé de la `ITarget` bloquer, si cette source décide de faire une copie du message.  
  
##  <a name="acquire_ref"></a>acquire_ref 

 En cas de substitution dans une classe dérivée, acquiert un décompte de références sur ce `ISource` bloc, pour empêcher la suppression.  
  
```
virtual void acquire_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_PTarget`  
 Pointeur vers le bloc cible qui appelle cette méthode.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode est appelée par une `ITarget` objet lié à cette source pendant la `link_target` méthode.  
  
##  <a name="consume"></a>consommer 

 En cas de substitution dans une classe dérivée, consomme un message précédemment offert par ce `ISource` bloquer et réservé avec succès par la cible, en transférant la propriété à l’appelant.  
  
```
virtual message<T>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de réservée `message` objet.  
  
 `_PTarget`  
 Un pointeur vers le bloc cible qui appelle la `consume` méthode.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le `message` que l’appelant est désormais propriétaire de l’objet.  
  
### <a name="remarks"></a>Remarques  
 Le `consume` méthode est similaire à `accept`, mais doit toujours être précédé par un appel à `reserve` qui a retourné `true`.  
  
##  <a name="dtor"></a>~ ISource 

 Détruit le `ISource` objet.  
  
```
virtual ~ISource();
```  
  
##  <a name="link_target"></a>link_target 

 En cas de substitution dans une classe dérivée, lie un bloc cible à ce `ISource` bloc.  
  
```
virtual void link_target(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_PTarget`  
 Un pointeur vers le bloc cible qui est lié à cette `ISource` bloc.  
  
##  <a name="release"></a>version 

 En cas de substitution dans une classe dérivée, libère une réservation de message réussie précédente.  
  
```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de réservée `message` objet.  
  
 `_PTarget`  
 Un pointeur vers le bloc cible qui appelle la `release` méthode.  
  
##  <a name="release_ref"></a>release_ref 

 En cas de substitution dans une classe dérivée, libère un décompte de références sur ce `ISource` bloc.  
  
```
virtual void release_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_PTarget`  
 Pointeur vers le bloc cible qui appelle cette méthode.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode est appelée par un `ITarget` objet dissocié de cette source. Le bloc source est autorisé à libérer les ressources réservées pour le bloc cible.  
  
##  <a name="reserve"></a>réserve 

 En cas de substitution dans une classe dérivée, réserve un message précédemment offert par ce `ISource` bloc.  
  
```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_MsgId`  
 Le `runtime_object_identity` de l’offerte `message` objet.  
  
 `_PTarget`  
 Un pointeur vers le bloc cible qui appelle la `reserve` méthode.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le message a été réservé, `false` dans le cas contraire. Les réservations peuvent échouer pour de nombreuses raisons, notamment : le message a été déjà réservé ou accepté par une autre cible, la source pourrait refuser des réservations et ainsi de suite.  
  
### <a name="remarks"></a>Remarques  
 Après avoir appelé `reserve`, si elle réussit, vous devez appeler `consume` ou `release` pour accepter ou renoncer à la possession du message, respectivement.  
  
##  <a name="unlink_target"></a>unlink_target 

 En cas de substitution dans une classe dérivée, dissocie un bloc cible de ce `ISource` bloquer, s’il était précédemment lié.  
  
```
virtual void unlink_target(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_PTarget`  
 Un pointeur vers le bloc cible qui est dissocié de ce `ISource` bloc.  
  
##  <a name="unlink_targets"></a>unlink_targets 

 En cas de substitution dans une classe dérivée, dissocie tous les blocs cibles de cet `ISource` bloc.  
  
```
virtual void unlink_targets() = 0;
```  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [ITarget, classe](itarget-class.md)
