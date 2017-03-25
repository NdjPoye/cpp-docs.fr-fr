---
title: Scheduler, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Scheduler
- CONCRT/concurrency::Scheduler
- CONCRT/concurrency::Scheduler::Scheduler
- CONCRT/concurrency::Scheduler::Attach
- CONCRT/concurrency::Scheduler::Create
- CONCRT/concurrency::Scheduler::CreateScheduleGroup
- CONCRT/concurrency::Scheduler::GetNumberOfVirtualProcessors
- CONCRT/concurrency::Scheduler::GetPolicy
- CONCRT/concurrency::Scheduler::Id
- CONCRT/concurrency::Scheduler::IsAvailableLocation
- CONCRT/concurrency::Scheduler::Reference
- CONCRT/concurrency::Scheduler::RegisterShutdownEvent
- CONCRT/concurrency::Scheduler::Release
- CONCRT/concurrency::Scheduler::ResetDefaultSchedulerPolicy
- CONCRT/concurrency::Scheduler::ScheduleTask
- CONCRT/concurrency::Scheduler::SetDefaultSchedulerPolicy
dev_langs:
- C++
helpviewer_keywords:
- Scheduler class
ms.assetid: 34cf7961-048d-4852-8a5c-a32f823e3506
caps.latest.revision: 19
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
ms.openlocfilehash: cc39a524e9a65aeab0c84fb43f5b38ddd892923e
ms.lasthandoff: 03/17/2017

---
# <a name="scheduler-class"></a>Scheduler, classe
Représente une abstraction pour un planificateur de runtime d'accès concurrentiel.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class Scheduler;
```  
  
## <a name="members"></a>Membres  
  
### <a name="protected-constructors"></a>Constructeurs protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[Planificateur](#ctor)|Un objet de la `Scheduler` classe peut uniquement être créé à l’aide de méthodes de fabrique, ou implicitement.|  
|[~ Scheduler, destructeur](#dtor)|Un objet de la `Scheduler` classe est détruite implicitement lorsque toutes les références externes cessent d’exister.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Attacher](#attach)|Attache le planificateur au contexte d’appel. Une fois que cette méthode retourne le contexte d’appel est géré par le planificateur et le planificateur devient le planificateur actuel.|  
|[Créer](#create)|Crée un nouveau planificateur dont le comportement est décrit par le `_Policy` paramètre, place une référence initiale sur le planificateur et retourne un pointeur vers elle.|  
|[CreateScheduleGroup](#createschedulegroup)|Surchargé. Crée un nouveau groupe de planification dans le planificateur. La version qui prend le paramètre `_Placement` entraîne des tâches au sein du groupe de planification nouvellement créée pour être favorise l’exécution à l’emplacement spécifié par ce paramètre.|  
|[GetNumberOfVirtualProcessors](#getnumberofvirtualprocessors)|Retourne le nombre actuel de processeurs virtuels pour le planificateur.|  
|[GetPolicy](#getpolicy)|Retourne une copie de la stratégie que le planificateur a été créé.|  
|[ID](#id)|Retourne un identificateur unique pour le planificateur.|  
|[IsAvailableLocation](#isavailablelocation)|Détermine si un emplacement donné est disponible sur le planificateur.|  
|[Référence](#reference)|Incrémente le décompte de références du planificateur.|  
|[RegisterShutdownEvent](#registershutdownevent)|Événements Windows passé dans le `_Event` paramètre soit signalé lorsque le planificateur s’arrête et détruit proprement dit. Au moment de que l’événement est signalé, tout le travail qui avait été planifié par le planificateur est terminé. Plusieurs événements d’arrêt peuvent être enregistrés via cette méthode.|  
|[Version release](#release)|Décrémente le planificateur décompte de références.|  
|[ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy)|Réinitialise la stratégie du planificateur par défaut à la valeur par défaut du runtime. La prochaine fois qu’un planificateur par défaut est créé, il utilisera les paramètres de stratégie d’exécution par défaut.|  
|[ScheduleTask](#scheduletask)|Surchargé. Planifie une tâche légère dans le planificateur. La tâche légère sera placée dans un groupe de planification déterminée par le runtime. La version qui prend le paramètre `_Placement` entraîne la tâche à être favorise l’exécution à l’emplacement spécifié.|  
|[SetDefaultSchedulerPolicy](#setdefaultschedulerpolicy)|Permet à une stratégie définie par l’utilisateur à utiliser pour créer le planificateur par défaut. Cette méthode peut être appelée uniquement lorsque aucun planificateur par défaut n’existe dans le processus. Une fois une stratégie par défaut a été définie, elle reste en vigueur jusqu’au prochain appel valid soit la `SetDefaultSchedulerPolicy` ou [ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy) (méthode).|  
  
## <a name="remarks"></a>Remarques  
 Le Planificateur de Runtime d’accès concurrentiel utilise des contextes d’exécution, qui mappent vers les contextes d’exécution de système d’exploitation, par exemple un thread, pour exécuter le travail en file d’attente à celle-ci par votre application. À tout moment, le niveau d’accès concurrentiel d’un planificateur est égal au nombre de lui accordé par le Gestionnaire de ressources de processeur virtuel. Un processeur virtuel est une abstraction pour une ressource de traitement et est mappé à un thread matériel sur le système sous-jacent. Seulement un contexte de planificateur unique peut s’exécuter sur un processeur virtuel à un moment donné.  
  
 Le Runtime d’accès concurrentiel créera un planificateur par défaut par processus pour exécuter le travail parallèle. En outre, vous pouvez créer votre propre planificateur instances et les manipuler à l’aide de cette classe.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `Scheduler`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="attach"></a>Joindre 

 Attache le planificateur au contexte d’appel. Une fois que cette méthode retourne le contexte d’appel est géré par le planificateur et le planificateur devient le planificateur actuel.  
  
```
virtual void Attach() = 0;
```  
  
### <a name="remarks"></a>Remarques  
 Attachement d’un planificateur implicitement place une référence sur le planificateur.  
  
 À un moment donné dans le futur, vous devez appeler le [CurrentScheduler::Detach](currentscheduler-class.md#detach) méthode afin de permettre l’arrêt du planificateur.  
  
 Si cette méthode est appelée à partir d’un contexte qui est déjà attaché à un planificateur différent, le planificateur existant est mémorisé comme le planificateur précédent, et le planificateur créé récemment devient le planificateur actuel. Lorsque vous appelez le `CurrentScheduler::Detach` méthode ultérieurement, le planificateur précédent est restaurée comme planificateur actuel.  
  
 Cette méthode lève un [improper_scheduler_attach](improper-scheduler-attach-class.md) exception si ce planificateur est le planificateur actuel du contexte d’appel.  
  
##  <a name="create"></a>Créer 

 Crée un nouveau planificateur dont le comportement est décrit par le `_Policy` paramètre, place une référence initiale sur le planificateur et retourne un pointeur vers elle.  
  
```
static Scheduler* __cdecl Create(const SchedulerPolicy& _Policy);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Policy`  
 La stratégie du planificateur qui décrit le comportement du planificateur créé récemment.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers un planificateur créé récemment. Cela `Scheduler` objet possède un décompte de références initial.  
  
### <a name="remarks"></a>Remarques  
 Une fois un planificateur créé avec le `Create` (méthode), vous devez appeler la `Release` méthode à un moment donné dans le futur afin de supprimer le décompte de références initial et autoriser l’arrêt du planificateur.  
  
 Un planificateur créé avec cette méthode n’est pas attaché au contexte d’appel. Il peut être joint à un contexte à l’aide de la [Attach](#attach) méthode.  
  
 Cette méthode peut lever diverses exceptions, notamment [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md) et [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md).  
  
##  <a name="createschedulegroup"></a>CreateScheduleGroup 

 Crée un nouveau groupe de planification dans le planificateur. La version qui prend le paramètre `_Placement` entraîne des tâches au sein du groupe de planification nouvellement créée pour être favorise l’exécution à l’emplacement spécifié par ce paramètre.  
  
```
virtual ScheduleGroup* CreateScheduleGroup() = 0;

virtual ScheduleGroup* CreateScheduleGroup(location& _Placement) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Placement`  
 Une référence à un emplacement où les tâches au sein du groupe de planification est favorise l’exécution à.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers le groupe de planification créé récemment. Cela `ScheduleGroup` objet possède un décompte de références initial.  
  
### <a name="remarks"></a>Notes  
 Vous devez appeler le [version](schedulegroup-class.md#release) méthode sur un groupe de planification lorsque vous avez fini de planifier le travail pour elle. Le planificateur détruira la planification de groupe lorsque tout le travail en file d’attente pour qu’il a terminé.  
  
 Notez que si vous avez créé ce planificateur explicitement, vous devez libérer toutes les références pour planifier des groupes, avant de libérer votre référence sur le planificateur.  
  
##  <a name="getnumberofvirtualprocessors"></a>GetNumberOfVirtualProcessors 

 Retourne le nombre actuel de processeurs virtuels pour le planificateur.  
  
```
virtual unsigned int GetNumberOfVirtualProcessors() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de processeurs virtuels pour le planificateur actuel.  
  
##  <a name="getpolicy"></a>GetPolicy 

 Retourne une copie de la stratégie que le planificateur a été créé.  
  
```
virtual SchedulerPolicy GetPolicy() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une copie de la stratégie que le planificateur a été créé.  
  
##  <a name="id"></a>ID 

 Retourne un identificateur unique pour le planificateur.  
  
```
virtual unsigned int Id() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Identificateur unique pour le planificateur.  
  
##  <a name="isavailablelocation"></a>IsAvailableLocation 

 Détermine si un emplacement donné est disponible sur le planificateur.  
  
```
virtual bool IsAvailableLocation(const location& _Placement) const = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Placement`  
 Une référence à l’emplacement d’une requête sur le planificateur.  
  
### <a name="return-value"></a>Valeur de retour  
 Indique si l’emplacement spécifié par le `_Placement` argument n’est disponible sur le planificateur.  
  
### <a name="remarks"></a>Remarques  
 Notez que la valeur de retour est un échantillonnage instantané si l’emplacement spécifié est disponible. En présence de plusieurs planificateurs, gestion dynamique des ressources pour ajouter ou retirer des ressources à partir des planificateurs à tout moment. Le cas échéant, l’emplacement donné peut modifier la disponibilité.  
  
##  <a name="reference"></a>Référence 

 Incrémente le décompte de références du planificateur.  
  
```
virtual unsigned int Reference() = 0 ;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le décompte de références incrémenté récemment.  
  
### <a name="remarks"></a>Remarques  
 Cela est généralement utilisé pour gérer la durée de vie du planificateur pour la composition. Lorsque le décompte de références d’un se situe planificateur à zéro, le planificateur s’arrête et CAPACITE de destruction lui-même fonctionne après tout sur le planificateur est terminé.  
  
 La méthode lève un [improper_scheduler_reference](improper-scheduler-reference-class.md) exception si le décompte de références avant d’appeler le `Reference` méthode était nul et l’appel est effectué depuis un contexte qui n’appartienne pas au planificateur.  
  
##  <a name="registershutdownevent"></a>RegisterShutdownEvent 

 Événements Windows passé dans le `_Event` paramètre soit signalé lorsque le planificateur s’arrête et détruit proprement dit. Au moment de que l’événement est signalé, tout le travail qui avait été planifié par le planificateur est terminé. Plusieurs événements d’arrêt peuvent être enregistrés via cette méthode.  
  
```
virtual void RegisterShutdownEvent(HANDLE _Event) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Event`  
 Handle vers un objet d’événement Windows qui sera signalé par l’exécution lorsque le planificateur s’arrête et détruit proprement dit.  
  
##  <a name="release"></a>Version 

 Décrémente le planificateur décompte de références.  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le décompte de références décrémenté récemment.  
  
### <a name="remarks"></a>Remarques  
 Cela est généralement utilisé pour gérer la durée de vie du planificateur pour la composition. Lorsque le décompte de références d’un se situe planificateur à zéro, le planificateur s’arrête et CAPACITE de destruction lui-même fonctionne après tout sur le planificateur est terminé.  
  
##  <a name="resetdefaultschedulerpolicy"></a>ResetDefaultSchedulerPolicy 

 Réinitialise la stratégie du planificateur par défaut à la valeur par défaut du runtime. La prochaine fois qu’un planificateur par défaut est créé, il utilisera les paramètres de stratégie d’exécution par défaut.  
  
```
static void __cdecl ResetDefaultSchedulerPolicy();
```  
  
### <a name="remarks"></a>Remarques  
 Cette méthode peut être appelée pendant un planificateur par défaut existe dans le processus. Cela n’affecte pas la stratégie du planificateur par défaut existant. Toutefois, si le planificateur par défaut s’arrête, et une nouvelle valeur par défaut est créée ultérieurement, le nouveau planificateur serait d’utiliser les paramètres de stratégie d’exécution par défaut.  
  
##  <a name="ctor"></a>Planificateur 

 Un objet de la `Scheduler` classe peut uniquement être créé à l’aide de méthodes de fabrique, ou implicitement.  
  
```
Scheduler();
```  
  
### <a name="remarks"></a>Notes  
 Le planificateur du processus par défaut est créé implicitement lorsque vous utilisez beaucoup des fonctions runtime qui nécessitent un planificateur soit joint au contexte d’appel. Méthodes dans la `CurrentScheduler` classe et les fonctionnalités des bibliothèque PPL et couches d’agents effectuent généralement une pièce jointe implicite.  
  
 Vous pouvez également créer un planificateur explicitement par le biais de la `CurrentScheduler::Create` (méthode) ou `Scheduler::Create` (méthode).  
  
##  <a name="dtor"></a>~ Scheduler 

 Un objet de la `Scheduler` classe est détruite implicitement lorsque toutes les références externes cessent d’exister.  
  
```
virtual ~Scheduler();
```  
  
##  <a name="scheduletask"></a>ScheduleTask 

 Planifie une tâche légère dans le planificateur. La tâche légère sera placée dans un groupe de planification déterminée par le runtime. La version qui prend le paramètre `_Placement` entraîne la tâche à être favorise l’exécution à l’emplacement spécifié.  
  
```
virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data) = 0;

virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data,
    location& _Placement) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Proc`  
 Pointeur vers la fonction à exécuter pour exécuter le corps de la tâche légère.  
  
 `_Data`  
 Un pointeur void vers les données qui seront transmis en tant que paramètre dans le corps de la tâche.  
  
 `_Placement`  
 Une référence à un emplacement où la tâche légère sera être favorise l’exécution à.  
  
##  <a name="setdefaultschedulerpolicy"></a>SetDefaultSchedulerPolicy 

 Permet à une stratégie définie par l’utilisateur à utiliser pour créer le planificateur par défaut. Cette méthode peut être appelée uniquement lorsque aucun planificateur par défaut n’existe dans le processus. Une fois une stratégie par défaut a été définie, elle reste en vigueur jusqu’au prochain appel valid soit la `SetDefaultSchedulerPolicy` ou [ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy) (méthode).  
  
```
static void __cdecl SetDefaultSchedulerPolicy(const SchedulerPolicy& _Policy);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Policy`  
 La stratégie à définir comme stratégie par défaut du planificateur.  
  
### <a name="remarks"></a>Remarques  
 Si le `SetDefaultSchedulerPolicy` est appelée lorsqu’un planificateur par défaut existe déjà dans le processus, le runtime génère une [default_scheduler_exists](default-scheduler-exists-class.md) exception.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [Scheduler (classe)](scheduler-class.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [Planificateur de tâches](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)




