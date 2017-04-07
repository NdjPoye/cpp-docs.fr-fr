---
title: Classe de message | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- message
- AGENTS/concurrency::message
- AGENTS/concurrency::message::message
- AGENTS/concurrency::message::add_ref
- AGENTS/concurrency::message::msg_id
- AGENTS/concurrency::message::remove_ref
- AGENTS/concurrency::message::payload
dev_langs:
- C++
helpviewer_keywords:
- message class
ms.assetid: 3e1f3505-6c0c-486c-8191-666d0880ec62
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: c6cc72c1fe9385eabe86194031913b7363d602ff
ms.lasthandoff: 03/17/2017

---
# <a name="message-class"></a>message, classe
Enveloppe de message de base contenant la charge utile de données transmise entre les blocs de messagerie.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class T>
class message : public ::Concurrency::details::_Runtime_object;
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Le type de données de la charge utile du message.  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`type`|Alias de type pour `T`.|  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[message](#ctor)|Surchargé. Construit un objet `message`.|  
|[~ message, destructeur](#dtor)|Détruit le `message` objet.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[add_ref](#add_ref)|Ajoute au décompte de références pour le `message` objet. Utilisé pour les blocs de messages qui nécessitent un décompte de références pour déterminer la durée de vie des messages.|  
|[msg_id](#msg_id)|Retourne l’ID de la `message` objet.|  
|[remove_ref](#remove_ref)|Soustrait le nombre de références pour le `message` objet. Utilisé pour les blocs de messages qui nécessitent un décompte de références pour déterminer la durée de vie des messages.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[charge utile](#payload)|La charge utile de la `message` objet.|  
  
## <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [blocs de messages asynchrones](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `message`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="add_ref"></a>add_ref 

 Ajoute au décompte de références pour le `message` objet. Utilisé pour les blocs de messages qui nécessitent un décompte de références pour déterminer la durée de vie des messages.  
  
```
long add_ref();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La nouvelle valeur du décompte de références.  
  
##  <a name="ctor"></a>Message 

 Construit un objet `message`.  
  
```
message(
    T const& _P);

message(
    T const& _P,
    runtime_object_identity _Id);

message(
    message const& _Msg);

message(
    _In_ message const* _Msg);
```  
  
### <a name="parameters"></a>Paramètres  
 `_P`  
 La charge utile de ce message.  
  
 `_Id`  
 ID unique de ce message.  
  
 `_Msg`  
 Une référence ou un pointeur vers un `message` objet.  
  
### <a name="remarks"></a>Notes  
 Le constructeur qui prend un pointeur vers un `message` de l’objet comme argument lève une [invalid_argument](../../../standard-library/invalid-argument-class.md) exception si le paramètre `_Msg` est `NULL`.  
  
##  <a name="dtor"></a>~ message 

 Détruit le `message` objet.  
  
```
virtual ~message();
```  
  
##  <a name="msg_id"></a>msg_id 

 Retourne l’ID de la `message` objet.  
  
```
runtime_object_identity msg_id() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le `runtime_object_identity` de la `message` objet.  
  
##  <a name="payload"></a>charge utile 

 La charge utile de la `message` objet.  
  
```
T const payload;
```  
  
##  <a name="remove_ref"></a>remove_ref 

 Soustrait le nombre de références pour le `message` objet. Utilisé pour les blocs de messages qui nécessitent un décompte de références pour déterminer la durée de vie des messages.  
  
```
long remove_ref();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La nouvelle valeur du décompte de références.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)

