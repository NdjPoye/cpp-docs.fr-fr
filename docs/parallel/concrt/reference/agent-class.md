---
title: agent, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agent
- AGENTS/concurrency::agent
- AGENTS/concurrency::agent::agent
- AGENTS/concurrency::agent::cancel
- AGENTS/concurrency::agent::start
- AGENTS/concurrency::agent::status
- AGENTS/concurrency::agent::status_port
- AGENTS/concurrency::agent::wait
- AGENTS/concurrency::agent::wait_for_all
- AGENTS/concurrency::agent::wait_for_one
- AGENTS/concurrency::agent::done
- AGENTS/concurrency::agent::run
dev_langs:
- C++
helpviewer_keywords:
- agent class
ms.assetid: 1b09e3d2-5e37-4966-b016-907ef1512456
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 1e6e23e742137bffd9035ecf69ecc32d199ca0c5
ms.contentlocale: fr-fr
ms.lasthandoff: 03/20/2017

---
# <a name="agent-class"></a>agent, classe
Classe destinée à être utilisée comme classe de base pour tous les agents indépendants. Elle est utilisée pour masquer l'état des autres agents et interagir par transmission de messages.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class agent;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[agent](#ctor)|Surchargé. Construit un agent.|  
|[~ agent, destructeur](#dtor)|Détruit l’agent.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Annuler](#cancel)|Déplace un agent à partir du `agent_created` ou `agent_runnable` États à la `agent_canceled` état.|  
|[start](#start)|Déplace un agent à partir de la `agent_created` l’état le `agent_runnable` d’état et il planifie l’exécution.|  
|[status](#status)|Source synchrone d’informations d’état de l’agent.|  
|[status_port](#status_port)|Source asynchrone d’informations d’état de l’agent.|  
|[attente](#wait)|Attend qu’un agent ait terminé sa tâche.|  
|[wait_for_all](#wait_for_all)|Attend que tous les agents spécifiés pour effectuer leurs tâches.|  
|[wait_for_one](#wait_for_one)|Attend que l’un des agents spécifiés ait terminé sa tâche.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[terminé](#done)|Déplace un agent dans le `agent_done` état indiquant que l’agent a terminé.|  
|[run](#run)|Représente la tâche principale d’un agent. `run`doit être substituée dans une classe dérivée et spécifie ce que l’agent doit faire après avoir été démarré.|  
  
## <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [Agents asynchrones](../../../parallel/concrt/asynchronous-agents.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `agent`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="ctor"></a>agent 

 Construit un agent.  
  
```
agent();

agent(Scheduler& _PScheduler);

agent(ScheduleGroup& _PGroup);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PScheduler`  
 Le `Scheduler` de l’objet dans lequel la tâche d’exécution de l’agent est planifiée.  
  
 `_PGroup`  
 Le `ScheduleGroup` de l’objet dans lequel la tâche d’exécution de l’agent est planifiée. L’objet `Scheduler` utilisé est suggéré par le groupe de planification.  
  
### <a name="remarks"></a>Notes  
 Le runtime utilise le planificateur par défaut si vous ne spécifiez pas le `_PScheduler` ou `_PGroup` paramètres.  
  
##  <a name="dtor"></a>~ agent 

 Détruit l’agent.  
  
```
virtual ~agent();
```  
  
### <a name="remarks"></a>Remarques  
 Il n’est pas détruire un agent qui n’est pas dans un état terminal (soit `agent_done` ou `agent_canceled`). Cela peut être évité en attendant que l’agent atteigne un état terminal dans le destructeur d’une classe qui hérite de la `agent` classe.  
  
##  <a name="cancel"></a>Annuler 

 Déplace un agent à partir du `agent_created` ou `agent_runnable` États à la `agent_canceled` état.  
  
```
bool cancel();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si l’agent a été annulé, `false` dans le cas contraire. Un agent ne peut pas être annulé si elle a déjà démarré en cours d’exécution ou est déjà terminée.  
  
##  <a name="done"></a>terminé 

 Déplace un agent dans le `agent_done` état indiquant que l’agent a terminé.  
  
```
bool done();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si l’agent est déplacé vers le `agent_done` état `false` dans le cas contraire. Impossible de déplacer un agent qui a été annulé à la `agent_done` état.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode doit être appelée à la fin de la `run` méthode, lorsque vous savez que l’exécution de votre agent est terminée.  
  
##  <a name="run"></a>exécuter 

 Représente la tâche principale d’un agent. `run`doit être substituée dans une classe dérivée et spécifie ce que l’agent doit faire après avoir été démarré.  
  
```
virtual void run() = 0;
```  
  
### <a name="remarks"></a>Remarques  
 L’état de l’agent est passé à `agent_started` avant que cette méthode est appelée. La méthode doit appeler `done` sur l’agent avec un état approprié avant de retourner et ne peut pas lever d’exception.  
  
##  <a name="start"></a>Démarrer 

 Déplace un agent à partir de la `agent_created` l’état le `agent_runnable` d’état et il planifie l’exécution.  
  
```
bool start();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si l’agent a démarré correctement, `false` dans le cas contraire. Impossible de démarrer un agent qui a été annulé.  
  
##  <a name="status"></a>état 

 Source synchrone d’informations d’état de l’agent.  
  
```
agent_status status();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’état actuel de l’agent. Notez que cet état retourné peut changer immédiatement après avoir été retourné.  
  
##  <a name="status_port"></a>status_port 

 Source asynchrone d’informations d’état de l’agent.  
  
```
ISource<agent_status>* status_port();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Renvoie une source de message qui peut envoyer des messages sur l’état actuel de l’agent.  
  
##  <a name="wait"></a>attente 

 Attend qu’un agent ait terminé sa tâche.  
  
```
static agent_status __cdecl wait(
    _Inout_ agent* _PAgent,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PAgent`  
 Pointeur vers l’agent à attendre.  
  
 `_Timeout`  
 La durée maximale d’attente, en millisecondes.  
  
### <a name="return-value"></a>Valeur de retour  
 Le `agent_status` de l’agent lorsque l’attente se termine. Il peut s’agir `agent_canceled` ou `agent_done`.  
  
### <a name="remarks"></a>Remarques  
 Une tâche d’agent est terminée lorsque l’agent passe le `agent_canceled` ou `agent_done` les États.  
  
 Si le paramètre `_Timeout` a une valeur autre que la constante `COOPERATIVE_TIMEOUT_INFINITE`, l’exception [operation_timed_out](operation-timed-out-class.md) est levée si la durée spécifiée expire avant que l’agent a terminé sa tâche.  
  
##  <a name="wait_for_all"></a>wait_for_all 

 Attend que tous les agents spécifiés pour effectuer leurs tâches.  
  
```
static void __cdecl wait_for_all(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    _Out_writes_opt_(count) agent_status* _PStatus = NULL,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Paramètres  
 `count`  
 Le nombre de pointeurs d’agent présents dans le tableau `_PAgents`.  
  
 `_PAgents`  
 Tableau de pointeurs vers les agents à attendre.  
  
 `_PStatus`  
 Pointeur vers un tableau d’états d’agent. Chaque valeur d’état représentera l’état de l’agent correspondant lorsque la méthode retourne.  
  
 `_Timeout`  
 La durée maximale d’attente, en millisecondes.  
  
### <a name="remarks"></a>Notes  
 Une tâche d’agent est terminée lorsque l’agent passe le `agent_canceled` ou `agent_done` les États.  
  
 Si le paramètre `_Timeout` a une valeur autre que la constante `COOPERATIVE_TIMEOUT_INFINITE`, l’exception [operation_timed_out](operation-timed-out-class.md) est levée si la durée spécifiée expire avant que l’agent a terminé sa tâche.  
  
##  <a name="wait_for_one"></a>wait_for_one 

 Attend que l’un des agents spécifiés ait terminé sa tâche.  
  
```
static void __cdecl wait_for_one(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    agent_status& _Status,
    size_t& _Index,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Paramètres  
 `count`  
 Le nombre de pointeurs d’agent présents dans le tableau `_PAgents`.  
  
 `_PAgents`  
 Tableau de pointeurs vers les agents à attendre.  
  
 `_Status`  
 Une référence à une variable où l’état de l’agent sera placé.  
  
 `_Index`  
 Une référence à une variable où l’index d’agent sera placé.  
  
 `_Timeout`  
 La durée maximale d’attente, en millisecondes.  
  
### <a name="remarks"></a>Remarques  
 Une tâche d’agent est terminée lorsque l’agent passe le `agent_canceled` ou `agent_done` les États.  
  
 Si le paramètre `_Timeout` a une valeur autre que la constante `COOPERATIVE_TIMEOUT_INFINITE`, l’exception [operation_timed_out](operation-timed-out-class.md) est levée si la durée spécifiée expire avant que l’agent a terminé sa tâche.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)

