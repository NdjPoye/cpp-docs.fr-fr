---
title: IExecutionContext (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::IExecutionContext
dev_langs:
- C++
helpviewer_keywords:
- IExecutionContext structure
ms.assetid: f3108089-ecda-4b07-86db-3efae60c31e0
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
ms.openlocfilehash: 5ad3f21e55371b904ac8a597a7a66d5c5deb8339
ms.lasthandoff: 02/24/2017

---
# <a name="iexecutioncontext-structure"></a>IExecutionContext, structure
Interface avec un contexte d'exécution qui peut s'exécuter sur un processeur virtuel donné et dont le contexte peut être commuté de manière coopérative.  
  
## <a name="syntax"></a>Syntaxe  
  
```
struct IExecutionContext;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[IExecutionContext::dispatch, méthode](#dispatch)|La méthode est appelée lorsqu’un proxy de thread commence à exécuter un contexte d’exécution spécifique. Il s’agit de la routine de travail principale pour votre planificateur.|  
|[IExecutionContext::GetId, méthode](#getid)|Retourne un identificateur unique pour le contexte d’exécution.|  
|[IExecutionContext::GetProxy, méthode](#getproxy)|Retourne une interface au proxy de thread qui exécute ce contexte.|  
|[IExecutionContext::GetScheduler, méthode](#getscheduler)|Retourne une interface au planificateur auquel appartient ce contexte d’exécution.|  
|[IExecutionContext::SetProxy, méthode](#setproxy)|Associe un proxy de thread à ce contexte d’exécution. Le proxy de thread associé appelle cette méthode juste avant l’exécution du contexte de la `Dispatch` méthode.|  
  
## <a name="remarks"></a>Remarques  
 Si vous implémentez un planificateur personnalisé qui interagit avec le Gestionnaire de ressources du Runtime d’accès concurrentiel, vous devrez implémenter le `IExecutionContext` interface. Les threads créés par le Gestionnaire des ressources exécutent le travail au nom de votre planificateur en exécutant la `IExecutionContext::Dispatch` méthode.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `IExecutionContext`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrtrm.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-namedispatcha--iexecutioncontextdispatch-method"></a><a name="dispatch"></a>IExecutionContext::dispatch, méthode  
 La méthode est appelée lorsqu’un proxy de thread commence à exécuter un contexte d’exécution spécifique. Il s’agit de la routine de travail principale pour votre planificateur.  
  
```
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `pDispatchState`  
 Pointeur vers l’état sous lequel ce contexte d’exécution est distribué. Pour plus d’informations sur l’état de dispatch, consultez [DispatchState](dispatchstate-structure.md).  
  
##  <a name="a-namegetida--iexecutioncontextgetid-method"></a><a name="getid"></a>IExecutionContext::GetId, méthode  
 Retourne un identificateur unique pour le contexte d’exécution.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Identificateur entier unique.  
  
### <a name="remarks"></a>Notes  
 Vous devez utiliser la méthode `GetExecutionContextId` pour obtenir un identificateur unique pour l’objet qui implémente le `IExecutionContext` interface, avant d’utiliser l’interface comme paramètre des méthodes fournies par le Gestionnaire de ressources. Vous devez retourner le même identificateur lorsque la `GetId` fonction est appelée.  
  
 Un identificateur obtenu à partir d’une autre source pourrait entraîner un comportement non défini.  
  
##  <a name="a-namegetproxya--iexecutioncontextgetproxy-method"></a><a name="getproxy"></a>IExecutionContext::GetProxy, méthode  
 Retourne une interface au proxy de thread qui exécute ce contexte.  
  
```
virtual IThreadProxy* GetProxy() = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Interface `IThreadProxy`. Si le proxy de thread du contexte d’exécution n’a pas été initialisé avec un appel à `SetProxy`, la fonction doit retourner `NULL`.  
  
### <a name="remarks"></a>Remarques  
 Appelle le Gestionnaire de ressources du `SetProxy` méthode sur un contexte d’exécution, avec une `IThreadProxy` interface comme paramètre, avant d’entrer le `Dispatch` méthode sur le sur le contexte. Vous devez stocker cet argument et le retourner lors des appels à `GetProxy()`.  
  
##  <a name="a-namegetschedulera--iexecutioncontextgetscheduler-method"></a><a name="getscheduler"></a>IExecutionContext::GetScheduler, méthode  
 Retourne une interface au planificateur auquel appartient ce contexte d’exécution.  
  
```
virtual IScheduler* GetScheduler() = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Interface `IScheduler`.  
  
### <a name="remarks"></a>Remarques  
 Vous devez initialiser le contexte d’exécution avec un nom `IScheduler` interface avant l’utiliser en tant que paramètre aux méthodes fournies par le Gestionnaire de ressources.  
  
##  <a name="a-namesetproxya--iexecutioncontextsetproxy-method"></a><a name="setproxy"></a>IExecutionContext::SetProxy, méthode  
 Associe un proxy de thread à ce contexte d’exécution. Le proxy de thread associé appelle cette méthode juste avant l’exécution du contexte de la `Dispatch` méthode.  
  
```
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `pThreadProxy`  
 Une interface au proxy de thread qui est sur le `Dispatch` méthode sur ce contexte d’exécution.  
  
### <a name="remarks"></a>Notes  
 Vous devez enregistrer le paramètre `pThreadProxy` et le retourner lors d’un appel à la `GetProxy` (méthode). Le Gestionnaire des ressources garantit que le proxy de thread associé au contexte d’exécution ne changera pas pendant que le proxy de thread exécute la `Dispatch` méthode.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [IScheduler (Structure)](ischeduler-structure.md)   
 [IThreadProxy (Structure)](ithreadproxy-structure.md)

