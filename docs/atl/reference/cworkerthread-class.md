---
title: Classe CWorkerThread | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CWorkerThread<ThreadTraits>
- ATL::CWorkerThread
- ATL.CWorkerThread
- ATL.CWorkerThread<ThreadTraits>
- CWorkerThread
dev_langs:
- C++
helpviewer_keywords:
- CWorkerThread class
ms.assetid: be79a832-1345-4a36-a13e-a406cc65286f
caps.latest.revision: 24
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
ms.openlocfilehash: ab1c92c1b7442025f91007ef971d81d087351212
ms.lasthandoff: 02/24/2017

---
# <a name="cworkerthread-class"></a>Classe CWorkerThread
Cette classe crée un thread de travail ou utilise un attend sur un ou plusieurs handles d’objet noyau et exécute une fonction de client spécifié lors d’une des poignées est signalée.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class ThreadTraits = DefaultThreadTraits>  
class CWorkerThread
```  
  
#### <a name="parameters"></a>Paramètres  
 `ThreadTraits`  
 La classe fournissant la fonction de création de thread, tel que [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) ou [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md).  
  
## <a name="members"></a>Membres  
  
### <a name="protected-structures"></a>Structures protégés  
  
|Nom|Description|  
|----------|-----------------|  
|`WorkerClientEntry`||  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CWorkerThread::CWorkerThread](#cworkerthread)|Le constructeur pour le thread de travail.|  
|[CWorkerThread :: ~ CWorkerThread](#dtor)|Le destructeur pour le thread de travail.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CWorkerThread::AddHandle](#addhandle)|Appelez cette méthode pour ajouter le handle d’un objet pouvant être attendu à la liste maintenue par le thread de travail.|  
|[CWorkerThread::AddTimer](#addtimer)|Appelez cette méthode pour ajouter une minuterie périodique pouvant être attendue à la liste maintenue par le thread de travail.|  
|[CWorkerThread::GetThreadHandle](#getthreadhandle)|Appelez cette méthode pour obtenir le handle du thread du thread de travail.|  
|[CWorkerThread::GetThreadId](#getthreadid)|Appelez cette méthode pour obtenir l’ID de thread du thread de travail.|  
|[CWorkerThread::Initialize](#initialize)|Appelez cette méthode pour initialiser le thread de travail.|  
|[CWorkerThread::RemoveHandle](#removehandle)|Appelez cette méthode pour supprimer un handle de la liste des objets.|  
|[CWorkerThread::Shutdown](#shutdown)|Appelez cette méthode pour arrêter le thread de travail.|  
  
## <a name="remarks"></a>Remarques  
  
### <a name="to-use-cworkerthread"></a>Pour utiliser CWorkerThread  
  
1.  Créez une instance de cette classe.  
  
2.  Appelez [CWorkerThread::Initialize](#initialize).  
  
3.  Appelez [CWorkerThread::AddHandle](#addhandle) avec le handle d’un objet de noyau et un pointeur vers une implémentation de [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md).  
  
     – ou –  
  
     Appelez [CWorkerThread::AddTimer](#addtimer) avec un pointeur vers une implémentation de [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md).  
  
4.  Implémentez [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) à prendre des mesures lorsque le descripteur ou un minuteur est signalé.  
  
5.  Pour supprimer un objet dans la liste des objets, appelez [CWorkerThread::RemoveHandle](#removehandle).  
  
6.  Pour mettre fin au thread, appelez [CWorkerThread::Shutdown](#shutdown).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlutil.h  
  
##  <a name="a-nameaddhandlea--cworkerthreadaddhandle"></a><a name="addhandle"></a>CWorkerThread::AddHandle  
 Appelez cette méthode pour ajouter le handle d’un objet pouvant être attendu à la liste maintenue par le thread de travail.  
  
```
HRESULT AddHandle(
    HANDLE hObject,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `hObject`  
 Le handle d’un objet pouvant être attendu.  
  
 `pClient`  
 Le pointeur vers le [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) interface sur l’objet à appeler lorsque le handle est signalé.  
  
 `dwParam`  
 Le paramètre doit être passé à [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) lorsque le handle est signalé.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) sera appelé par `pClient` quand le handle, `hObject`, est signalé.  
  
##  <a name="a-nameaddtimera--cworkerthreadaddtimer"></a><a name="addtimer"></a>CWorkerThread::AddTimer  
 Appelez cette méthode pour ajouter une minuterie périodique pouvant être attendue à la liste maintenue par le thread de travail.  
  
```
HRESULT AddTimer(
    DWORD dwInterval,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam,
    HANDLE* phTimer) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 *dwInterval*  
 Spécifie la durée de la minuterie en millisecondes.  
  
 `pClient`  
 Le pointeur vers le [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) interface sur l’objet à appeler lorsque le handle est signalé.  
  
 `dwParam`  
 Le paramètre doit être passé à [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) lorsque le handle est signalé.  
  
 `phTimer`  
 [out] Adresse de la variable de HANDLE qui, en cas de réussite, reçoit le handle lié à la minuterie nouvellement créé.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) sera appelé par `pClient` lorsque la minuterie est signalée.  
  
 Passez le handle du minuteur de `phTimer` à [CWorkerThread::RemoveHandle](#removehandle) pour fermer le minuteur.  
  
##  <a name="a-namecworkerthreada--cworkerthreadcworkerthread"></a><a name="cworkerthread"></a>CWorkerThread::CWorkerThread  
 Constructeur.  
  
```
CWorkerThread() throw();
```  
  
##  <a name="a-namedtora--cworkerthreadcworkerthread"></a><a name="dtor"></a>CWorkerThread :: ~ CWorkerThread  
 Destructeur.  
  
```
~CWorkerThread() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Appels [CWorkerThread::Shutdown](#shutdown).  
  
##  <a name="a-namegetthreadhandlea--cworkerthreadgetthreadhandle"></a><a name="getthreadhandle"></a>CWorkerThread::GetThreadHandle  
 Appelez cette méthode pour obtenir le handle du thread du thread de travail.  
  
```
HANDLE GetThreadHandle() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le handle du thread ou NULL si le thread de travail n’a pas été initialisé.  
  
##  <a name="a-namegetthreadida--cworkerthreadgetthreadid"></a><a name="getthreadid"></a>CWorkerThread::GetThreadId  
 Appelez cette méthode pour obtenir l’ID de thread du thread de travail.  
  
```
DWORD GetThreadId() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’ID de thread ou NULL si le thread de travail n’a pas été initialisé.  
  
##  <a name="a-nameinitializea--cworkerthreadinitialize"></a><a name="initialize"></a>CWorkerThread::Initialize  
 Appelez cette méthode pour initialiser le thread de travail.  
  
```
HRESULT Initialize() throw();

HRESULT Initialize(CWorkerThread<ThreadTraits>* pThread) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `pThread`  
 Un thread de travail existant.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode doit être appelée pour initialiser l’objet après la création ou après un appel à [CWorkerThread::Shutdown](#shutdown).  
  
 Deux ou plusieurs `CWorkerThread` objets utilisent le même thread de travail, un d’eux sans passer d’arguments puis passez un pointeur vers cet objet pour initialiser le `Initialize` méthodes des autres. Les objets sont initialisés à l’aide du pointeur doivent être fermés avant que l’objet utilisé pour les initialiser.  
  
 Consultez la page [CWorkerThread::Shutdown](#shutdown) pour plus d’informations sur les modifications de comportement de cette méthode lorsque initialisé à l’aide d’un pointeur vers un objet existant.  
  
##  <a name="a-nameremovehandlea--cworkerthreadremovehandle"></a><a name="removehandle"></a>CWorkerThread::RemoveHandle  
 Appelez cette méthode pour supprimer un handle de la liste des objets.  
  
```
HRESULT RemoveHandle(HANDLE hObject) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `hObject`  
 Le handle à supprimer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Lorsque le handle est supprimé [IWorkerThreadClient::CloseHandle](../../atl/reference/iworkerthreadclient-interface.md#closehandle) seront appelées sur l’objet associé a été passé à [AddHandle](#addhandle). Si cet appel échoue, `CWorkerThread` appellera Windows [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211) fonction sur le handle.  
  
##  <a name="a-nameshutdowna--cworkerthreadshutdown"></a><a name="shutdown"></a>CWorkerThread::Shutdown  
 Appelez cette méthode pour arrêter le thread de travail.  
  
```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `dwWait`  
 Durée en millisecondes d’attente pour le thread de travail pour l’arrêter.  
  
### <a name="return-value"></a>Valeur de retour  
 Renvoie la valeur S_OK réussite, ou une erreur HRESULT en cas d’échec, par exemple si la valeur de délai d’attente, `dwWait`, est dépassée.  
  
### <a name="remarks"></a>Remarques  
 Pour réutiliser l’objet, appelez [CWorkerThread::Initialize](#initialize) après l’appel de cette méthode.  
  
 Notez que l’appel **arrêt** sur un objet initialisé avec un pointeur vers un autre `CWorkerThread` objet n’a aucun effet et renvoie toujours S_OK.  
  
## <a name="see-also"></a>Voir aussi  
 [DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)   
 [Classes](../../atl/reference/atl-classes.md)   
 [Multithreading : Création de Threads de travail](../../parallel/multithreading-creating-worker-threads.md)   
 [Interface de IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)

