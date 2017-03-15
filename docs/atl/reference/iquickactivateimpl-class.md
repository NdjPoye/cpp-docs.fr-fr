---
title: Classe de IQuickActivateImpl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::IQuickActivateImpl
- ATL::IQuickActivateImpl<T>
- ATL.IQuickActivateImpl
- ATL.IQuickActivateImpl<T>
- IQuickActivateImpl
dev_langs:
- C++
helpviewer_keywords:
- activating ATL controls
- controls [ATL], activating
- IQuickActivateImpl class
- IQuickActivate ATL implementation
ms.assetid: aa80c056-1041-494e-b21d-2acca7dc27ea
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
ms.openlocfilehash: 4f6b75da64efa12e43fa160c57da4291acae03ca
ms.lasthandoff: 02/24/2017

---
# <a name="iquickactivateimpl-class"></a>IQuickActivateImpl (classe)
Cette classe associe l’initialisation du contrôle de conteneurs en un seul appel.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T>  
class ATL_NO_VTABLE IQuickActivateImpl : public IQuickActivate
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Votre classe, dérivée de `IQuickActivateImpl`.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[IQuickActivateImpl::GetContentExtent](#getcontentextent)|Récupère la taille d’affichage actuel pour un contrôle en cours d’exécution.|  
|[IQuickActivateImpl::QuickActivate](#quickactivate)|Effectue une initialisation des contrôles en cours de chargement rapide.|  
|[IQuickActivateImpl::SetContentExtent](#setcontentextent)|Indique au contrôle de la quantité d’espace complet le conteneur a affecté à celle-ci.|  
  
## <a name="remarks"></a>Remarques  
 Le [IQuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms690146) interface permet d’éviter les retards lors du chargement de contrôles en combinant l’initialisation dans un seul appel conteneurs. Le `QuickActivate` méthode permet au conteneur de passer un pointeur vers un [QACONTAINER](http://msdn.microsoft.com/library/windows/desktop/ms688630) structure qui conserve des pointeurs vers toutes les interfaces de contrôle a besoin. Au retour, le contrôle passe à nouveau un pointeur vers un [QACONTROL](http://msdn.microsoft.com/library/windows/desktop/ms693721) structure qui conserve des pointeurs vers ses propres interfaces, qui sont utilisées par le conteneur. Classe `IQuickActivateImpl` fournit une implémentation par défaut de **IQuickActivate** et implémente **IUnknown** en envoyant des informations de dump génère l’appareil en mode de débogage.  
  
 **Articles connexes** [didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [création d’un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `IQuickActivate`  
  
 `IQuickActivateImpl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlctl.h  
  
##  <a name="a-namegetcontentextenta--iquickactivateimplgetcontentextent"></a><a name="getcontentextent"></a>IQuickActivateImpl::GetContentExtent  
 Récupère la taille d’affichage actuel pour un contrôle en cours d’exécution.  
  
```
STDMETHOD(GetContentExtent)(LPSIZEL pSize);
```  
  
### <a name="remarks"></a>Remarques  
 La taille est pour un rendu complet du contrôle et est spécifiée en unités HIMETRIC.  
  
 Consultez la page [IQuickActivate::GetContentExtent](http://msdn.microsoft.com/library/windows/desktop/ms693792) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namequickactivatea--iquickactivateimplquickactivate"></a><a name="quickactivate"></a>IQuickActivateImpl::QuickActivate  
 Effectue une initialisation des contrôles en cours de chargement rapide.  
  
```
STDMETHOD(QuickActivate)(
    QACONTAINER* pQACont,
    QACONTROL* pQACtrl);
```  
  
### <a name="remarks"></a>Remarques  
 La structure contient des pointeurs vers les interfaces requises par le contrôle et les valeurs de certaines propriétés ambiantes. Au moment du retour, le contrôle passe un pointeur vers un [QACONTROL](http://msdn.microsoft.com/library/windows/desktop/ms693721) structure qui contient des pointeurs vers ses propres interfaces nécessitant le conteneur et d’autres informations d’état.  
  
 Consultez la page [IQuickActivate::QuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms682421) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetcontentextenta--iquickactivateimplsetcontentextent"></a><a name="setcontentextent"></a>IQuickActivateImpl::SetContentExtent  
 Indique au contrôle de la quantité d’espace complet le conteneur a affecté à celle-ci.  
  
```
STDMETHOD(SetContentExtent)(LPSIZEL pSize);
```  
  
### <a name="remarks"></a>Remarques  
 La taille est spécifiée en unités HIMETRIC.  
  
 Consultez la page [IQuickActivate::SetContentExtent](http://msdn.microsoft.com/library/windows/desktop/ms678806) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [CComControl (classe)](../../atl/reference/ccomcontrol-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

