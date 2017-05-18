---
title: Classe de IOleControlImpl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IOleControlImpl
- ATLCTL/ATL::IOleControlImpl
- ATLCTL/ATL::IOleControlImpl::FreezeEvents
- ATLCTL/ATL::IOleControlImpl::GetControlInfo
- ATLCTL/ATL::IOleControlImpl::OnAmbientPropertyChange
- ATLCTL/ATL::IOleControlImpl::OnMnemonic
dev_langs:
- C++
helpviewer_keywords:
- IOleControlImpl class
ms.assetid: 5a4255ad-ede4-49ca-ba9a-07c2e919fa85
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5e63849a504b931de30141dd91af557f16c67fd8
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="iolecontrolimpl-class"></a>IOleControlImpl (classe)
Cette classe fournit une implémentation par défaut de la **IOleControl** interface et implémente **IUnknown**.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
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
|[IOleControlImpl::FreezeEvents](#freezeevents)|Indique si le conteneur ignore ou accepte les événements du contrôle.|  
|[IOleControlImpl::GetControlInfo](#getcontrolinfo)|Remplit les informations sur le comportement du clavier du contrôle. Retourne l’implémentation ATL **E_NOTIMPL**.|  
|[IOleControlImpl::OnAmbientPropertyChange](#onambientpropertychange)|Indique un contrôle qu’un ou plusieurs des propriétés ambiantes du conteneur a changé. Retourne l’implémentation ATL `S_OK`.|  
|[IOleControlImpl::OnMnemonic](#onmnemonic)|Indique au contrôle qu’un utilisateur a appuyé sur une combinaison de touches spécifiée. Retourne l’implémentation ATL **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Remarques  
 Classe `IOleControlImpl` fournit une implémentation par défaut de la [IOleControl](http://msdn.microsoft.com/library/windows/desktop/ms694320) interface et implémente **IUnknown** en envoyant des informations de dump génère l’appareil en mode de débogage.  
  
 **Articles connexes** [didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [création d’un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `IOleControl`  
  
 `IOleControlImpl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlctl.h  
  
##  <a name="freezeevents"></a>IOleControlImpl::FreezeEvents  
 Dans l’implémentation d’ATL, `FreezeEvents` incrémente la classe de contrôle `m_nFreezeEvents` membre de données si `bFreeze` est **TRUE**et décrémente `m_nFreezeEvents` si `bFreeze` est **FALSE**.  
  
```
HRESULT FreezeEvents(BOOL bFreeze);
```  
  
### <a name="remarks"></a>Notes  
 `FreezeEvents`puis le renvoie `S_OK`.  
  
 Consultez la page [IOleControl::FreezeEvents](http://msdn.microsoft.com/library/windows/desktop/ms678482) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getcontrolinfo"></a>IOleControlImpl::GetControlInfo  
 Remplit les informations sur le comportement du clavier du contrôle.  
  
```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IOleControl:GetControlInfo](http://msdn.microsoft.com/library/windows/desktop/ms693730) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
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
 Consultez la page [IOleControl::OnAmbientPropertyChange](http://msdn.microsoft.com/library/windows/desktop/ms690175) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onmnemonic"></a>IOleControlImpl::OnMnemonic  
 Indique au contrôle qu’un utilisateur a appuyé sur une combinaison de touches spécifiée.  
  
```
HRESULT OnMnemonic(LPMSG pMsg);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **E_NOTIMPL**.  
  
### <a name="remarks"></a>Notes  
 Consultez la page [IOleControl::OnMnemonic](http://msdn.microsoft.com/library/windows/desktop/ms680699) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [IOleObjectImpl (classe)](../../atl/reference/ioleobjectimpl-class.md)   
 [Interfaces de contrôles ActiveX](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

