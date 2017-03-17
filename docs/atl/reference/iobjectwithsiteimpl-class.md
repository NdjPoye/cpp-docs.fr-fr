---
title: "Classe d’IObjectWithSiteImpl de prendre facilement | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl::GetSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetChildSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetSite
- ATLCOM/ATL::IObjectWithSiteImpl::m_spUnkSite
dev_langs:
- C++
helpviewer_keywords:
- IObjectWithSiteImpl class
ms.assetid: 4e1f774f-bc3d-45ee-9a1c-c3533a511588
caps.latest.revision: 18
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
ms.openlocfilehash: 49c52810417650c3d80fe4d0c09ccb2b67208ad4
ms.lasthandoff: 02/24/2017

---
# <a name="iobjectwithsiteimpl-class"></a>IObjectWithSiteImpl de prendre facilement (classe)
Cette classe fournit des méthodes permettant d’objet communiquer avec son site.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T>
    class ATL_NO_VTABLE IObjectWithSiteImpl :
    public IObjectWithSite
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Votre classe, dérivée de `IObjectWithSiteImpl`.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[IObjectWithSiteImpl::GetSite](#getsite)|Interroge le site d’un pointeur d’interface.|  
|[IObjectWithSiteImpl::SetChildSite](#setchildsite)|Fournit l’objet du site **IUnknown** pointeur.|  
|[IObjectWithSiteImpl::SetSite](#setsite)|Fournit l’objet du site **IUnknown** pointeur.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[IObjectWithSiteImpl::m_spUnkSite](#m_spunksite)|Gestion du site **IUnknown** pointeur.|  
  
## <a name="remarks"></a>Remarques  
 Le [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) interface permet à un objet communiquer avec son site. Classe `IObjectWithSiteImpl` fournit une implémentation par défaut de cette interface et implémente **IUnknown** en envoyant des informations de dump génère l’appareil en mode de débogage.  
  
 `IObjectWithSiteImpl`Spécifie les deux méthodes. Le client appelle d’abord `SetSite`, en passant du site **IUnknown** pointeur. Ce pointeur est stocké dans l’objet et peuvent être récupéré ultérieurement via un appel à `GetSite`.  
  
 En règle générale, vous dérivez votre classe de `IObjectWithSiteImpl` lorsque vous créez un objet qui n’est pas un contrôle. Pour les contrôles, dérivez votre classe de [IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md), qui fournit également un pointeur de site. Ne dérivent pas de votre classe de deux `IObjectWithSiteImpl` et `IOleObjectImpl`.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `IObjectWithSite`  
  
 `IObjectWithSiteImpl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
##  <a name="getsite"></a>IObjectWithSiteImpl::GetSite  
 Interroge le site d’un pointeur vers l’interface identifié par `riid`.  
  
```
STDMETHOD(GetSite)(
    REFIID riid,
    void** ppvSite);
```  
  
### <a name="remarks"></a>Remarques  
 Si le site prend en charge cette interface, le pointeur est retourné `ppvSite`. Dans le cas contraire, `ppvSite` a **NULL**.  
  
 Consultez la page [IObjectWithSite::GetSite](http://msdn.microsoft.com/library/windows/desktop/ms694452) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="m_spunksite"></a>IObjectWithSiteImpl::m_spUnkSite  
 Gestion du site **IUnknown** pointeur.  
  
```
CComPtr<IUnknown> m_spUnkSite;
```  
  
### <a name="remarks"></a>Remarques  
 `m_spUnkSite`reçoit le pointeur this via un appel à [SetSite](#setsite).  
  
##  <a name="setchildsite"></a>IObjectWithSiteImpl::SetChildSite  
 Fournit l’objet du site **IUnknown** pointeur.  
  
```
HRESULT SetChildSite(IUnknown* pUnkSite);
```  
  
### <a name="parameters"></a>Paramètres  
 *pUnkSite*  
 [in] Pointeur vers le **IUnknown** pointeur d’interface du site de gestion de cet objet. Si la valeur NULL, l’objet doit appeler `IUnknown::Release` sur n’importe quel site existant à partir duquel l’objet n’est plus sait que son site.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `S_OK`.  
  
##  <a name="setsite"></a>IObjectWithSiteImpl::SetSite  
 Fournit l’objet du site **IUnknown** pointeur.  
  
```
STDMETHOD(SetSite)(IUnknown* pUnkSite);
```  
  
### <a name="remarks"></a>Notes  
 Consultez la page [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

