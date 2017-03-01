---
title: IExecutionResource (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::IExecutionResource
dev_langs:
- C++
helpviewer_keywords:
- IExecutionResource structure
ms.assetid: 6b27042b-b98c-4f7f-b831-566950af84cd
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
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 530fd40409a08be6ae13ad604deb5b85989b2964
ms.lasthandoff: 02/24/2017

---
# <a name="iexecutionresource-structure"></a>IExecutionResource, structure
Abstraction d'un thread matériel.  
  
## <a name="syntax"></a>Syntaxe  
  
```
struct IExecutionResource;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[IExecutionResource::CurrentSubscriptionLevel, méthode](#currentsubscriptionlevel)|Retourne le nombre de processeur virtuel activée racines et inscrit les threads externes actuellement associés au thread matériel sous-jacent que cette ressource d’exécution représente.|  
|[IExecutionResource::GetExecutionResourceId, méthode](#getexecutionresourceid)|Retourne un identificateur unique pour le thread matériel que cette ressource d’exécution représente.|  
|[IExecutionResource::GetNodeId, méthode](#getnodeid)|Retourne un identificateur unique pour le nœud processeur auquel appartient cette ressource d’exécution.|  
|[IExecutionResource::Remove, méthode](#remove)|Retourne cette ressource d’exécution pour le Gestionnaire de ressources.|  
  
## <a name="remarks"></a>Notes  
 Ressources d’exécution peuvent être autonomes ou associées aux racines de processeur virtuel. Une ressource d’exécution autonome est créée lorsqu’un thread dans votre application crée un abonnement de thread. Les méthodes [ISchedulerProxy::SubscribeThread](ischedulerproxy-structure.md#subscribecurrentthread) et [ISchedulerProxy::RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) créent des abonnements de thread et retournent un `IExecutionResource` interface qui représente l’abonnement. Création d’un abonnement de thread est un moyen d’informer le Gestionnaire de ressources qui participe à un thread donné le travail en file d’attente dans un planificateur, ainsi que les racines de processeur virtuel Resource Manager affecte au planificateur. Le Gestionnaire de ressources utilise les informations pour éviter le surabonnement des threads matériels lorsqu’il le peut.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `IExecutionResource`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrtrm.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-namecurrentsubscriptionlevela--iexecutionresourcecurrentsubscriptionlevel-method"></a><a name="currentsubscriptionlevel"></a>IExecutionResource::CurrentSubscriptionLevel, méthode  
 Retourne le nombre de processeur virtuel activée racines et inscrit les threads externes actuellement associés au thread matériel sous-jacent que cette ressource d’exécution représente.  
  
```
virtual unsigned int CurrentSubscriptionLevel() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le niveau d’abonnement actuel.  
  
### <a name="remarks"></a>Remarques  
 Le niveau d’abonnement vous indique le nombre de threads en cours d’exécution associé au thread matériel. Cela inclut uniquement les threads du Gestionnaire de ressources est informé dans le formulaire des threads souscrits et les racines de processeur virtuel qui exécutent activement des proxys de thread.  
  
 Appel de la méthode [ISchedulerProxy::SubscribeCurrentThread](ischedulerproxy-structure.md#subscribecurrentthread), ou la méthode [ISchedulerProxy::RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) avec le paramètre `doSubscribeCurrentThread` la valeur `true` incrémente le niveau d’abonnement d’un thread matériel d’une unité. Elles retournent également une `IExecutionResource` interface qui représente l’abonnement. Un appel correspondant à la [IExecutionResource::Remove](#remove) décrémente niveau d’abonnement du thread matériel d’une unité.  
  
 L’acte d’activation d’une racine de processeur virtuel à l’aide de la méthode [IVirtualProcessorRoot::Activate](ivirtualprocessorroot-structure.md#activate) incrémente le niveau d’abonnement d’un thread matériel d’une unité. Les méthodes [IVirtualProcessorRoot::Deactivate](ivirtualprocessorroot-structure.md#deactivate), ou [IExecutionResource::Remove](#remove) décrémenter le niveau d’abonnement en cas d’appel sur une racine de processeur virtuel activée.  
  
 Le Gestionnaire de ressources utilise les informations au niveau d’abonnement comme l’une des façons de déterminer quand déplacer des ressources entre les planificateurs.  
  
##  <a name="a-namegetexecutionresourceida--iexecutionresourcegetexecutionresourceid-method"></a><a name="getexecutionresourceid"></a>IExecutionResource::GetExecutionResourceId, méthode  
 Retourne un identificateur unique pour le thread matériel que cette ressource d’exécution représente.  
  
```
virtual unsigned int GetExecutionResourceId() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Identificateur unique du thread matériel sous-jacent de cette ressource d’exécution.  
  
### <a name="remarks"></a>Remarques  
 Chaque thread matériel est assigné un identificateur unique par le Runtime d’accès concurrentiel. Si plusieurs ressources d’exécution sont matériel associé thread, ils auront le même identificateur de ressource d’exécution.  
  
##  <a name="a-namegetnodeida--iexecutionresourcegetnodeid-method"></a><a name="getnodeid"></a>IExecutionResource::GetNodeId, méthode  
 Retourne un identificateur unique pour le nœud processeur auquel appartient cette ressource d’exécution.  
  
```
virtual unsigned int GetNodeId() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Identificateur unique pour un nœud de processeur.  
  
### <a name="remarks"></a>Remarques  
 Le Runtime d’accès concurrentiel représente des threads matériels sur le système dans des groupes de nœuds processeur. Nœuds sont dérivés habituellement de la topologie de matériel du système. Par exemple, tous les processeurs sur un socket spécifique ou un nœud NUMA spécifique peuvent appartenir au même nœud du processeur. Le Gestionnaire des ressources assigne des identificateurs uniques à ces nœuds en commençant à `0` de `nodeCount - 1`, où `nodeCount` représente le nombre total de nœuds processeur sur le système.  
  
 Le nombre de nœuds peut être obtenu à partir de la fonction [GetProcessorNodeCount](concurrency-namespace-functions.md).  
  
##  <a name="a-nameremovea--iexecutionresourceremove-method"></a><a name="remove"></a>IExecutionResource::Remove, méthode  
 Retourne cette ressource d’exécution pour le Gestionnaire de ressources.  
  
```
virtual void Remove(_Inout_ IScheduler* pScheduler) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `pScheduler`  
 Interface au planificateur qui fait la demande de suppression de cette ressource d’exécution.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette méthode pour retourner des ressources d’exécution autonomes ainsi que les ressources d’exécution associées aux racines de processeur virtuel pour le Gestionnaire de ressources.  
  
 S’il s’agit d’une ressource d’exécution autonome que vous avez reçue d’une des méthodes [ISchedulerProxy::SubscribeCurrentThread](ischedulerproxy-structure.md#subscribecurrentthread) ou [ISchedulerProxy::RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors), appelant la méthode `Remove` se termine à l’abonnement de thread, la ressource a été créée pour représenter. Vous devez terminer tous les abonnements de thread avant d’arrêter un proxy de planificateur et que vous devez appeler `Remove` à partir du thread qui a créé l’abonnement.  
  
 Racines de processeur virtuel, peuvent être retournées au Gestionnaire de ressources en appelant le `Remove` (méthode), car l’interface `IVirtualProcessorRoot` hérite le `IExecutionResource` interface. Vous devrez peut-être retourner une racine de processeur virtuel en réponse à un appel à la [IScheduler::RemoveVirtualProcessors](ischeduler-structure.md#removevirtualprocessors) (méthode), ou lorsque vous avez terminé avec une racine de processeur virtuel sursouscrite obtenue à partir de la [ISchedulerProxy::CreateOversubscriber](ischedulerproxy-structure.md#createoversubscriber) méthode. Pour les racines de processeur virtuel, il n’existe aucune restriction sur le thread peut appeler la `Remove` méthode.  
  
 `invalid_argument`est levé si le paramètre `pScheduler` est défini sur `NULL`.  
  
 `invalid_operation`est levé si le paramètre `pScheduler` est différent du planificateur que cette ressource d’exécution a été créée, ou, avec une ressource d’exécution autonome, si le thread actuel est différent du thread qui a créé l’abonnement de thread.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [IVirtualProcessorRoot (Structure)](ivirtualprocessorroot-structure.md)

