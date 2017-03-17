---
title: Classe de IViewObjectExImpl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IViewObjectExImpl
- ATLCTL/ATL::IViewObjectExImpl
- ATLCTL/ATL::IViewObjectExImpl::Draw
- ATLCTL/ATL::IViewObjectExImpl::Freeze
- ATLCTL/ATL::IViewObjectExImpl::GetAdvise
- ATLCTL/ATL::IViewObjectExImpl::GetColorSet
- ATLCTL/ATL::IViewObjectExImpl::GetExtent
- ATLCTL/ATL::IViewObjectExImpl::GetNaturalExtent
- ATLCTL/ATL::IViewObjectExImpl::GetRect
- ATLCTL/ATL::IViewObjectExImpl::GetViewStatus
- ATLCTL/ATL::IViewObjectExImpl::QueryHitPoint
- ATLCTL/ATL::IViewObjectExImpl::QueryHitRect
- ATLCTL/ATL::IViewObjectExImpl::SetAdvise
- ATLCTL/ATL::IViewObjectExImpl::Unfreeze
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], drawing
- IViewObjectEx ATL implementation
- advise sinks
- IViewObjectExImpl class
ms.assetid: ad6de760-1ee5-4883-b033-ae57beffc369
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
ms.openlocfilehash: 2b585a056324507cc631e64e6dbe9d0ed610361d
ms.lasthandoff: 02/24/2017

---
# <a name="iviewobjecteximpl-class"></a>IViewObjectExImpl (classe)
Cette classe implémente **IUnknown** et fournit des implémentations par défaut de la [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763), [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318), et [IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375) interfaces.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class T>  
class ATL_NO_VTABLE IViewObjectExImpl 
   : public IViewObjectEx
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Votre classe, dérivée de `IViewObjectExImpl`.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[IViewObjectExImpl::Draw](#draw)|Dessine une représentation du contrôle sur un contexte de périphérique.|  
|[IViewObjectExImpl::Freeze](#freeze)|Fige la représentation sous forme de dessinée d’un contrôle afin qu’il ne changera pas jusqu'à un `Unfreeze`. Retourne l’implémentation ATL **E_NOTIMPL**.|  
|[IViewObjectExImpl::GetAdvise](#getadvise)|Récupère une connexion existante de récepteur de notifications sur le contrôle, le cas échéant.|  
|[IViewObjectExImpl::GetColorSet](#getcolorset)|Retourne la palette logique utilisée par le contrôle de dessin. Retourne l’implémentation ATL **E_NOTIMPL**.|  
|[IViewObjectExImpl::GetExtent](#getextent)|Récupère la taille d’affichage du contrôle en unités HIMETRIC (0,01 millimètre par unité) dans le membre de données de classe de contrôle [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).|  
|[IViewObjectExImpl::GetNaturalExtent](#getnaturalextent)|Fournit des conseils de dimensionnement du conteneur pour l’objet à utiliser lorsque l’utilisateur le redimensionne.|  
|[IViewObjectExImpl::GetRect](#getrect)|Retourne un rectangle décrivant un aspect de dessin demandé. Retourne l’implémentation ATL **E_NOTIMPL**.|  
|[IViewObjectExImpl::GetViewStatus](#getviewstatus)|Retourne des informations relatives à l’opacité de l’objet et les aspects de dessin sont pris en charge.|  
|[IViewObjectExImpl::QueryHitPoint](#queryhitpoint)|Vérifie si le point spécifié se trouve dans le rectangle spécifié et retourne un [HITRESULT](http://msdn.microsoft.com/library/windows/desktop/ms682187) valeur dans `pHitResult`.|  
|[IViewObjectExImpl::QueryHitRect](#queryhitrect)|Vérifie si le rectangle d’affichage du contrôle empiète sur n’importe quel point dans le rectangle de l’emplacement spécifié et retourne un **HITRESULT** valeur dans `pHitResult`.|  
|[IViewObjectExImpl::SetAdvise](#setadvise)|Configure une connexion entre le contrôle et un récepteur de notifications pour le récepteur peut être informé des changements apportés dans l’affichage du contrôle.|  
|[IViewObjectExImpl::Unfreeze](#unfreeze)|Libère la représentation sous forme de dessinée du contrôle. Retourne l’implémentation ATL **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Remarques  
 Le [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763), [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318), et [IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375) interfaces permettent un contrôle à afficher directement et créer et gérer un récepteur de notifications pour notifier au conteneur des modifications dans l’affichage du contrôle. Le **IViewObjectEx** interface prend en charge les fonctionnalités de contrôle étendu telles que le dessin sans scintillement, des contrôles non rectangulaires et transparents et le test de recherche (par exemple, comment fermer un clic de souris doit être considéré sur le contrôle). Classe `IViewObjectExImpl` fournit une implémentation par défaut de ces interfaces et implémente **IUnknown** en envoyant des informations de dump génère l’appareil en mode de débogage.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `IViewObjectEx`  
  
 `IViewObjectExImpl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlctl.h  
  
##  <a name="draw"></a>IViewObjectExImpl::Draw  
 Dessine une représentation du contrôle sur un contexte de périphérique.  
  
```
STDMETHOD(Draw)(
    DWORD dwDrawAspect,
    LONG lindex,
    void* pvAspect,
    DVTARGETDEVICE* ptd,
    HDC hicTargetDev,
    LPCRECTL prcBounds,
    LPCRECTL prcWBounds,
    BOOL(_stdcall* /* pfnContinue*/) (DWORD_PTR dwContinue),
    DWORD_PTR /* dwContinue */);
```  
  
### <a name="remarks"></a>Notes  
 Cette méthode appelle **CComControl::OnDrawAdvanced** qui appelle votre classe de contrôle `OnDraw` (méthode). Un `OnDraw` méthode est automatiquement ajoutée à votre classe de contrôle lorsque vous créez votre contrôle avec l’Assistant contrôle ATL. Par défaut de l’Assistant `OnDraw` Dessine un rectangle avec l’étiquette « ATL 3.0 ».  
  
 Consultez la page [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="freeze"></a>IViewObjectExImpl::Freeze  
 Fige la représentation sous forme de dessinée d’un contrôle afin qu’il ne changera pas jusqu'à un `Unfreeze`. Retourne l’implémentation ATL **E_NOTIMPL**.  
  
```
STDMETHOD(Freeze)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DWORD* /* pdwFreeze */);
```  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IViewObject::Freeze](http://msdn.microsoft.com/library/windows/desktop/ms688728) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getadvise"></a>IViewObjectExImpl::GetAdvise  
 Récupère une connexion existante de récepteur de notifications sur le contrôle, le cas échéant.  
  
```
STDMETHOD(GetAdvise)(
    DWORD* /* pAspects */,
    DWORD* /* pAdvf */,
    IAdviseSink** /* ppAdvSink */);
```  
  
### <a name="remarks"></a>Remarques  
 Le récepteur de notifications est stocké dans le membre de données de classe de contrôle [CComControlBase::m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink).  
  
 Consultez la page [IViewObject::GetAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692772) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getcolorset"></a>IViewObjectExImpl::GetColorSet  
 Retourne la palette logique utilisée par le contrôle de dessin. Retourne l’implémentation ATL **E_NOTIMPL**.  
  
```
STDMETHOD(GetColorSet)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    LOGPALETTE** /* ppColorSet */);
```  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IViewObject::GetColorSet](http://msdn.microsoft.com/library/windows/desktop/ms686553) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getextent"></a>IViewObjectExImpl::GetExtent  
 Récupère la taille d’affichage du contrôle en unités HIMETRIC (0,01 millimètre par unité) dans le membre de données de classe de contrôle [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).  
  
```
STDMETHOD(GetExtent)(
    DWORD /* dwDrawAspect */,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    LPSIZEL* lpsizel);
```  
  
### <a name="remarks"></a>Notes  
 Consultez la page [IViewObject2::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms684032) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getnaturalextent"></a>IViewObjectExImpl::GetNaturalExtent  
 Fournit des conseils de dimensionnement du conteneur pour l’objet à utiliser lorsque l’utilisateur le redimensionne.  
  
```
STDMETHOD(GetNaturalExtent)(
    DWORD dwAspect,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    DVEXTENTINFO* pExtentInfo,
    LPSIZEL psizel);
```  
  
### <a name="remarks"></a>Notes  
 Si `dwAspect` est `DVASPECT_CONTENT` et *pExtentInfo-> dwExtentMode* est **DVEXTENT_CONTENT**, définit * `psizel` au membre de données de la classe control [CComControlBase::m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural). Sinon, retourne une erreur `HRESULT`.  
  
 Consultez la page [IViewObjectEx::GetNaturalExtent](http://msdn.microsoft.com/library/windows/desktop/ms683718) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getrect"></a>IViewObjectExImpl::GetRect  
 Retourne un rectangle décrivant un aspect de dessin demandé. Retourne l’implémentation ATL **E_NOTIMPL**.  
  
```
STDMETHOD(GetRect)(DWORD /* dwAspect */, LPRECTL /* pRect */);
```  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IViewObjectEx::GetRect](http://msdn.microsoft.com/library/windows/desktop/ms695246) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getviewstatus"></a>IViewObjectExImpl::GetViewStatus  
 Retourne des informations relatives à l’opacité de l’objet et les aspects de dessin sont pris en charge.  
  
```
STDMETHOD(GetViewStatus)(DWORD* pdwStatus);
```  
  
### <a name="remarks"></a>Remarques  
 Par défaut, ATL définit `pdwStatus` pour indiquer que le contrôle prend en charge **VIEWSTATUS_OPAQUE** (les valeurs possibles sont dans le [double](http://msdn.microsoft.com/library/windows/desktop/ms687201) énumération).  
  
 Consultez la page [IViewObjectEx::GetViewStatus](http://msdn.microsoft.com/library/windows/desktop/ms693371) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="queryhitpoint"></a>IViewObjectExImpl::QueryHitPoint  
 Vérifie si le point spécifié se trouve dans le rectangle spécifié et retourne un [HITRESULT](http://msdn.microsoft.com/library/windows/desktop/ms682187) valeur dans `pHitResult`.  
  
```
STDMETHOD(QueryHitPoint)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    POINT ptlLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```  
  
### <a name="remarks"></a>Remarques  
 La valeur peut être **HITRESULT_HIT** ou **HITRESULT_OUTSIDE**.  
  
 Si `dwAspect` est égal à [DVASPECT_CONTENT](http://msdn.microsoft.com/library/windows/desktop/ms690318), la méthode retourne `S_OK`. Dans le cas contraire, la méthode retourne **E_FAIL**.  
  
 Consultez la page [IViewObjectEx::QueryHitPoint](http://msdn.microsoft.com/library/windows/desktop/ms691209) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="queryhitrect"></a>IViewObjectExImpl::QueryHitRect  
 Vérifie si le rectangle d’affichage du contrôle empiète sur n’importe quel point dans le rectangle de l’emplacement spécifié et retourne un [HITRESULT](http://msdn.microsoft.com/library/windows/desktop/ms682187) valeur dans `pHitResult`.  
  
```
STDMETHOD(QueryHitRect)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    LPRECT prcLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```  
  
### <a name="remarks"></a>Remarques  
 La valeur peut être **HITRESULT_HIT** ou **HITRESULT_OUTSIDE**.  
  
 Si `dwAspect` est égal à [DVASPECT_CONTENT](http://msdn.microsoft.com/library/windows/desktop/ms690318), la méthode retourne `S_OK`. Dans le cas contraire, la méthode retourne **E_FAIL**.  
  
 Consultez la page [IViewObjectEx::QueryHitRect](http://msdn.microsoft.com/library/windows/desktop/ms693797) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setadvise"></a>IViewObjectExImpl::SetAdvise  
 Configure une connexion entre le contrôle et un récepteur de notifications pour le récepteur peut être informé des changements apportés dans l’affichage du contrôle.  
  
```
STDMETHOD(SetAdvise)(
    DWORD /* aspects */,
    DWORD /* advf */,
    IAdviseSink* pAdvSink);
```  
  
### <a name="remarks"></a>Remarques  

 Le pointeur vers le [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) interface sur le récepteur de notifications est stocké dans le membre de données de classe de contrôle [CComControlBase::m_spAdviseSink](ccomcontrolbase-class.md#m_spadvisesink).  

  
 Consultez la page [IViewObject::SetAdvise](http://msdn.microsoft.com/library/windows/desktop/ms683950) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="unfreeze"></a>IViewObjectExImpl::Unfreeze  
 Libère la représentation sous forme de dessinée du contrôle. Retourne l’implémentation ATL **E_NOTIMPL**.  
  
```
STDMETHOD(Unfreeze)(DWORD /* dwFreeze */);
```  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [IViewObject::Unfreeze](http://msdn.microsoft.com/library/windows/desktop/ms686641) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="closehandle"></a>IWorkerThreadClient::CloseHandle  
 Implémentez cette méthode pour fermer le handle associé à cet objet.  
  
```
HRESULT CloseHandle(HANDLE hHandle);
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
  
 [!code-cpp[NVC_ATL_Utilities&#135;](../../atl/codesnippet/cpp/iviewobjecteximpl-class_1.cpp)]  
  
##  <a name="execute"></a>IWorkerThreadClient::Execute  
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
  
### <a name="remarks"></a>Remarques  
 Le handle et DWORD/pointeur passé à cette méthode ont été précédemment associé à cet objet par un appel à [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Exemple  
 Le code suivant montre une implémentation simple de `IWorkerThreadClient::Execute`.  
  
 [!code-cpp[NVC_ATL_Utilities&#136;](../../atl/codesnippet/cpp/iviewobjecteximpl-class_2.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [CComControl (classe)](../../atl/reference/ccomcontrol-class.md)   
 [Interfaces de contrôles ActiveX](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Didacticiel](../../atl/active-template-library-atl-tutorial.md)   
 [Création d’un projet ATL](../../atl/reference/creating-an-atl-project.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

