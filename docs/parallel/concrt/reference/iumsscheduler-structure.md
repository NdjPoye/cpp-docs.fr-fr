---
title: IUMSScheduler (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::IUMSScheduler
dev_langs:
- C++
helpviewer_keywords:
- IUMSScheduler structure
ms.assetid: 3a500225-4e02-4849-bb56-d744865f5870
caps.latest.revision: 18
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
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 658c0d0c9ddb9bbe51134f0a7ea0211be9c39815
ms.lasthandoff: 02/24/2017

---
# <a name="iumsscheduler-structure"></a>IUMSScheduler, structure
Interface avec une abstraction d'un planificateur de tâches qui veut que le gestionnaire des ressources du runtime d'accès concurrentiel lui remette des threads UMS (User-Mode Scheduling). Le gestionnaire des ressources utilise cette interface pour communiquer avec les planificateurs de threads UMS. L'interface `IUMSScheduler` hérite de l'interface `IScheduler`.  
  
## <a name="syntax"></a>Syntaxe  
  
```
struct IUMSScheduler : public IScheduler;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[IUMSScheduler::SetCompletionList, méthode](#setcompletionlist)|Assigne un `IUMSCompletionList` interface à un planificateur de thread UMS.|  
  
## <a name="remarks"></a>Remarques  
 Si vous implémentez un planificateur personnalisé qui communique avec le Gestionnaire de ressources et que vous souhaitez que les threads UMS soient transmis à votre planificateur au lieu de threads Win32 ordinaires, vous devez fournir une implémentation de la `IUMSScheduler` interface. En outre, vous devez définir la valeur de stratégie pour la clé de stratégie du planificateur `SchedulerKind` à `UmsThreadDefault`. Si la stratégie spécifie le thread UMS, le `IScheduler` interface est passée comme paramètre à la [IResourceManager::RegisterScheduler](iresourcemanager-structure.md#registerscheduler) méthode doit être un `IUMSScheduler` interface.  
  
 Le Gestionnaire de ressources est en mesure de vous les threads UMS uniquement sur les systèmes d’exploitation qui ont la fonctionnalité UMS. les systèmes d’exploitation 64 bits avec la version Windows 7 et versions ultérieures prennent en charge des threads UMS. Si vous créez une stratégie du planificateur avec la `SchedulerKind` clé définie sur la valeur `UmsThreadDefault` et la plateforme sous-jacente ne prend pas en charge UMS, la valeur de la `SchedulerKind` clé de cette stratégie est remplacé par la valeur `ThreadScheduler`. Vous devez toujours relire cette valeur de stratégie avant d’attendre de recevoir des threads UMS.  
  
 Le `IUMSScheduler` interface est une extrémité d’un canal bidirectionnel de communication entre un planificateur et le Gestionnaire de ressources. L’autre extrémité est représentée par le `IResourceManager` et `ISchedulerProxy` les interfaces qui sont implémentées par le Gestionnaire de ressources.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [IScheduler](ischeduler-structure.md)  
  
 `IUMSScheduler`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrtrm.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-namesetcompletionlista--iumsschedulersetcompletionlist-method"></a><a name="setcompletionlist"></a>IUMSScheduler::SetCompletionList, méthode  
 Assigne un `IUMSCompletionList` interface à un planificateur de thread UMS.  
  
```
virtual void SetCompletionList(_Inout_ IUMSCompletionList* pCompletionList) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `pCompletionList`  
 Interface de la liste de saisie semi-automatique pour le planificateur. Il existe une liste unique par planificateur.  
  
### <a name="remarks"></a>Remarques  
 Le Gestionnaire de ressources appelle cette méthode sur un planificateur qui indique qu’il veut threads UMS, après que le planificateur a demandé une allocation initiale de ressources. Le planificateur peut utiliser le `IUMSCompletionList` interface pour déterminer quand les proxys de thread UMS ont été débloqués. Il est uniquement valide pour accéder à cette interface à partir d’un proxy de thread en cours d’exécution sur une racine de processeur virtuel affectée au planificateur UMS.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [PolicyElementKey, énumération](concurrency-namespace-enums.md)   
 [IScheduler (Structure)](ischeduler-structure.md)   
 [IUMSCompletionList (Structure)](iumscompletionlist-structure.md)   
 [IResourceManager (Structure)](iresourcemanager-structure.md)

