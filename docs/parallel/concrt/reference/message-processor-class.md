---
title: message_processor, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::message_processor
dev_langs:
- C++
helpviewer_keywords:
- message_processor class
ms.assetid: 23afb052-daa7-44ed-bf24-d2513db748da
caps.latest.revision: 16
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
ms.openlocfilehash: 98f1c1072916c4cf3670e40ce0c6ddd1a17f1b63
ms.lasthandoff: 02/24/2017

---
# <a name="messageprocessor-class"></a>message_processor, classe
La classe `message_processor` est la classe de base abstraite pour le traitement des objets `message`. Aucune garantie n'existe sur l'ordre des messages.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class T>
class message_processor;
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Le type de données de la charge utile dans les messages gérés par cet `message_processor` objet.  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`type`|Alias de type pour `T`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[async_send (méthode)](#async_send)|En cas de substitution dans une classe dérivée, place les messages dans le bloc en mode asynchrone.|  
|[sync_send (méthode)](#sync_send)|En cas de substitution dans une classe dérivée, place les messages dans le bloc synchrone.|  
|[Wait (méthode)](#wait)|En cas de substitution dans une classe dérivée, attend que toutes les opérations asynchrones se termine.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[process_incoming_message (méthode)](#process_incoming_message)|En cas de substitution dans une classe dérivée, effectue le traitement de transfert des messages dans le bloc. Appelé à chaque fois qu’un nouveau message est ajouté et la file d’attente n’est pas vide.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `message_processor`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-nameasyncsenda-asyncsend"></a><a name="async_send"></a>async_send 

 En cas de substitution dans une classe dérivée, place les messages dans le bloc en mode asynchrone.  
  
```
virtual void async_send(_Inout_opt_ message<T>* _Msg) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Msg`  
 Un `message` objet à envoyer de façon asynchrone.  
  
### <a name="remarks"></a>Notes  
 Les implémentations de processeur doivent substituer cette méthode.  
  
##  <a name="a-nameprocessincomingmessagea-processincomingmessage"></a><a name="process_incoming_message"></a>process_incoming_message 

 En cas de substitution dans une classe dérivée, effectue le traitement de transfert des messages dans le bloc. Appelé à chaque fois qu’un nouveau message est ajouté et la file d’attente n’est pas vide.  
  
```
virtual void process_incoming_message() = 0;
```  
  
### <a name="remarks"></a>Notes  
 Les implémentations de bloc de message doivent substituer cette méthode.  
  
##  <a name="a-namesyncsenda-syncsend"></a><a name="sync_send"></a>sync_send 

 En cas de substitution dans une classe dérivée, place les messages dans le bloc synchrone.  
  
```
virtual void sync_send(_Inout_opt_ message<T>* _Msg) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Msg`  
 Un `message` objet à envoyer de façon synchrone.  
  
### <a name="remarks"></a>Remarques  
 Les implémentations de processeur doivent substituer cette méthode.  
  
##  <a name="a-namewaita-wait"></a><a name="wait"></a>attente 

 En cas de substitution dans une classe dérivée, attend que toutes les opérations asynchrones se termine.  
  
```
virtual void wait() = 0;
```  
  
### <a name="remarks"></a>Remarques  
 Les implémentations de processeur doivent substituer cette méthode.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [ordered_message_processor, classe](ordered-message-processor-class.md)

