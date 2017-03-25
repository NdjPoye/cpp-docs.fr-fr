---
title: CurrentScheduler, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CurrentScheduler
- CONCRT/concurrency::CurrentScheduler
- CONCRT/concurrency::CurrentScheduler::Create
- CONCRT/concurrency::CurrentScheduler::CreateScheduleGroup
- CONCRT/concurrency::CurrentScheduler::Detach
- CONCRT/concurrency::CurrentScheduler::Get
- CONCRT/concurrency::CurrentScheduler::GetNumberOfVirtualProcessors
- CONCRT/concurrency::CurrentScheduler::GetPolicy
- CONCRT/concurrency::CurrentScheduler::Id
- CONCRT/concurrency::CurrentScheduler::IsAvailableLocation
- CONCRT/concurrency::CurrentScheduler::RegisterShutdownEvent
- CONCRT/concurrency::CurrentScheduler::ScheduleTask
dev_langs:
- C++
helpviewer_keywords:
- CurrentScheduler class
ms.assetid: 31c20e0e-4cdf-49b4-8220-d726130aad2b
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 9536dd28eeb375f3b9e018539cefb338812e340b
ms.lasthandoff: 03/17/2017

---
# <a name="currentscheduler-class"></a>CurrentScheduler, classe
Représente une abstraction pour le planificateur actuel associé au contexte d'appel.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CurrentScheduler;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Créer](#create)|Crée un nouveau planificateur dont le comportement est décrit par le `_Policy` paramètre et l’attache au contexte d’appel. Le planificateur créé récemment deviendra le planificateur actuel pour le contexte d’appel.|  
|[CreateScheduleGroup](#createschedulegroup)|Surchargé. Crée un nouveau groupe de planification dans le planificateur associé au contexte d’appel. La version qui prend le paramètre `_Placement` entraîne des tâches au sein du groupe de planification nouvellement créée pour être favorise l’exécution à l’emplacement spécifié par ce paramètre.|  
|[Détacher](#detach)|Détache le planificateur actuel du contexte d’appel et restaure le planificateur précédemment associé comme planificateur actuel, s’il en existe. Une fois que cette méthode retourne le contexte d’appel est ensuite géré par le planificateur précédemment attaché au contexte à l’aide du `CurrentScheduler::Create` ou `Scheduler::Attach` (méthode).|  
|[Télécharger](#get)|Retourne un pointeur vers le planificateur associé au contexte d’appel, également appelé planificateur actuel.|  
|[GetNumberOfVirtualProcessors](#getnumberofvirtualprocessors)|Retourne le nombre actuel de processeurs virtuels pour le planificateur associé au contexte d’appel.|  
|[GetPolicy](#getpolicy)|Retourne une copie de la stratégie créée avec le planificateur actuel.|  
|[ID](#id)|Retourne un identificateur unique pour le planificateur actuel.|  
|[IsAvailableLocation](#isavailablelocation)|Détermine si un emplacement donné est disponible sur le planificateur actuel.|  
|[RegisterShutdownEvent](#registershutdownevent)|Événements Windows passé dans le `_ShutdownEvent` paramètre soit signalé lorsque le planificateur associé au contexte actuel s’arrête et détruit proprement dit. Au moment de que l’événement est signalé, tout le travail qui avait été planifié par le planificateur est terminé. Plusieurs événements d’arrêt peuvent être enregistrés via cette méthode.|  
|[ScheduleTask](#scheduletask)|Surchargé. Planifie une tâche légère dans le planificateur associé au contexte d’appel. La tâche légère sera placée dans un groupe de planification déterminée par le runtime. La version qui prend le paramètre `_Placement` entraîne la tâche à être favorise l’exécution à l’emplacement spécifié.|  
  
## <a name="remarks"></a>Remarques  
 S’il n’existe aucun planificateur (consultez [planificateur](scheduler-class.md)) associé au contexte d’appel, de nombreuses méthodes dans la `CurrentScheduler` classe entraîne par défaut planificateur le processus du. Cela peut également impliquer que le planificateur du processus par défaut est créé au cours de cet appel.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `CurrentScheduler`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="create"></a>Créer 

 Crée un nouveau planificateur dont le comportement est décrit par le `_Policy` paramètre et l’attache au contexte d’appel. Le planificateur créé récemment deviendra le planificateur actuel pour le contexte d’appel.  
  
```
static void __cdecl Create(const SchedulerPolicy& _Policy);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Policy`  
 La stratégie du planificateur qui décrit le comportement du planificateur créé récemment.  
  
### <a name="remarks"></a>Notes  
 La pièce jointe du planificateur au contexte d’appel place implicitement un décompte de références sur le planificateur.  
  
 Une fois un planificateur créé avec le `Create` (méthode), vous devez appeler le [CurrentScheduler::Detach](#detach) méthode à un moment donné dans le futur afin d’autoriser l’arrêt du planificateur.  
  
 Si cette méthode est appelée à partir d’un contexte qui est déjà attaché à un planificateur différent, le planificateur existant est mémorisé comme le planificateur précédent, et le planificateur créé récemment devient le planificateur actuel. Lorsque vous appelez le `CurrentScheduler::Detach` méthode ultérieurement, le planificateur précédent est restaurée comme planificateur actuel.  
  
 Cette méthode peut lever diverses exceptions, notamment [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md) et [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md).  
  
##  <a name="createschedulegroup"></a>CreateScheduleGroup 

 Crée un nouveau groupe de planification dans le planificateur associé au contexte d’appel. La version qui prend le paramètre `_Placement` entraîne des tâches au sein du groupe de planification nouvellement créée pour être favorise l’exécution à l’emplacement spécifié par ce paramètre.  
  
```
static ScheduleGroup* __cdecl CreateScheduleGroup();

static ScheduleGroup* __cdecl CreateScheduleGroup(location& _Placement);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Placement`  
 Une référence à un emplacement où les tâches au sein du groupe de planification seront être favorise l’exécution à.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers le groupe de planification créé récemment. Cela `ScheduleGroup` objet possède un décompte de références initial.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode entraîne la création du planificateur par défaut du processus et/ou son attachement au contexte d'appel s'il n'existe aucun planificateur actuellement associé au contexte d'appel.  
  
 Vous devez appeler le [version](schedulegroup-class.md#release) méthode sur un groupe de planification lorsque vous avez fini de planifier le travail pour elle. Le planificateur détruira la planification de groupe lorsque tout le travail en file d’attente pour qu’il a terminé.  
  
 Notez que si vous avez créé ce planificateur explicitement, vous devez libérer toutes les références pour planifier des groupes, avant de libérer votre référence sur le planificateur, en détachant le contexte actuel à partir de celui-ci.  
  
##  <a name="detach"></a>Détacher 

 Détache le planificateur actuel du contexte d’appel et restaure le planificateur précédemment associé comme planificateur actuel, s’il en existe. Une fois que cette méthode retourne le contexte d’appel est ensuite géré par le planificateur précédemment attaché au contexte à l’aide du `CurrentScheduler::Create` ou `Scheduler::Attach` (méthode).  
  
```
static void __cdecl Detach();
```  
  
### <a name="remarks"></a>Remarques  
 Le `Detach` méthode supprime implicitement un décompte de références du planificateur.  
  
 S’il n’existe aucun planificateur associé au contexte d’appel, l’appel de cette méthode entraîne un [scheduler_not_attached](scheduler-not-attached-class.md) exception ne soit levée.  
  
 Appel de cette méthode dans un contexte qui est interne et géré par un planificateur ou un contexte qui a été attaché à l’aide d’une méthode autre que la [Scheduler::Attach](scheduler-class.md#attach) ou [CurrentScheduler::Create](#create) méthodes, entraîne une [improper_scheduler_detach](improper-scheduler-detach-class.md) levée d’exception.  
  
##  <a name="get"></a>Télécharger 

 Retourne un pointeur vers le planificateur associé au contexte d’appel, également appelé planificateur actuel.  
  
```
static Scheduler* __cdecl Get();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers le planificateur associé au contexte d’appel (planificateur actuel).  
  
### <a name="remarks"></a>Remarques  
 Cette méthode entraîne la création du planificateur par défaut du processus et/ou son attachement au contexte d'appel s'il n'existe aucun planificateur actuellement associé au contexte d'appel. Aucune référence supplémentaire n’est placé sur le `Scheduler` objet retourné par cette méthode.  
  
##  <a name="getnumberofvirtualprocessors"></a>GetNumberOfVirtualProcessors 

 Retourne le nombre actuel de processeurs virtuels pour le planificateur associé au contexte d’appel.  
  
```
static unsigned int __cdecl GetNumberOfVirtualProcessors();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si un planificateur est associé au contexte d’appel, le nombre actuel de processeurs virtuels pour ce planificateur ; dans le cas contraire, la valeur `-1`.  
  
### <a name="remarks"></a>Notes  
 Cette méthode n’entraîne pas de pièce jointe planificateur si le contexte d’appel n’est pas déjà associé à un planificateur.  
  
 La valeur de retour de cette méthode est un échantillonnage instantané du nombre de processeurs virtuels pour le planificateur associé au contexte d’appel. Cette valeur peut être obsolète au moment où qu'elle est retournée.  
  
##  <a name="getpolicy"></a>GetPolicy 

 Retourne une copie de la stratégie créée avec le planificateur actuel.  
  
```
static SchedulerPolicy __cdecl GetPolicy();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une copie de la stratégie que le planificateur actuel a été créé.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode entraîne la création du planificateur par défaut du processus et/ou son attachement au contexte d'appel s'il n'existe aucun planificateur actuellement associé au contexte d'appel.  
  
##  <a name="id"></a>ID 

 Retourne un identificateur unique pour le planificateur actuel.  
  
```
static unsigned int __cdecl Id();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si un planificateur est associé au contexte d’appel, un identificateur unique pour ce planificateur ; dans le cas contraire, la valeur `-1`.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode n’entraîne pas de pièce jointe planificateur si le contexte d’appel n’est pas déjà associé à un planificateur.  
  
##  <a name="isavailablelocation"></a>IsAvailableLocation 

 Détermine si un emplacement donné est disponible sur le planificateur actuel.  
  
```
static bool __cdecl IsAvailableLocation(const location& _Placement);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Placement`  
 Une référence à l’emplacement d’une requête sur le planificateur actuel.  
  
### <a name="return-value"></a>Valeur de retour  
 Indique si l’emplacement spécifié par le `_Placement` argument n’est disponible sur le planificateur actuel.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode n’entraîne pas de pièce jointe planificateur si le contexte d’appel n’est pas déjà associé à un planificateur.  
  
 Notez que la valeur de retour est un échantillonnage instantané si l’emplacement spécifié est disponible. En présence de plusieurs planificateurs, gestion dynamique des ressources pour ajouter ou retirer des ressources à partir des planificateurs à tout moment. Le cas échéant, l’emplacement donné peut modifier la disponibilité.  
  
##  <a name="registershutdownevent"></a>RegisterShutdownEvent 

 Événements Windows passé dans le `_ShutdownEvent` paramètre soit signalé lorsque le planificateur associé au contexte actuel s’arrête et détruit proprement dit. Au moment de que l’événement est signalé, tout le travail qui avait été planifié par le planificateur est terminé. Plusieurs événements d’arrêt peuvent être enregistrés via cette méthode.  
  
```
static void __cdecl RegisterShutdownEvent(HANDLE _ShutdownEvent);
```  
  
### <a name="parameters"></a>Paramètres  
 `_ShutdownEvent`  
 Handle vers un objet d’événement Windows qui sera signalé par l’exécution lorsque le planificateur associé au contexte actuel s’arrête et détruit proprement dit.  
  
### <a name="remarks"></a>Remarques  
 S’il n’existe aucun planificateur associé au contexte d’appel, l’appel de cette méthode entraîne un [scheduler_not_attached](scheduler-not-attached-class.md) exception ne soit levée.  
  
##  <a name="scheduletask"></a>ScheduleTask 

 Planifie une tâche légère dans le planificateur associé au contexte d’appel. La tâche légère sera placée dans un groupe de planification déterminée par le runtime. La version qui prend le paramètre `_Placement` entraîne la tâche à être favorise l’exécution à l’emplacement spécifié.  
  
```
static void __cdecl ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data);

static void __cdecl ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data,
    location& _Placement);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Proc`  
 Pointeur vers la fonction à exécuter pour exécuter le corps de la tâche légère.  
  
 `_Data`  
 Un pointeur void vers les données qui seront transmis en tant que paramètre dans le corps de la tâche.  
  
 `_Placement`  
 Une référence à un emplacement où la tâche légère sera être favorise l’exécution à.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode entraîne la création du planificateur par défaut du processus et/ou son attachement au contexte d'appel s'il n'existe aucun planificateur actuellement associé au contexte d'appel.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [Scheduler (classe)](scheduler-class.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [Planificateur de tâches](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)




