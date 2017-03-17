---
title: Classe de IOleInPlaceObjectWindowlessImpl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetDropTarget
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::OnWindowMessage
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::SetObjectRects
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::UIDeactivate
dev_langs:
- C++
helpviewer_keywords:
- IOleInPlaceObjectWindowless, ATL implementation
- activation [C++], ATL
- IOleInPlaceObjectWindowlessImpl class
- ActiveX controls [C++], communication between container and control
- controls [ATL], windowless
- deactivating ATL
ms.assetid: a2e0feb4-bc59-4adf-aab2-105457bbdbb4
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 06ce03a896c9948bff14b4f91ae48000d07c3edd
ms.lasthandoff: 02/24/2017

---
# <a name="ioleinplaceobjectwindowlessimpl-class"></a>IOleInPlaceObjectWindowlessImpl (classe)
Cette classe implémente **IUnknown** et fournit des méthodes qui permettent à un contrôle sans fenêtre pour recevoir des messages de fenêtre et participer aux opérations de glisser-déplacer.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class T>
class IOleInPlaceObjectWindowlessImpl
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Votre classe, dérivée de `IOleInPlaceObjectWindowlessImpl`.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp](#contextsensitivehelp)|Permet à l’aide contextuelle. Retourne l’implémentation ATL **E_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::GetDropTarget](#getdroptarget)|Fournit le `IDropTarget` interface pour un objet sur place actif, sans fenêtre qui prend en charge glisser -déplacer. Retourne l’implémentation ATL **E_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::GetWindow](#getwindow)|Obtient un handle de fenêtre.|  
|[IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate](#inplacedeactivate)|Désactive l’actif d’un contrôle sur place.|  
|[IOleInPlaceObjectWindowlessImpl::OnWindowMessage](#onwindowmessage)|Distribue un message à partir du conteneur à un contrôle sans fenêtre est actif sur place.|  
|[IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo](#reactivateandundo)|Réactive un contrôle précédemment désactivé. Retourne l’implémentation ATL **E_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::SetObjectRects](#setobjectrects)|Indique quelle partie du contrôle sur place est visible.|  
|[IOleInPlaceObjectWindowlessImpl::UIDeactivate](#uideactivate)|Désactive et supprime l’interface utilisateur qui prend en charge l’activation sur place.|  
  
## <a name="remarks"></a>Remarques  
 Le [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) interface gère la réactivation la désactivation de la place les contrôles et détermine la quantité du contrôle doit être visible. Le [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304) interface permet à un contrôle sans fenêtre pour recevoir des messages de fenêtre et participer aux opérations de glisser-déplacer. Classe `IOleInPlaceObjectWindowlessImpl` fournit une implémentation par défaut de `IOleInPlaceObject` et `IOleInPlaceObjectWindowless` et implémente **IUnknown** en envoyant des informations de dump génère l’appareil en mode de débogage.  
  
 **Articles connexes** [didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [création d’un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `IOleInPlaceObjectWindowless`  
  
 `IOleInPlaceObjectWindowlessImpl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlctl.h  
  
##  <a name="contextsensitivehelp"></a>IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp  
 Retourne **E_NOTIMPL**.  
  
```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```  
  
### <a name="remarks"></a>Notes  
 Consultez la page [IOleWindow::ContextSensitiveHelp](http://msdn.microsoft.com/library/windows/desktop/ms680059) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getdroptarget"></a>IOleInPlaceObjectWindowlessImpl::GetDropTarget  
 Retourne **E_NOTIMPL**.  
  
```
HRESULT GetDropTarget(IDropTarget** ppDropTarget);
```  
  
### <a name="remarks"></a>Notes  
 Consultez la page [IOleInPlaceObjectWindowless::GetDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms678535) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getwindow"></a>IOleInPlaceObjectWindowlessImpl::GetWindow  
 Le conteneur appelle cette fonction pour obtenir le handle de fenêtre du contrôle.  
  
```
HRESULT GetWindow(HWND* phwnd);
```  
  
### <a name="remarks"></a>Remarques  
 Certains conteneurs ne fonctionnera pas avec un contrôle qui a été sans fenêtre, même si elle est actuellement fenêtré. Dans l’implémentation d’ATL, si membre de données de la classe control `m_bWasOnceWindowless` est **TRUE**, la fonction retourne **E_FAIL**. Sinon, si *phwnd* n’est pas **NULL**, `GetWindow` définit \* *phwnd* au membre de données de la classe control `m_hWnd` et retourne `S_OK`.  
  
 Consultez la page [IOleWindow::GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms687282) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="inplacedeactivate"></a>IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate  
 Appelée par le conteneur pour désactiver un contrôle actif sur place.  
  
```
HRESULT InPlaceDeactivate(HWND* phwnd);
```  
  
### <a name="remarks"></a>Remarques  
 Cette méthode effectue une désactivation complète ou partielle selon l’état du contrôle. Si nécessaire, l’interface utilisateur du contrôle est désactivé, et la fenêtre de contrôle, le cas échéant, est détruite. Le conteneur est averti que le contrôle n’est plus actif en place. Le **IOleInPlaceUIWindow** interface utilisée par le conteneur pour négocier des menus et de bordure d’espace est libéré.  
  
 Consultez la page [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onwindowmessage"></a>IOleInPlaceObjectWindowlessImpl::OnWindowMessage  
 Distribue un message à partir d’un conteneur à un contrôle sans fenêtre est actif sur place.  
  
```
HRESULT OnWindowMessage(
    UINT msg,
    WPARAM WParam,
    LPARAM LParam,
    LRESULT plResultParam);
```  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IOleInPlaceObjectWindowless::OnWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms693783) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="reactivateandundo"></a>IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo  
 Retourne **E_NOTIMPL**.  
  
```
HRESULT ReactivateAndUndo();
```  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IOleInPlaceObject::ReactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms691372) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setobjectrects"></a>IOleInPlaceObjectWindowlessImpl::SetObjectRects  
 Appelée par le conteneur pour informer le contrôle que sa taille et/ou la position a changé.  
  
```
HRESULT SetObjectRects(LPCRECT prcPos, LPCRECT prcClip);
```  
  
### <a name="remarks"></a>Notes  
 Mises à jour du contrôle `m_rcPos` membre de données et l’affichage du contrôle. Seule la partie du contrôle qui entre en intersection avec la zone de découpage est affichée. Si l’affichage d’un contrôle a été attachée précédemment, mais la capture a été supprimée, cette fonction peut être appelée pour redessiner une vue complète du contrôle.  
  
 Consultez la page [IOleInPlaceObject::SetObjectRects](http://msdn.microsoft.com/library/windows/desktop/ms683767) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="uideactivate"></a>IOleInPlaceObjectWindowlessImpl::UIDeactivate  
 Désactive et supprime l’interface utilisateur du contrôle qui prend en charge l’activation sur place.  
  
```
HRESULT UIDeactivate();
```  
  
### <a name="remarks"></a>Remarques  
 Définit le membre de données de la classe control `m_bUIActive` à **FALSE**. L’implémentation ATL de cette fonction toujours renvoie `S_OK`.  
  
 Consultez la page [IOleInPlaceObject::UIDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms693348) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [CComControl (classe)](../../atl/reference/ccomcontrol-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

