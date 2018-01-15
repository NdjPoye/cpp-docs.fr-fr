---
title: "Interface de l’interface IThreadPoolConfig | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IThreadPoolConfig
- ATLUTIL/ATL::IThreadPoolConfig
- ATLUTIL/ATL::GetSize
- ATLUTIL/ATL::GetTimeout
- ATLUTIL/ATL::SetSize
- ATLUTIL/ATL::SetTimeout
dev_langs: C++
helpviewer_keywords: IThreadPoolConfig interface
ms.assetid: 69e642bf-6925-46e6-9a37-cce52231b1cc
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d967720778305eace4eff9ad8b2163456fb4bb46
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ithreadpoolconfig-interface"></a>Interface de l’interface IThreadPoolConfig
Cette interface fournit des méthodes pour la configuration d’un pool de threads.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
__interface
    __declspec(uuid("B1F64757-6E88-4fa2-8886-7848B0D7E660")) IThreadPoolConfig : public IUnknown
```  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[GetSize](#getsize)|Appelez cette méthode pour obtenir le nombre de threads dans le pool.|  
|[GetTimeout](#gettimeout)|Appelez cette méthode pour obtenir le temps maximal en millisecondes d’attente du pool de threads d’un thread pour l’arrêter.|  
|[SetSize](#setsize)|Appelez cette méthode pour définir le nombre de threads dans le pool.|  
|[SetTimeout](#settimeout)|Appelez cette méthode pour définir le délai maximal en millisecondes d’attente du pool de threads d’un thread pour l’arrêter.|  
  
## <a name="remarks"></a>Notes  
 Cette interface est implémentée par [CThreadPool](../../atl/reference/cthreadpool-class.md).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atlutil.h  
  
##  <a name="getsize"></a>IThreadPoolConfig::GetSize  
 Appelez cette méthode pour obtenir le nombre de threads dans le pool.  
  
```
STDMETHOD(GetSize)(int* pnNumThreads);
```  
  
### <a name="parameters"></a>Paramètres  
 `pnNumThreads`  
 [out] Adresse de la variable qui, en cas de réussite, reçoit le nombre de threads dans le pool.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/ithreadpoolconfig-interface_1.cpp)]  
  
##  <a name="gettimeout"></a>IThreadPoolConfig::GetTimeout  
 Appelez cette méthode pour obtenir le temps maximal en millisecondes d’attente du pool de threads d’un thread pour l’arrêter.  
  
```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```  
  
### <a name="parameters"></a>Paramètres  
 `pdwMaxWait`  
 [out] Adresse de la variable qui, en cas de réussite, reçoit la durée maximale en millisecondes d’attente du pool de threads d’un thread pour l’arrêter.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="example"></a>Exemple  
 Consultez [IThreadPoolConfig::GetSize](#getsize).  
  
##  <a name="setsize"></a>IThreadPoolConfig::SetSize  
 Appelez cette méthode pour définir le nombre de threads dans le pool.  
  
```
STDMETHOD(SetSize)int nNumThreads);
```  
  
### <a name="parameters"></a>Paramètres  
 `nNumThreads`  
 Le nombre demandé de threads dans le pool.  
  
 Si `nNumThreads` est négatif, sa valeur absolue sera multiplié par le nombre de processeurs sur l’ordinateur pour obtenir le nombre total de threads.  
  
 Si `nNumThreads` est égal à zéro, [ATLS_DEFAULT_THREADSPERPROC](http://msdn.microsoft.com/library/e0dcf107-72a9-4122-abb4-83c63aa7d571) sera multiplié par le nombre de processeurs sur l’ordinateur pour obtenir le nombre total de threads.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="example"></a>Exemple  
 Consultez [IThreadPoolConfig::GetSize](#getsize).  
  
##  <a name="settimeout"></a>IThreadPoolConfig::SetTimeout  
 Appelez cette méthode pour définir le délai maximal en millisecondes d’attente du pool de threads d’un thread pour l’arrêter.  
  
```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwMaxWait`  
 L’heure demandée maximal en millisecondes d’attente du pool de threads d’un thread pour l’arrêter.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="example"></a>Exemple  
 Consultez [IThreadPoolConfig::GetSize](#getsize).  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../atl/reference/atl-classes.md)   
 [CThreadPool, classe](../../atl/reference/cthreadpool-class.md)
