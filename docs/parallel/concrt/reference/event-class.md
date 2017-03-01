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
- concrt/concurrency::event
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: abda6512f391b59cb48c8e96a489714ee117ae68
ms.lasthandoff: 02/24/2017

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
|[Reset (méthode)](#reset)|Réinitialise l’événement à un état non signalé.|  
|[Set, méthode](#set)|Signale l’événement.|  
|[Wait (méthode)](#wait)|Attend que l’événement soit signalé.|  
|[wait_for_multiple (méthode)](#wait_for_multiple)|Attend que plusieurs événements soient signalés.|  
  
### <a name="public-constants"></a>Constantes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[timeout_infinite (constante)](#timeout_infinite)|Valeur qui indique qu'une attente ne doit jamais expirer.|  
  
## <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [des Structures de données de synchronisation](../../../parallel/concrt/synchronization-data-structures.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `event`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-namectora-event"></a><a name="ctor"></a>événement 

 Construit un nouvel événement.  
  
```
_CRTIMP event();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namedtora-event"></a><a name="dtor"></a>~ événement 

 Détruit un événement.  
  
```
~event();
```  
  
### <a name="remarks"></a>Remarques  
 Il est probable qu’il n’y a aucun thread n’attend l’événement lorsque le destructeur s’exécute. Autoriser l’événement détruire des threads en attente sur elle entraîne un comportement non défini.  
  
##  <a name="a-namereseta-reset"></a><a name="reset"></a>Réinitialiser 

 Réinitialise l’événement à un état non signalé.  
  
```
void reset();
```  
  
##  <a name="a-nameseta-set"></a><a name="set"></a>ensemble 

 Signale l’événement.  
  
```
void set();
```  
  
### <a name="remarks"></a>Remarques  
 Signalement de l’événement peut provoquer un nombre arbitraire de contextes d’attendre l’événement soit exécutable.  
  
##  <a name="a-nametimeoutinfinitea-timeoutinfinite"></a><a name="timeout_infinite"></a>timeout_infinite 

 Valeur qui indique qu'une attente ne doit jamais expirer.  
  
```
static const unsigned int timeout_infinite = COOPERATIVE_TIMEOUT_INFINITE;
```  
  
##  <a name="a-namewaita-wait"></a><a name="wait"></a>attente 

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
  
##  <a name="a-namewaitformultiplea-waitformultiple"></a><a name="wait_for_multiple"></a>wait_for_multiple 

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
  
### <a name="remarks"></a>Notes  
 Si le paramètre `_FWaitAll` a la valeur `true` pour indiquer que tous les événements doivent être signalés afin de respecter l’attente, l’index retourné par la fonction ne véhicule aucune signification spéciale autre que le fait qu’il n’est pas la valeur `COOPERATIVE_WAIT_TIMEOUT`.  
  
> [!IMPORTANT]
>  Dans un [!INCLUDE[win8_appname_long](../../../build/includes/win8_appname_long_md.md)] application, n’appelez pas `wait_for_multiple` sur l’ASTA thread car ceci peut bloquer le thread actuel et peut entraîner l’application à cesser de répondre.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)

