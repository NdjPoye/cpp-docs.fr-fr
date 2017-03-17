---
title: Classe de IRunnableObjectImpl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl::GetRunningClass
- ATLCTL/ATL::IRunnableObjectImpl::IsRunning
- ATLCTL/ATL::IRunnableObjectImpl::LockRunning
- ATLCTL/ATL::IRunnableObjectImpl::Run
- ATLCTL/ATL::IRunnableObjectImpl::SetContainedObject
dev_langs:
- C++
helpviewer_keywords:
- containers, running controls
- IRunnableObjectImpl class
- IRunnableObject, ATL implementation
- controls [ATL], running
- controls [C++], container running in ATL
ms.assetid: 305c7c3b-889e-49dd-aca1-34379c1b9931
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: a9b2698c195ac5bd709e6d40d3c30008d3fa26d4
ms.lasthandoff: 02/24/2017

---
# <a name="irunnableobjectimpl-class"></a>IRunnableObjectImpl (classe)
Cette classe implémente **IUnknown** et fournit une implémentation par défaut de la [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) interface.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class T>  
class IRunnableObjectImpl
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Votre classe, dérivée de `IRunnableObjectImpl`.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[IRunnableObjectImpl::GetRunningClass](#getrunningclass)|Retourne le CLSID du contrôle en cours d’exécution. L’implémentation ATL définit le CLSID `GUID_NULL` et retourne **E_UNEXPECTED**.|  
|[IRunnableObjectImpl::IsRunning](#isrunning)|Détermine si le contrôle est en cours d’exécution. Retourne l’implémentation ATL **TRUE**.|  
|[IRunnableObjectImpl::LockRunning](#lockrunning)|Verrouille le contrôle à l’état en cours d’exécution. Retourne l’implémentation ATL `S_OK`.|  
|[IRunnableObjectImpl::Run](#run)|Force le contrôle à exécuter. Retourne l’implémentation ATL `S_OK`.|  
|[IRunnableObjectImpl::SetContainedObject](#setcontainedobject)|Indique que le contrôle est incorporé. Retourne l’implémentation ATL `S_OK`.|  
  
## <a name="remarks"></a>Remarques  
 Le [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) interface permet à un conteneur déterminer si un contrôle est en cours d’exécution, le forcer à exécuter ou mettez-le à l’état en cours d’exécution. Classe `IRunnableObjectImpl` fournit une implémentation par défaut de cette interface et implémente **IUnknown** en envoyant des informations de dump génère l’appareil en mode de débogage.  
  
 **Articles connexes** [didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [création d’un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `IRunnableObject`  
  
 `IRunnableObjectImpl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlctl.h  
  
##  <a name="getrunningclass"></a>IRunnableObjectImpl::GetRunningClass  
 Retourne le CLSID du contrôle en cours d’exécution.  
  
```
HRESULT GetRunningClass(LPCLSID lpClsid);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Les jeux d’implémentation ATL \* *lpClsid* à `GUID_NULL` et retourne **E_UNEXPECTED**.  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IRunnableObject::GetRunningClass](http://msdn.microsoft.com/library/windows/desktop/ms693734) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="isrunning"></a>IRunnableObjectImpl::IsRunning  
 Détermine si le contrôle est en cours d’exécution.  
  
```
virtual BOOL IsRunning();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’implémentation ATL **TRUE**.  
  
### <a name="remarks"></a>Notes  
 Consultez la page [IRunnableObject::IsRunning](http://msdn.microsoft.com/library/windows/desktop/ms678496) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="lockrunning"></a>IRunnableObjectImpl::LockRunning  
 Verrouille le contrôle à l’état en cours d’exécution.  
  
```
HRESULT LockRunning(BOOL fLock, BOOL fLastUnlockCloses);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’implémentation ATL `S_OK`.  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IRunnableObject::LockRunning](http://msdn.microsoft.com/library/windows/desktop/ms693361) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="run"></a>IRunnableObjectImpl::Run  
 Force le contrôle à exécuter.  
  
```
HRESULT Run(LPBINDCTX lpbc);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’implémentation ATL `S_OK`.  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IRunnableObject::Run](http://msdn.microsoft.com/library/windows/desktop/ms694517) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setcontainedobject"></a>IRunnableObjectImpl::SetContainedObject  
 Indique que le contrôle est incorporé.  
  
```
HRESULT SetContainedObject(BOOL fContained);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’implémentation ATL `S_OK`.  
  
### <a name="remarks"></a>Notes  
 Consultez la page [IRunnableObject::SetContainedObject](http://msdn.microsoft.com/library/windows/desktop/ms693710) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [CComControl (classe)](../../atl/reference/ccomcontrol-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

