---
title: ITarget, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::ITarget
dev_langs:
- C++
helpviewer_keywords:
- ITarget class
ms.assetid: 5678db25-112a-4f72-be13-42e16b67c48b
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
ms.openlocfilehash: aa9001de9ec35f20cd76f701d6b8acc5de7ffde0
ms.lasthandoff: 02/24/2017

---
# <a name="itarget-class"></a>ITarget, classe
La classe `ITarget` est l'interface de tous les blocs cibles. Les blocs cibles consomment les messages qui leur sont offerts par les blocs `ISource`.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class T>
class ITarget;
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Le type de données de la charge utile dans les messages acceptés par le bloc cible.  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`filter_method`|La signature de toute méthode utilisée par le bloc qui retourne un `bool` afin de déterminer si un message proposé doit être accepté.|  
|`type`|Alias de type pour `T`.|  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[~ ITarget, destructeur](#dtor)|Détruit le `ITarget` objet.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Propagate (méthode)](#propagate)|En cas de substitution dans une classe dérivée, passe de façon asynchrone un message à partir d’un bloc source à ce bloc cible.|  
|[Send (méthode)](#send)|En cas de substitution dans une classe dérivée, passe de façon synchrone un message au bloc cible.|  
|[supports_anonymous_source (méthode)](#supports_anonymous_source)|En cas de substitution dans une classe dérivée, retourne la valeur true ou false selon si le bloc de message accepte des messages offertes par une source qui n’est pas liée à celui-ci. Si la méthode substituée retourne `true`, la cible ne peut pas différer un message proposé, comme la consommation d’un message différé ultérieurement, la source soit identifiée dans son Registre de lien sourse.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[link_source (méthode)](#link_source)|En cas de substitution dans une classe dérivée, lie un bloc source spécifié à ce `ITarget` bloc.|  
|[unlink_source (méthode)](#unlink_source)|En cas de substitution dans une classe dérivée, dissocie un bloc source spécifié à partir de ce `ITarget` bloc.|  
|[unlink_sources (méthode)](#unlink_sources)|En cas de substitution dans une classe dérivée, dissocie tous les blocs de code source à partir de ce `ITarget` bloc.|  
  
## <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [blocs de messages asynchrones](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `ITarget`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-namedtora-itarget"></a><a name="dtor"></a>~ ITarget 

 Détruit le `ITarget` objet.  
  
```
virtual ~ITarget();
```  
  
##  <a name="a-namelinksourcea-linksource"></a><a name="link_source"></a>link_source 

 En cas de substitution dans une classe dérivée, lie un bloc source spécifié à ce `ITarget` bloc.  
  
```
virtual void link_source(_Inout_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_PSource`  
 Le `ISource` bloquer lié à cette `ITarget` bloc.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction ne doit pas être appelée directement sur un `ITarget` bloc. Les blocs doivent être connectés à l’aide de la `link_target` méthode sur `ISource` blocs, qui appelleront le `link_source` méthode sur la cible correspondante.  
  
##  <a name="a-namepropagatea-propagate"></a><a name="propagate"></a>propager 

 En cas de substitution dans une classe dérivée, passe de façon asynchrone un message à partir d’un bloc source à ce bloc cible.  
  
```
virtual message_status propagate(
    _Inout_opt_ message<T>* _PMessage,
    _Inout_opt_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_PMessage`  
 Pointeur vers l'objet `message`.  
  
 `_PSource`  
 Pointeur vers le bloc source qui transmet le message.  
  
### <a name="return-value"></a>Valeur de retour  
 A [message_status](concurrency-namespace-enums.md) indication de ce que la cible a décidé de faire avec ce message.  
  
### <a name="remarks"></a>Remarques  
 La méthode lève un [invalid_argument](../../../standard-library/invalid-argument-class.md) exception si le `_PMessage` ou `_PSource` paramètre est `NULL`.  
  
##  <a name="a-namesenda-send"></a><a name="send"></a>Envoyer 

 En cas de substitution dans une classe dérivée, passe de façon synchrone un message au bloc cible.  
  
```
virtual message_status send(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource) = 0;
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
  
##  <a name="a-namesupportsanonymoussourcea-supportsanonymoussource"></a><a name="supports_anonymous_source"></a>supports_anonymous_source 

 En cas de substitution dans une classe dérivée, retourne la valeur true ou false selon si le bloc de message accepte des messages offertes par une source qui n’est pas liée à celui-ci. Si la méthode substituée retourne `true`, la cible ne peut pas différer un message proposé, comme la consommation d’un message différé ultérieurement, la source soit identifiée dans son Registre de lien sourse.  
  
```
virtual bool supports_anonymous_source();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le bloc peut accepter des messages provenant d’une source qui n’est pas lié à celui-ci `false` dans le cas contraire.  
  
##  <a name="a-nameunlinksourcea-unlinksource"></a><a name="unlink_source"></a>unlink_source 

 En cas de substitution dans une classe dérivée, dissocie un bloc source spécifié à partir de ce `ITarget` bloc.  
  
```
virtual void unlink_source(_Inout_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_PSource`  
 Le `ISource` bloc qui est dissocié de ce `ITarget` bloc.  
  
### <a name="remarks"></a>Notes  
 Cette fonction ne doit pas être appelée directement sur un `ITarget` bloc. Les blocs doivent être déconnectés à l’aide de la `unlink_target` ou `unlink_targets` méthodes sur `ISource` blocs, qui appellent la `unlink_source` méthode sur la cible correspondante.  
  
##  <a name="a-nameunlinksourcesa-unlinksources"></a><a name="unlink_sources"></a>unlink_sources 

 En cas de substitution dans une classe dérivée, dissocie tous les blocs de code source à partir de ce `ITarget` bloc.  
  
```
virtual void unlink_sources() = 0;
```  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [ISource (classe)](isource-class.md)

