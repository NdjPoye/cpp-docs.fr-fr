---
title: Classe de CNonStatelessWorker | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CNonStatelessWorker<Worker>
- ATL::CNonStatelessWorker
- ATL.CNonStatelessWorker
- CNonStatelessWorker
- ATL::CNonStatelessWorker<Worker>
dev_langs:
- C++
helpviewer_keywords:
- CNonStatelessWorker class
ms.assetid: d00936c6-9e7d-49fb-b87d-417b963367d1
caps.latest.revision: 21
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 804b87bf752aac5cecf64cb61b4d53d6269963f2
ms.lasthandoff: 02/24/2017

---
# <a name="cnonstatelessworker-class"></a>CNonStatelessWorker (classe)
Reçoit des demandes à partir d’un pool de threads et les transmet à un objet de travail qui est créé et détruit dans chaque demande.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Worker>  
class CNonStatelessWorker
```  
  
#### <a name="parameters"></a>Paramètres  
 *Travail*  
 Une classe de thread de travail qui se conforment à la [archétype de travail](../../atl/reference/worker-archetype.md) approprié pour la gestion des demandes en attente sur [CThreadPool](../../atl/reference/cthreadpool-class.md).  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CNonStatelessWorker::RequestType](#requesttype)|Implémentation de [WorkerArchetype::RequestType](worker-archetype.md#requesttype).|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CNonStatelessWorker::Execute](#execute)|Implémentation de [WorkerArchetype::Execute](worker-archetype.md#execute).|  
|[CNonStatelessWorker::Initialize](#initialize)|Implémentation de [WorkerArchetype::Initialize](worker-archetype.md#initialize).|  
|[CNonStatelessWorker::Terminate](#terminate)|Implémentation de [WorkerArchetype::Terminate](worker-archetype.md#terminate).|  
  
## <a name="remarks"></a>Remarques  
 Cette classe est un thread de travail simple à utiliser avec [CThreadPool](../../atl/reference/cthreadpool-class.md). Cette classe ne fournit pas toutes les capacités de traitement des demandes qui lui sont propres. Au lieu de cela, il instancie une instance de *travail* par demande et délègue l’implémentation de ses méthodes à cette instance.  
  
 L’avantage de cette classe est qu’il fournit un moyen pratique de modifier le modèle d’état pour les classes de thread de travail existantes. `CThreadPool`Crée un seul processus de travail pour la durée de vie du thread, donc si la classe worker possède un état, il contiendra il sur plusieurs demandes. En encapsulant simplement cette classe dans le `CNonStatelessWorker` modèle avant de l’utiliser avec `CThreadPool`, la durée de vie du travailleur et de l’état qu’il contient est limité à une seule demande.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlutil.h  
  
##  <a name="a-nameexecutea--cnonstatelessworkerexecute"></a><a name="execute"></a>CNonStatelessWorker::Execute  
 Implémentation de [WorkerArchetype::Execute](worker-archetype.md#execute).  

  
```
void Execute(
    Worker::RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```  
  
### <a name="remarks"></a>Remarques  
 Cette méthode crée une instance de la *travail* classe sur la pile et les appels [initialiser](worker-archetype.md#initialize) sur cet objet. Si l’initialisation réussit, cette méthode appelle également [Execute](worker-archetype.md#execute) et [Terminate](worker-archetype.md#terminate) sur le même objet.  

  
##  <a name="a-nameinitializea--cnonstatelessworkerinitialize"></a><a name="initialize"></a>CNonStatelessWorker::Initialize  
 Implémentation de [WorkerArchetype::Initialize](worker-archetype.md#initialize).  
  
```
BOOL Initialize(void* /* pvParam */) throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Renvoie toujours TRUE.  
  
### <a name="remarks"></a>Remarques  
 Cette classe ne toute initialisation `Initialize`.  
  
##  <a name="a-namerequesttypea--cnonstatelessworkerrequesttype"></a><a name="requesttype"></a>CNonStatelessWorker::RequestType  
 Implémentation de [WorkerArchetype::RequestType](worker-archetype.md#requesttype).  
  
```
typedef Worker::RequestType RequestType;
```  
  
### <a name="remarks"></a>Notes  
 Cette classe gère le même type d’élément de travail que la classe utilisée pour le *travail* paramètre de modèle. Consultez la page [CNonStatelessWorker présentation](../../atl/reference/cnonstatelessworker-class.md) pour plus d’informations.  
  
##  <a name="a-nameterminatea--cnonstatelessworkerterminate"></a><a name="terminate"></a>CNonStatelessWorker::Terminate  
 Implémentation de [WorkerArchetype::Terminate](worker-archetype.md#terminate).  
  
```
void Terminate(void* /* pvParam */) throw();
```  
  
### <a name="remarks"></a>Remarques  
 Cette classe ne pas procéder au nettoyage `Terminate`.  
  
## <a name="see-also"></a>Voir aussi  
 [CThreadPool (classe)](../../atl/reference/cthreadpool-class.md)   
 [Archétype de travail](../../atl/reference/worker-archetype.md)   
 [Classes](../../atl/reference/atl-classes.md)

