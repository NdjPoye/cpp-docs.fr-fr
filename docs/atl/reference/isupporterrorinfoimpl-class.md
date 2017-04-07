---
title: Classe de ISupportErrorInfoImpl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl::InterfaceSupportsErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- ISupportErrorInfo ATL implementation
- ISupportErrorInfoImpl class
- error information, ATL
ms.assetid: e33a4b11-a123-41cf-bcea-7b19743902af
caps.latest.revision: 23
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
ms.openlocfilehash: 320cb27d1d22a5e4240861c934e9bcfabd731bad
ms.lasthandoff: 02/24/2017

---
# <a name="isupporterrorinfoimpl-class"></a>ISupportErrorInfoImpl (classe)
Cette classe fournit une implémentation par défaut de la [ISupportErrorInfo Interface](http://msdn.microsoft.com/en-us/42d33066-36b4-4a5b-aa5d-46682e560f32) et peut être utilisé lorsque qu’une interface génère des erreurs sur un objet.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<const IID* piid>  
class ATL_NO_VTABLE ISupportErrorInfoImpl 
   : public ISupportErrorInfo
```  
  
#### <a name="parameters"></a>Paramètres  
 `piid`  
 Un pointeur vers l’IID d’une interface qui prend en charge [IErrorInfo](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447).  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](#interfacesupportserrorinfo)|Indique si l’interface est identifié par `riid` prend en charge les [IErrorInfo](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447) interface.|  
  
## <a name="remarks"></a>Remarques  
 Le [ISupportErrorInfo Interface](http://msdn.microsoft.com/en-us/42d33066-36b4-4a5b-aa5d-46682e560f32) garantit que les informations d’erreur peuvent être renvoyées au client. Objets qui utilisent **IErrorInfo** doit implémenter **ISupportErrorInfo**.  
  
 Classe `ISupportErrorInfoImpl` fournit une implémentation par défaut de **ISupportErrorInfo** et peut être utilisé lorsque qu’une interface génère des erreurs sur un objet. Exemple :  
  
 [!code-cpp[NVC_ATL_COM N °&48;](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `ISupportErrorInfo`  
  
 `ISupportErrorInfoImpl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
##  <a name="interfacesupportserrorinfo"></a>ISupportErrorInfoImpl::InterfaceSupportsErrorInfo  
 Indique si l’interface est identifié par `riid` prend en charge les [IErrorInfo](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447) interface.  
  
```
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [ISupportErrorInfo::InterfaceSupportsErrorInfo](http://msdn.microsoft.com/en-us/a54ef18d-ee3f-4483-ac4a-99d758f0960a) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
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
 [!code-cpp[NVC_ATL_Utilities&#134;](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_2.cpp)]  
  
##  <a name="gettimeout"></a>IThreadPoolConfig::GetTimeout  
 Appelez cette méthode pour obtenir le temps maximal en millisecondes d’attente d’un thread arrêter le pool de threads.  
  
```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```  
  
### <a name="parameters"></a>Paramètres  
 `pdwMaxWait`  
 [out] Adresse de la variable qui, en cas de réussite, reçoit le temps maximal en millisecondes d’attente d’un thread arrêter le pool de threads.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="example"></a>Exemple  
 Consultez la page [IThreadPoolConfig::GetSize](#getsize).  
  
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
 Consultez la page [IThreadPoolConfig::GetSize](#getsize).  
  
##  <a name="settimeout"></a>IThreadPoolConfig::SetTimeout  
 Appelez cette méthode pour définir le temps maximal en millisecondes d’attente d’un thread arrêter le pool de threads.  
  
```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwMaxWait`  
 La durée maximale demandée en millisecondes d’attente d’un thread arrêter le pool de threads.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="example"></a>Exemple  
 Consultez la page [IThreadPoolConfig::GetSize](#getsize).  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

