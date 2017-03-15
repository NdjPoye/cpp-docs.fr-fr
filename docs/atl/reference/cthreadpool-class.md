---
title: CThreadPool (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CThreadPool
- ATL::CThreadPool
- CThreadPool
dev_langs:
- C++
helpviewer_keywords:
- CThreadPool class
ms.assetid: 06683718-01b9-413c-9481-2dc1734ec70f
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 632514d03e7037ef42a1566462db5dec6f5cc1e5
ms.lasthandoff: 02/24/2017

---
# <a name="cthreadpool-class"></a>CThreadPool (classe)
Cette classe fournit un pool de threads qui traitent une file d’attente des éléments de travail.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Worker, class ThreadTraits = DefaultThreadTraits>  
class CThreadPool : public IThreadPoolConfig
```  
  
#### <a name="parameters"></a>Paramètres  
 *Travail*  
 La classe conforme à la [archétype de travail](../../atl/reference/worker-archetype.md) en fournissant le code utilisé pour traiter les éléments en file d’attente du pool de threads de travail.  
  
 `ThreadTraits`  
 La classe fournissant la fonction utilisée pour créer les threads dans le pool.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CThreadPool::CThreadPool](#cthreadpool)|Le constructeur pour le pool de threads.|  
|[CThreadPool :: ~ CThreadPool](#dtor)|Le destructeur pour le pool de threads.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CThreadPool::AddRef](#addref)|Implémentation de `IUnknown::AddRef`.|  
|[CThreadPool::GetNumThreads](#getnumthreads)|Appelez cette méthode pour obtenir le nombre de threads dans le pool.|  
|[CThreadPool::GetQueueHandle](#getqueuehandle)|Appelez cette méthode pour obtenir le handle de port de terminaison d’e/s utilisé pour les éléments de travail en file d’attente.|  
|[À CThreadPool::GetSize](#getsize)|Appelez cette méthode pour obtenir le nombre de threads dans le pool.|  
|[CThreadPool::GetTimeout](#gettimeout)|Appelez cette méthode pour obtenir le temps maximal en millisecondes d’attente d’un thread arrêter le pool de threads.|  
|[CThreadPool::Initialize](#initialize)|Appelez cette méthode pour initialiser le pool de threads.|  
|[CThreadPool::QueryInterface](#queryinterface)|Implémentation de **IUnknown::QueryInterface**.|  
|[CThreadPool::QueueRequest](#queuerequest)|Appelez cette méthode pour un élément de travail d’être gérés par un thread du pool de la file d’attente.|  
|[CThreadPool::Release](#release)|Implémentation de `IUnknown::Release`.|  
|[CThreadPool::SetSize](#setsize)|Appelez cette méthode pour définir le nombre de threads dans le pool.|  
|[CThreadPool::SetTimeout](#settimeout)|Appelez cette méthode pour définir le temps maximal en millisecondes d’attente d’un thread arrêter le pool de threads.|  
|[CThreadPool::Shutdown](#shutdown)|Appelez cette méthode pour arrêter le pool de threads.|  
  
## <a name="remarks"></a>Notes  
 Threads du pool sont créés et détruits lorsque le pool est initialisé, le redimensionnement ou s’est arrêté. Une instance de classe *travail* sera créé sur la pile de chaque thread de travail dans le pool. Chaque instance résideront pour la durée de vie du thread.  
  
 Immédiatement après la création d’un thread, *travail*:: `Initialize` seront appelées sur l’objet associé à ce thread. Juste avant la destruction d’un thread, *travail*:: `Terminate` sera appelé. Les deux méthodes doivent accepter une **void\* ** argument. La valeur de cet argument est passée au pool de threads via le `pvWorkerParam` paramètre de [CThreadPool::Initialize](#initialize).  
  
 Lorsqu’il existe des éléments de travail dans les threads de travail et de la file d’attente de travail, un thread de travail extrait un élément de la file d’attente et appelez le **Execute** procédé de la *travail* objet pour ce thread. Trois éléments sont ensuite passés à la méthode : l’élément à partir de la file d’attente, le même `pvWorkerParam` transmis à *travail*:: `Initialize` et *travail*:: `Terminate`et un pointeur vers le [OVERLAPPED](http://msdn.microsoft.com/library/windows/desktop/ms684342) structure utilisée pour la file d’attente de port de terminaison d’e/s.  
  
 Le *travail* classe déclare le type des éléments qui seront mises en attente sur le pool de threads en fournissant un typedef, *travail*:: `RequestType`. Ce type doit pouvoir être casté vers et depuis un **ULONG_PTR entière**.  
  
 Un exemple d’un *travail* classe est [CNonStatelessWorker classe](../../atl/reference/cnonstatelessworker-class.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `IUnknown`  
  
 [Interface IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)  
  
 `CThreadPool`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlutil.h  
  
##  <a name="a-nameaddrefa--cthreadpooladdref"></a><a name="addref"></a>CThreadPool::AddRef  
 Implémentation de `IUnknown::AddRef`.  
  
```
ULONG STDMETHODCALLTYPE AddRef() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours 1.  
  
### <a name="remarks"></a>Remarques  
 Cette classe n’implémente pas de contrôle de durée de vie à l’aide de décompte de références.  
  
##  <a name="a-namecthreadpoola--cthreadpoolcthreadpool"></a><a name="cthreadpool"></a>CThreadPool::CThreadPool  
 Le constructeur pour le pool de threads.  
  
```
CThreadPool() throw();
```  
  
### <a name="remarks"></a>Notes  
 Initialise la valeur de délai d’attente à [ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT](http://msdn.microsoft.com/library/c1e660a7-d490-42af-bbe1-ded76e80cc10).  
  
##  <a name="a-namedtora--cthreadpoolcthreadpool"></a><a name="dtor"></a>CThreadPool :: ~ CThreadPool  
 Le destructeur pour le pool de threads.  
  
```
~CThreadPool() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Appels [CThreadPool::Shutdown](#shutdown).  
  
##  <a name="a-namegetnumthreadsa--cthreadpoolgetnumthreads"></a><a name="getnumthreads"></a>CThreadPool::GetNumThreads  
 Appelez cette méthode pour obtenir le nombre de threads dans le pool.  
  
```
int GetNumThreads() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre de threads dans le pool.  
  
##  <a name="a-namegetqueuehandlea--cthreadpoolgetqueuehandle"></a><a name="getqueuehandle"></a>CThreadPool::GetQueueHandle  
 Appelez cette méthode pour obtenir le handle de port de terminaison d’e/s utilisé pour les éléments de travail en file d’attente.  
  
```
HANDLE GetQueueHandle() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le handle de la file d’attente ou NULL si le pool de threads n’a pas été initialisé.  
  
##  <a name="a-namegetsizea--cthreadpoolgetsize"></a><a name="getsize"></a>À CThreadPool::GetSize  
 Appelez cette méthode pour obtenir le nombre de threads dans le pool.  
  
```
HRESULT STDMETHODCALLTYPE GetSize(int* pnNumThreads) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `pnNumThreads`  
 [out] Adresse de la variable qui, en cas de réussite, reçoit le nombre de threads dans le pool.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
##  <a name="a-namegettimeouta--cthreadpoolgettimeout"></a><a name="gettimeout"></a>CThreadPool::GetTimeout  
 Appelez cette méthode pour obtenir le temps maximal en millisecondes d’attente d’un thread arrêter le pool de threads.  
  
```
HRESULT STDMETHODCALLTYPE GetTimeout(DWORD* pdwMaxWait) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `pdwMaxWait`  
 [out] Adresse de la variable qui, en cas de réussite, reçoit le temps maximal en millisecondes d’attente d’un thread arrêter le pool de threads.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette valeur de délai d’attente est utilisée par [CThreadPool::Shutdown](#shutdown) si aucune autre valeur n’est fournie à cette méthode.  
  
##  <a name="a-nameinitializea--cthreadpoolinitialize"></a><a name="initialize"></a>CThreadPool::Initialize  
 Appelez cette méthode pour initialiser le pool de threads.  
  
```
HRESULT Initialize(
    void* pvWorkerParam = NULL,
    int nNumThreads = 0,
    DWORD dwStackSize = 0,
    HANDLE hCompletion = INVALID_HANDLE_VALUE) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `pvWorkerParam`  
 Le paramètre de travail à passer à l’objet de thread de travail `Initialize`, **Execute**, et `Terminate` méthodes.  
  
 `nNumThreads`  
 Le nombre demandé de threads dans le pool.  
  
 Si `nNumThreads` est négatif, sa valeur absolue sera multiplié par le nombre de processeurs sur l’ordinateur pour obtenir le nombre total de threads.  
  
 Si `nNumThreads` est égal à zéro, [ATLS_DEFAULT_THREADSPERPROC](http://msdn.microsoft.com/library/e0dcf107-72a9-4122-abb4-83c63aa7d571) sera multiplié par le nombre de processeurs sur l’ordinateur pour obtenir le nombre total de threads.  
  
 `dwStackSize`  
 La taille de pile pour chaque thread dans le pool.  
  
 *hCompletion*  
 Le handle d’un objet à associer avec le port de terminaison.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
##  <a name="a-namequeryinterfacea--cthreadpoolqueryinterface"></a><a name="queryinterface"></a>CThreadPool::QueryInterface  
 Implémentation de **IUnknown::QueryInterface**.  
  
```
HRESULT STDMETHODCALLTYPE QueryInterface(REFIID riid, void** ppv) throw();
```  
  
### <a name="remarks"></a>Remarques  
 Objets de cette classe peuvent être interrogées avec succès pour le **IUnknown** et [interface IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md) interfaces.  
  
##  <a name="a-namequeuerequesta--cthreadpoolqueuerequest"></a><a name="queuerequest"></a>CThreadPool::QueueRequest  
 Appelez cette méthode pour un élément de travail d’être gérés par un thread du pool de la file d’attente.  
  
```
BOOL QueueRequest(Worker::RequestType request) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `request`  
 La demande en file d’attente.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE en cas de réussite, FALSE en cas d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode ajoute un élément de travail à la file d’attente. Les threads dans le pool de choisir des éléments de la file d’attente dans l’ordre dans lequel ils sont reçus.  
  
##  <a name="a-namereleasea--cthreadpoolrelease"></a><a name="release"></a>CThreadPool::Release  
 Implémentation de `IUnknown::Release`.  
  
```
ULONG STDMETHODCALLTYPE Release() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours 1.  
  
### <a name="remarks"></a>Notes  
 Cette classe n’implémente pas de contrôle de durée de vie à l’aide de décompte de références.  
  
##  <a name="a-namesetsizea--cthreadpoolsetsize"></a><a name="setsize"></a>CThreadPool::SetSize  
 Appelez cette méthode pour définir le nombre de threads dans le pool.  
  
```
HRESULT STDMETHODCALLTYPE SetSizeint nNumThreads) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nNumThreads`  
 Le nombre demandé de threads dans le pool.  
  
 Si `nNumThreads` est négatif, sa valeur absolue sera multiplié par le nombre de processeurs sur l’ordinateur pour obtenir le nombre total de threads.  
  
 Si `nNumThreads` est égal à zéro, [ATLS_DEFAULT_THREADSPERPROC](http://msdn.microsoft.com/library/e0dcf107-72a9-4122-abb4-83c63aa7d571) sera multiplié par le nombre de processeurs sur l’ordinateur pour obtenir le nombre total de threads.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Si le nombre de threads spécifié est inférieur au nombre de threads actuellement dans le pool, l’objet place un message d’arrêt sur la file d’attente pour être récupéré par un thread en attente. Lorsqu’un thread en attente récupère le message de la file d’attente, il notifie le pool de threads et termine la procédure de thread. Ce processus est répété jusqu'à ce que le nombre de threads dans le pool atteint le nombre spécifié ou jusqu'à ce qu’aucun thread ne s’est arrêté dans le délai spécifié par [GetTimeout](#gettimeout)/ [SetTimeout](#settimeout). Dans ce cas la méthode retourne un HRESULT correspondant à **WAIT_TIMEOUT** et que le message d’arrêt en attente est annulé.  
  
##  <a name="a-namesettimeouta--cthreadpoolsettimeout"></a><a name="settimeout"></a>CThreadPool::SetTimeout  
 Appelez cette méthode pour définir le temps maximal en millisecondes d’attente d’un thread arrêter le pool de threads.  
  
```
HRESULT STDMETHODCALLTYPE SetTimeout(DWORD dwMaxWait) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `dwMaxWait`  
 La durée maximale demandée en millisecondes d’attente d’un thread arrêter le pool de threads.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Le délai d’expiration est initialisé à [ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT](http://msdn.microsoft.com/library/c1e660a7-d490-42af-bbe1-ded76e80cc10) dans le constructeur.  
  
 Notez que `dwMaxWait` est le délai d’attente pour un seul thread arrêter le pool. La durée maximale qui pourrait être prise pour supprimer plusieurs threads du pool peut être légèrement inférieure à `dwMaxWait` multiplié par le nombre de threads.  
  
##  <a name="a-nameshutdowna--cthreadpoolshutdown"></a><a name="shutdown"></a>CThreadPool::Shutdown  
 Appelez cette méthode pour arrêter le pool de threads.  
  
```
void Shutdown(DWORD dwMaxWait = 0) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `dwMaxWait`  
 La durée maximale demandée en millisecondes d’attente d’un thread arrêter le pool de threads. Si 0 ou aucune valeur n’est fournie, cette méthode utilise le délai défini par [CThreadPool::SetTimeout](#settimeout).  
  
### <a name="remarks"></a>Notes  
 Cette méthode publie une demande d’arrêt à tous les threads dans le pool. Si le délai expire, cette méthode appelle [TerminateThread](http://msdn.microsoft.com/library/windows/desktop/ms686717) sur n’importe quel thread qui n’existait pas. Cette méthode est appelée automatiquement à partir du destructeur de la classe.  
  
## <a name="see-also"></a>Voir aussi  
 [Interface de l’interface IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)   
 [DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)   
 [Classes](../../atl/reference/atl-classes.md)

