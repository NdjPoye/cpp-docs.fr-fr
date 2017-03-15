---
title: ISource (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::ISource
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
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: db3ba296a96b2e77c0ae7d9be3d0a499fe2e7f76
ms.lasthandoff: 02/24/2017

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
|[Accept (méthode)](#accept)|En cas de substitution dans une classe dérivée, accepte un message qui a été transmis par ce `ISource` bloc, en transférant la propriété à l’appelant.|  
|[acquire_ref (méthode)](#acquire_ref)|En cas de substitution dans une classe dérivée, acquiert un décompte de références sur ce `ISource` bloc, pour empêcher la suppression.|  
|[consume (méthode)](#consume)|En cas de substitution dans une classe dérivée, consomme un message précédemment offert par ce `ISource` bloquer et réservé avec succès par la cible, en transférant la propriété à l’appelant.|  
|[link_target (méthode)](#link_target)|En cas de substitution dans une classe dérivée, lie un bloc cible à ce `ISource` bloc.|  
|[Release (méthode)](#release)|En cas de substitution dans une classe dérivée, libère une réservation de message réussie précédente.|  
|[release_ref (méthode)](#release_ref)|En cas de substitution dans une classe dérivée, libère un décompte de références sur ce `ISource` bloc.|  
|[RESERVE (méthode)](#reserve)|En cas de substitution dans une classe dérivée, réserve un message précédemment offert par ce `ISource` bloc.|  
|[unlink_target (méthode)](#unlink_target)|En cas de substitution dans une classe dérivée, dissocie un bloc cible de ce `ISource` bloquer, s’il était précédemment lié.|  
|[unlink_targets (méthode)](#unlink_targets)|En cas de substitution dans une classe dérivée, dissocie tous les blocs cibles de cet `ISource` bloc.|  
  
## <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [blocs de messages asynchrones](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `ISource`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-nameaccepta-accept"></a><a name="accept"></a>accepter 

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
  
##  <a name="a-nameacquirerefa-acquireref"></a><a name="acquire_ref"></a>acquire_ref 

 En cas de substitution dans une classe dérivée, acquiert un décompte de références sur ce `ISource` bloc, pour empêcher la suppression.  
  
```
virtual void acquire_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_PTarget`  
 Pointeur vers le bloc cible qui appelle cette méthode.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode est appelée par une `ITarget` objet lié à cette source pendant la `link_target` méthode.  
  
##  <a name="a-nameconsumea-consume"></a><a name="consume"></a>consommer 

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
  
### <a name="remarks"></a>Notes  
 Le `consume` méthode est similaire à `accept`, mais doit toujours être précédé par un appel à `reserve` qui a retourné `true`.  
  
##  <a name="a-namedtora-isource"></a><a name="dtor"></a>~ ISource 

 Détruit le `ISource` objet.  
  
```
virtual ~ISource();
```  
  
##  <a name="a-namelinktargeta-linktarget"></a><a name="link_target"></a>link_target 

 En cas de substitution dans une classe dérivée, lie un bloc cible à ce `ISource` bloc.  
  
```
virtual void link_target(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_PTarget`  
 Un pointeur vers le bloc cible qui est lié à cette `ISource` bloc.  
  
##  <a name="a-namereleasea-release"></a><a name="release"></a>version 

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
  
##  <a name="a-namereleaserefa-releaseref"></a><a name="release_ref"></a>release_ref 

 En cas de substitution dans une classe dérivée, libère un décompte de références sur ce `ISource` bloc.  
  
```
virtual void release_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_PTarget`  
 Pointeur vers le bloc cible qui appelle cette méthode.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode est appelée par un `ITarget` objet dissocié de cette source. Le bloc source est autorisé à libérer les ressources réservées pour le bloc cible.  
  
##  <a name="a-namereservea-reserve"></a><a name="reserve"></a>réserve 

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
  
##  <a name="a-nameunlinktargeta-unlinktarget"></a><a name="unlink_target"></a>unlink_target 

 En cas de substitution dans une classe dérivée, dissocie un bloc cible de ce `ISource` bloquer, s’il était précédemment lié.  
  
```
virtual void unlink_target(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_PTarget`  
 Un pointeur vers le bloc cible qui est dissocié de ce `ISource` bloc.  
  
##  <a name="a-nameunlinktargetsa-unlinktargets"></a><a name="unlink_targets"></a>unlink_targets 

 En cas de substitution dans une classe dérivée, dissocie tous les blocs cibles de cet `ISource` bloc.  
  
```
virtual void unlink_targets() = 0;
```  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [ITarget, classe](itarget-class.md)

