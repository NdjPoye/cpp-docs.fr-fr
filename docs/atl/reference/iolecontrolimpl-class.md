---
title: Classe de IOleControlImpl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IOleControlImpl
- ATLCTL/ATL::IOleControlImpl
- ATLCTL/ATL::IOleControlImpl::FreezeEvents
- ATLCTL/ATL::IOleControlImpl::GetControlInfo
- ATLCTL/ATL::IOleControlImpl::OnAmbientPropertyChange
- ATLCTL/ATL::IOleControlImpl::OnMnemonic
dev_langs: C++
helpviewer_keywords: IOleControlImpl class
ms.assetid: 5a4255ad-ede4-49ca-ba9a-07c2e919fa85
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 23375f8f76e1a58bf29e3e3e269077fea4ae8d61
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="iolecontrolimpl-class"></a>Classe de IOleControlImpl
Cette classe fournit une implémentation par défaut de la **IOleControl** interface et implémente **IUnknown**.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class T>
class IOleControlImpl
```   
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Votre classe, dérivée de `IOleControlImpl`.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[IOleControlImpl::FreezeEvents](#freezeevents)|Indique si le conteneur ignore ou accepte les événements à partir du contrôle.|  
|[IOleControlImpl::GetControlInfo](#getcontrolinfo)|Remplit les informations sur le comportement du contrôle clavier. L’implémentation ATL retourne **E_NOTIMPL**.|  
|[IOleControlImpl::OnAmbientPropertyChange](#onambientpropertychange)|Indique un contrôle qu’un ou plusieurs des propriétés ambiantes du conteneur a changé. L’implémentation ATL retourne `S_OK`.|  
|[IOleControlImpl::OnMnemonic](#onmnemonic)|Informe le contrôle qu’un utilisateur a appuyé sur une séquence de touches spécifiée. L’implémentation ATL retourne **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Notes  
 Classe `IOleControlImpl` fournit une implémentation par défaut de la [IOleControl](http://msdn.microsoft.com/library/windows/desktop/ms694320) interface et implémente **IUnknown** en envoyant des informations pour le vidage de builds périphérique en mode débogage.  
  
 **Articles connexes** [didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [création d’un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `IOleControl`  
  
 `IOleControlImpl`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atlctl.h  
  
##  <a name="freezeevents"></a>IOleControlImpl::FreezeEvents  
 Dans l’implémentation de d’ATL, `FreezeEvents` incrémente la classe de contrôle `m_nFreezeEvents` membre de données si `bFreeze` est **TRUE**et décrémente `m_nFreezeEvents` si `bFreeze` est **FALSE**.  
  
```
HRESULT FreezeEvents(BOOL bFreeze);
```  
  
### <a name="remarks"></a>Notes  
 `FreezeEvents`retourne ensuite `S_OK`.  
  
 Consultez [IOleControl::FreezeEvents](http://msdn.microsoft.com/library/windows/desktop/ms678482) dans le Kit de développement logiciel Windows.  
  
##  <a name="getcontrolinfo"></a>IOleControlImpl::GetControlInfo  
 Remplit les informations sur le comportement du contrôle clavier.  
  
```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```  
  
### <a name="remarks"></a>Notes  
 Consultez [IOleControl:GetControlInfo](http://msdn.microsoft.com/library/windows/desktop/ms693730) dans le Kit de développement logiciel Windows.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **E_NOTIMPL**.  
  
##  <a name="onambientpropertychange"></a>IOleControlImpl::OnAmbientPropertyChange  
 Indique un contrôle qu’un ou plusieurs des propriétés ambiantes du conteneur a changé.  
  
```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `S_OK`.  
  
### <a name="remarks"></a>Notes  
 Consultez [IOleControl::OnAmbientPropertyChange](http://msdn.microsoft.com/library/windows/desktop/ms690175) dans le Kit de développement logiciel Windows.  
  
##  <a name="onmnemonic"></a>IOleControlImpl::OnMnemonic  
 Informe le contrôle qu’un utilisateur a appuyé sur une séquence de touches spécifiée.  
  
```
HRESULT OnMnemonic(LPMSG pMsg);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **E_NOTIMPL**.  
  
### <a name="remarks"></a>Notes  
 Consultez [IOleControl::OnMnemonic](http://msdn.microsoft.com/library/windows/desktop/ms680699) dans le Kit de développement logiciel Windows.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md)   
 [Interfaces de contrôles ActiveX](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
