---
title: Interface de IWorkerThreadClient | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.IWorkerThreadClient
- ATL::IWorkerThreadClient
- IWorkerThreadClient
dev_langs:
- C++
helpviewer_keywords:
- IWorkerThreadClient interface
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
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
ms.openlocfilehash: 2127d13dc11edb353ef27396f3457dd9abdc4a99
ms.lasthandoff: 02/24/2017

---
# <a name="iworkerthreadclient-interface"></a>Interface de IWorkerThreadClient
`IWorkerThreadClient`est l’interface implémentée par les clients de la [CWorkerThread](../../atl/reference/cworkerthread-class.md) classe.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```
__interface IWorkerThreadClient
```  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[CloseHandle](#closehandle)|Implémentez cette méthode pour fermer le handle associé à cet objet.|  
|[Exécuter](#execute)|Implémentez cette méthode pour exécuter du code lorsque le handle associé à cet objet soit signalé.|  
  
## <a name="remarks"></a>Remarques  
 Implémentez cette interface lorsque vous avez du code qui doit s’exécuter sur un thread de travail en réponse à un handle ne soit signalé.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlutil.h  
  
##  <a name="a-nameclosehandlea--iworkerthreadclientclosehandle"></a><a name="closehandle"></a>IWorkerThreadClient::CloseHandle  
 Implémentez cette méthode pour fermer le handle associé à cet objet.  
  
```
HRESULT CloseHandle(HANDLE  hHandle);
```  
  
### <a name="parameters"></a>Paramètres  
 *hHandle*  
 Le handle est fermé.  
  
### <a name="return-value"></a>Valeur de retour  
 Sur la réussite ou une erreur HRESULT en cas d’échec, retourne S_OK.  
  
### <a name="remarks"></a>Remarques  
 Le handle passé à cette méthode a été précédemment associé à cet objet par un appel à [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Exemple  
 Le code suivant montre une implémentation simple de `IWorkerThreadClient::CloseHandle`.  
  
 [!code-cpp[NVC_ATL_Utilities&#135;](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]  
  
##  <a name="a-nameexecutea--iworkerthreadclientexecute"></a><a name="execute"></a>IWorkerThreadClient::Execute  
 Implémentez cette méthode pour exécuter du code lorsque le handle associé à cet objet soit signalé.  
  
```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwParam`  
 Le paramètre user.  
  
 `hObject`  
 Le handle a été signalé.  
  
### <a name="return-value"></a>Valeur de retour  
 Sur la réussite ou une erreur HRESULT en cas d’échec, retourne S_OK.  
  
### <a name="remarks"></a>Notes  
 Le handle et DWORD/pointeur passé à cette méthode ont été précédemment associé à cet objet par un appel à [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Exemple  
 Le code suivant montre une implémentation simple de `IWorkerThreadClient::Execute`.  
  
 [!code-cpp[NVC_ATL_Utilities&#136;](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../atl/reference/atl-classes.md)   
 [Classe CWorkerThread](../../atl/reference/cworkerthread-class.md)

