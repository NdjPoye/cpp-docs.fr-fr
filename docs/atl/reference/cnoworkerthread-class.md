---
title: Classe de CNoWorkerThread | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CNoWorkerThread
- ATLUTIL/ATL::CNoWorkerThread
- ATLUTIL/ATL::CNoWorkerThread::AddHandle
- ATLUTIL/ATL::CNoWorkerThread::AddTimer
- ATLUTIL/ATL::CNoWorkerThread::GetThreadHandle
- ATLUTIL/ATL::CNoWorkerThread::GetThreadId
- ATLUTIL/ATL::CNoWorkerThread::Initialize
- ATLUTIL/ATL::CNoWorkerThread::RemoveHandle
- ATLUTIL/ATL::CNoWorkerThread::Shutdown
dev_langs:
- C++
helpviewer_keywords:
- CNoWorkerThread class
ms.assetid: 29f06bae-b658-4aac-9c14-331e996d25d1
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4c38d778849a31d55a657fc1022c2e9f4a370eec
ms.lasthandoff: 02/24/2017

---
# <a name="cnoworkerthread-class"></a>CNoWorkerThread (classe)
Utilisez cette classe comme argument pour la `MonitorClass` paramètre de modèle pour les classes de cache si vous souhaitez désactiver la gestion de cache dynamique.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CNoWorkerThread
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CNoWorkerThread::AddHandle](#addhandle)|Non fonctionnel équivalent de [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).|  
|[CNoWorkerThread::AddTimer](#addtimer)|Non fonctionnel équivalent de [CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer).|  
|[CNoWorkerThread::GetThreadHandle](#getthreadhandle)|Non fonctionnel équivalent de [CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle).|  
|[CNoWorkerThread::GetThreadId](#getthreadid)|Non fonctionnel équivalent de [CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).|  
|[CNoWorkerThread::Initialize](#initialize)|Non fonctionnel équivalent de [CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize).|  
|[CNoWorkerThread::RemoveHandle](#removehandle)|Non fonctionnel équivalent de [CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle).|  
|[CNoWorkerThread::Shutdown](#shutdown)|Non fonctionnel équivalent de [CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown).|  
  
## <a name="remarks"></a>Remarques  
 Cette classe fournit la même interface publique en tant que [CWorkerThread](../../atl/reference/cworkerthread-class.md). Cette interface devrait être fourni par le `MonitorClass` paramètre de modèle pour les classes de cache.  
  
 Les méthodes de cette classe sont implémentées pour ne rien faire. Les méthodes qui retournent une valeur HRESULT toujours retournent S_OK et les méthodes qui retournent un ID de HANDLE ou de thread toujours retournent 0.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlutil.h  
  
##  <a name="addhandle"></a>CNoWorkerThread::AddHandle  
 Non fonctionnel équivalent de [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
```
HRESULT AddHandle(HANDLE /* hObject
 */,
    IWorkerThreadClient* /* pClient
 */,
    DWORD_PTR /* dwParam
 */) throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours S_OK.  
  
### <a name="remarks"></a>Notes  
 L’implémentation fournie par cette classe ne fait rien.  
  
##  <a name="addtimer"></a>CNoWorkerThread::AddTimer  
 Non fonctionnel équivalent de [CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer).  
  
```
HRESULT AddTimer(DWORD /* dwInterval
 */,
    IWorkerThreadClient* /* pClient
 */,
    DWORD_PTR /* dwParam
 */,
    HANDLE* /* phTimer
 */) throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours S_OK.  
  
### <a name="remarks"></a>Remarques  
 L’implémentation fournie par cette classe ne fait rien.  
  
##  <a name="getthreadhandle"></a>CNoWorkerThread::GetThreadHandle  
 Non fonctionnel équivalent de [CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle).  
  
```
HANDLE GetThreadHandle() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours NULL.  
  
### <a name="remarks"></a>Remarques  
 L’implémentation fournie par cette classe ne fait rien.  
  
##  <a name="getthreadid"></a>CNoWorkerThread::GetThreadId  
 Non fonctionnel équivalent de [CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).  
  
```
DWORD GetThreadId() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours 0.  
  
### <a name="remarks"></a>Notes  
 L’implémentation fournie par cette classe ne fait rien.  
  
##  <a name="initialize"></a>CNoWorkerThread::Initialize  
 Non fonctionnel équivalent de [CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize).  
  
```
HRESULT Initialize() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours S_OK.  
  
### <a name="remarks"></a>Remarques  
 L’implémentation fournie par cette classe ne fait rien.  
  
##  <a name="removehandle"></a>CNoWorkerThread::RemoveHandle  
 Non fonctionnel équivalent de [CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle).  
  
```
HRESULT RemoveHandle(HANDLE /* hObject
 */) throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours S_OK.  
  
### <a name="remarks"></a>Notes  
 L’implémentation fournie par cette classe ne fait rien.  
  
##  <a name="shutdown"></a>CNoWorkerThread::Shutdown  
 Non fonctionnel équivalent de [CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown).  
  
```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours S_OK.  
  
### <a name="remarks"></a>Notes  
 L’implémentation fournie par cette classe ne fait rien.

