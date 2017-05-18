---
title: Classe de IConnectionPointImpl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl::Advise
- ATLCOM/ATL::IConnectionPointImpl::EnumConnections
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionInterface
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionPointContainer
- ATLCOM/ATL::IConnectionPointImpl::Unadvise
- ATLCOM/ATL::IConnectionPointImpl::m_vec
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], implementing
- IConnectionPointImpl class
ms.assetid: 27992115-3b86-45dd-bc9e-54f32876c557
caps.latest.revision: 19
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: c9788496bbed3734b959d0ab4c49c89a176ea199
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="iconnectionpointimpl-class"></a>Classe de IConnectionPointImpl
Cette classe implémente un point de connexion.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class T, const IID* piid, class CDV = CComDynamicUnkArray>  
class ATL_NO_VTABLE IConnectionPointImpl : public _ICPLocator<piid>
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Votre classe, dérivée de `IConnectionPointImpl`.  
  
 `piid`  
 Pointeur vers l’IID de l’interface représentée par l’objet de point de connexion.  
  
 `CDV`  
 Une classe qui gère les connexions. La valeur par défaut est [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), ce qui permet un nombre illimité de connexions. Vous pouvez également utiliser [CComUnkArray](../../atl/reference/ccomunkarray-class.md), qui spécifie un nombre fixe de connexions.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[IConnectionPointImpl::Advise](#advise)|Établit une connexion entre le point de connexion et un récepteur.|  
|[IConnectionPointImpl::EnumConnections](#enumconnections)|Crée un énumérateur pour itérer sur les connexions pour le point de connexion.|  
|[IConnectionPointImpl::GetConnectionInterface](#getconnectioninterface)|Récupère l’IID de l’interface représentée par le point de connexion.|  
|[IConnectionPointImpl::GetConnectionPointContainer](#getconnectionpointcontainer)|Récupère un pointeur d’interface vers l’objet connectable.|  
|[IConnectionPointImpl::Unadvise](#unadvise)|Met fin à une connexion précédemment établie par `Advise`.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[IConnectionPointImpl::m_vec](#m_vec)|Gère les connexions pour le point de connexion.|  
  
## <a name="remarks"></a>Remarques  
 `IConnectionPointImpl`implémente un point de connexion, ce qui permet à un objet d’exposer une interface sortante au client. Le client implémente cette interface sur un objet appelé récepteur.  
  
 ATL utilise [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) pour implémenter l’objet connectable. Chaque point de connexion dans l’objet connectable représente une interface sortante, identifiée par `piid`. Classe *CDV* gère les connexions entre le point de connexion et un récepteur. Chaque connexion est identifiée par un « cookie ».  
  
 Pour plus d’informations sur l’utilisation de points de connexion dans ATL, consultez l’article [Points de connexion](../../atl/atl-connection-points.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `_ICPLocator`  
  
 `IConnectionPointImpl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
##  <a name="advise"></a>IConnectionPointImpl::Advise  
 Établit une connexion entre le point de connexion et un récepteur.  
  
```
STDMETHOD(Advise)(
    IUnknown* pUnkSink,
    DWORD* pdwCookie);
```  
  
### <a name="remarks"></a>Remarques  
 Utilisez [Unadvise](#unadvise) pour mettre fin à l’appel de connexion.  
  
 Consultez la page [IConnectionPoint::Advise](http://msdn.microsoft.com/library/windows/desktop/ms678815) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="enumconnections"></a>IConnectionPointImpl::EnumConnections  
 Crée un énumérateur pour itérer sur les connexions pour le point de connexion.  
  
```
STDMETHOD(EnumConnections)(IEnumConnections** ppEnum);
```  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IConnectionPoint::EnumConnections](http://msdn.microsoft.com/library/windows/desktop/ms680755) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getconnectioninterface"></a>IConnectionPointImpl::GetConnectionInterface  
 Récupère l’IID de l’interface représentée par le point de connexion.  
  
```
STDMETHOD(GetConnectionInterface)(IID* piid2);
```  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IConnectionPoint::GetConnectionInterface](http://msdn.microsoft.com/library/windows/desktop/ms693468) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getconnectionpointcontainer"></a>IConnectionPointImpl::GetConnectionPointContainer  
 Récupère un pointeur d’interface vers l’objet connectable.  
  
```
STDMETHOD(GetConnectionPointContainer)(IConnectionPointContainer** ppCPC);
```  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IConnectionPoint::GetConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms679669) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="m_vec"></a>IConnectionPointImpl::m_vec  
 Gère les connexions entre l’objet point de connexion et un récepteur.  
  
```
CDV m_vec;
```     
  
### <a name="remarks"></a>Remarques  
 Par défaut, `m_vec` est de type [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md).  
  
##  <a name="unadvise"></a>IConnectionPointImpl::Unadvise  
 Met fin à une connexion précédemment établie par [Advise](#advise).  
  
```
STDMETHOD(Unadvise)(DWORD dwCookie);
```  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IConnectionPoint::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms686608) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

