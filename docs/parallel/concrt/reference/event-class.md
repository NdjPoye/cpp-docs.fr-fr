---
title: Event, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- event
- CONCRT/concurrency::event
- CONCRT/concurrency::event::reset
- CONCRT/concurrency::event::set
- CONCRT/concurrency::event::wait
- CONCRT/concurrency::event::wait_for_multiple
- CONCRT/concurrency::event::timeout_infinite
dev_langs:
- C++
helpviewer_keywords:
- event class
ms.assetid: fba35a53-6568-4bfa-9aaf-07c0928cf73d
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: f858bfad08ca8d62c42556c54b505908b7122569
ms.lasthandoff: 03/17/2017

---
# <a name="event-class"></a>event, classe
Événement de réinitialisation manuelle qui a explicitement connaissance du runtime d'accès concurrentiel.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class event;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[~ event, destructeur](#dtor)|Détruit un événement.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[reset](#reset)|Réinitialise l’événement à un état non signalé.|  
|[set](#set)|Signale l’événement.|  
|[attente](#wait)|Attend que l’événement soit signalé.|  
|[wait_for_multiple](#wait_for_multiple)|Attend que plusieurs événements soient signalés.|  
  
### <a name="public-constants"></a>Constantes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[timeout_infinite](#timeout_infinite)|Valeur qui indique qu'une attente ne doit jamais expirer.|  
  
## <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [des Structures de données de synchronisation](../../../parallel/concrt/synchronization-data-structures.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `event`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="ctor"></a>événement 

 Construit un nouvel événement.  
  
```
_CRTIMP event();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="dtor"></a>~ événement 

 Détruit un événement.  
  
```
~event();
```  
  
### <a name="remarks"></a>Remarques  
 Il est probable qu’il n’y a aucun thread n’attend l’événement lorsque le destructeur s’exécute. Autoriser l’événement détruire des threads en attente sur elle entraîne un comportement non défini.  
  
##  <a name="reset"></a>Réinitialiser 

 Réinitialise l’événement à un état non signalé.  
  
```
void reset();
```  
  
##  <a name="set"></a>ensemble 

 Signale l’événement.  
  
```
void set();
```  
  
### <a name="remarks"></a>Remarques  
 Signalement de l’événement peut provoquer un nombre arbitraire de contextes d’attendre l’événement soit exécutable.  
  
##  <a name="timeout_infinite"></a>timeout_infinite 

 Valeur qui indique qu'une attente ne doit jamais expirer.  
  
```
static const unsigned int timeout_infinite = COOPERATIVE_TIMEOUT_INFINITE;
```  
  
##  <a name="wait"></a>attente 

 Attend que l’événement soit signalé.  
  
```
size_t wait(unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Timeout`  
 Indique le nombre de millisecondes avant l’attente expire. La valeur `COOPERATIVE_TIMEOUT_INFINITE` signifie qu’il n’existe aucun délai d’attente.  
  
### <a name="return-value"></a>Valeur de retour  
 Si l’attente a été satisfaite, la valeur `0` est retourné ; sinon, la valeur `COOPERATIVE_WAIT_TIMEOUT` pour indiquer que l’attente a expiré sans que l’événement ne soit signalé.  
  
> [!IMPORTANT]
>  Dans un [!INCLUDE[win8_appname_long](../../../build/includes/win8_appname_long_md.md)] application, n’appelez pas `wait` sur l’ASTA thread car ceci peut bloquer le thread actuel et peut entraîner l’application à cesser de répondre.  
  
##  <a name="wait_for_multiple"></a>wait_for_multiple 

 Attend que plusieurs événements soient signalés.  
  
```
static size_t __cdecl wait_for_multiple(
    _In_reads_(count) event** _PPEvents,
    size_t count,
    bool _FWaitAll,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PPEvents`  
 Tableau d’événements à attendre. Le nombre d’événements dans le tableau est indiqué par le `count` paramètre.  
  
 `count`  
 Le nombre d’événements dans le tableau fourni dans le `_PPEvents` paramètre.  
  
 `_FWaitAll`  
 Si la valeur `true`, le paramètre spécifie que tous les événements dans le tableau fourni dans le `_PPEvents` paramètre doit être signalé afin de respecter l’attente. Si la valeur `false`, il spécifie que n’importe quel événement dans le tableau fourni dans le `_PPEvents` paramètre ne soit signalé satisfait l’attente.  
  
 `_Timeout`  
 Indique le nombre de millisecondes avant l’attente expire. La valeur `COOPERATIVE_TIMEOUT_INFINITE` signifie qu’il n’existe aucun délai d’attente.  
  
### <a name="return-value"></a>Valeur de retour  
 Si l’attente a été satisfaite, l’index dans le tableau fourni dans le `_PPEvents` paramètre qui satisfait la condition d’attente ; sinon, la valeur `COOPERATIVE_WAIT_TIMEOUT` pour indiquer que l’attente a expiré sans que la condition satisfaite.  
  
### <a name="remarks"></a>Remarques  
 Si le paramètre `_FWaitAll` a la valeur `true` pour indiquer que tous les événements doivent être signalés afin de respecter l’attente, l’index retourné par la fonction ne véhicule aucune signification spéciale autre que le fait qu’il n’est pas la valeur `COOPERATIVE_WAIT_TIMEOUT`.  
  
> [!IMPORTANT]
>  Dans un [!INCLUDE[win8_appname_long](../../../build/includes/win8_appname_long_md.md)] application, n’appelez pas `wait_for_multiple` sur l’ASTA thread car ceci peut bloquer le thread actuel et peut entraîner l’application à cesser de répondre.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)

