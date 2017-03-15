---
title: ScheduleGroup, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::ScheduleGroup
dev_langs:
- C++
helpviewer_keywords:
- ScheduleGroup class
ms.assetid: 86d380ff-f2e8-411c-b1a8-22bd3079824a
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
ms.openlocfilehash: 424b2f53f39bce57c85e44f0df54928acdac399a
ms.lasthandoff: 02/24/2017

---
# <a name="schedulegroup-class"></a>ScheduleGroup, classe
Représente une abstraction d'un groupe de planification. Les groupes de planification organisent un ensemble de travaux connexes qui ont l’avantage d’être planifiés de façon rapprochée soit dans le temps, en exécutant une autre tâche dans le même groupe avant de passer à un autre groupe, soit dans l’espace, en exécutant plusieurs éléments au sein du même groupe sur le même nœud NUMA ou socket physique.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class ScheduleGroup;
```  
  
## <a name="members"></a>Membres  
  
### <a name="protected-constructors"></a>Constructeurs protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[~ ScheduleGroup, destructeur](#dtor)||  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[ID (méthode)](#id)|Retourne un identificateur pour le groupe de planification qui est unique dans le planificateur auquel le groupe appartient.|  
|[Reference (méthode)](#reference)|Incrémente le décompte de références de groupe de planification.|  
|[Release (méthode)](#release)|Décrémente le planificateur groupe décompte de références.|  
|[ScheduleTask (méthode)](#scheduletask)|Planifie une tâche légère dans le groupe de planification.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `ScheduleGroup`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-nameida-id"></a><a name="id"></a>ID 

 Retourne un identificateur pour le groupe de planification qui est unique dans le planificateur auquel le groupe appartient.  
  
```
virtual unsigned int Id() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Identificateur du groupe de planification qui est unique dans le planificateur auquel le groupe appartient.  
  
##  <a name="a-nameoperatordeletea-operator-delete"></a><a name="operator_delete"></a>opérateur delete 

 Un `ScheduleGroup` est détruit en interne par le runtime lorsque toutes les références externes sont disponibles. Il ne peut pas être supprimé explicitement.  
  
```
void operator delete(
    void* _PObject);

void operator delete(
    void* _PObject,
    int,
 const char *,
    int);
```    
  
### <a name="parameters"></a>Paramètres  
 `_PObject`  
 Pointeur vers l’objet à supprimer.  
  
##  <a name="a-namereferencea-reference"></a><a name="reference"></a>Référence 

 Incrémente le décompte de références de groupe de planification.  
  
```
virtual unsigned int Reference() = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le décompte de références incrémenté récemment.  
  
### <a name="remarks"></a>Remarques  
 Cela est généralement utilisé pour gérer la durée de vie du groupe de planification pour la composition. Lorsque le décompte de références d’un groupe de planification atteint zéro, le groupe de planification est supprimé par le runtime. Un groupe de planification créé à l’aide du [CurrentScheduler::CreateScheduleGroup](currentscheduler-class.md#createschedulegroup) (méthode), ou le [Scheduler::CreateScheduleGroup](scheduler-class.md#createschedulegroup) méthode commence avec un décompte de références d’un.  
  
##  <a name="a-namereleasea-release"></a><a name="release"></a>Version 

 Décrémente le planificateur groupe décompte de références.  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le décompte de références décrémenté récemment.  
  
### <a name="remarks"></a>Remarques  
 Cela est généralement utilisé pour gérer la durée de vie du groupe de planification pour la composition. Lorsque le décompte de références d’un groupe de planification atteint zéro, le groupe de planification est supprimé par le runtime. Après avoir appelé la `Release` méthode le nombre spécifique de fois pour supprimer la création de référence count et toutes les références supplémentaires placées à l’aide de la `Reference` (méthode), vous ne pouvez pas utiliser le groupe de planification. Cela entraînerait un comportement non défini.  
  
 Un groupe de planification est associé à une instance de planificateur spécifique. Vous devez vous assurer que toutes les références au groupe de planification sont libérées avant toutes les références au planificateur, car ce dernier pourrait entraîner la destruction du planificateur. Cela entraîne un comportement dans le cas contraire.  
  
##  <a name="a-namedtora-schedulegroup"></a><a name="dtor"></a>~ ScheduleGroup 

```
virtual ~ScheduleGroup();
```  
  
##  <a name="a-namescheduletaska-scheduletask"></a><a name="scheduletask"></a>ScheduleTask 

 Planifie une tâche légère dans le groupe de planification.  
  
```
virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Proc`  
 Pointeur vers la fonction à exécuter pour exécuter le corps de la tâche légère.  
  
 `_Data`  
 Un pointeur void vers les données qui seront transmis en tant que paramètre dans le corps de la tâche.  
  
### <a name="remarks"></a>Notes  
 Appel de la `ScheduleTask` méthode place implicitement un décompte de références sur le groupe de planification est supprimé par le runtime à un moment approprié après l’exécution de la tâche.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [CurrentScheduler, classe](currentscheduler-class.md)   
 [Scheduler (classe)](scheduler-class.md)   
 [Planificateur de tâches](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)




