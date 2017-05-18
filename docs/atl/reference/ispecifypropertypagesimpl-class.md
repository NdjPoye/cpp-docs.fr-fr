---
title: Classe de ISpecifyPropertyPagesImpl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl::GetPages
dev_langs:
- C++
helpviewer_keywords:
- property pages, CLSIDs associated with
- ISpecifyPropertyPages
- ISpecifyPropertyPagesImpl class
ms.assetid: 4e4b9795-b656-4d56-9b8c-85941e7731f9
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 4d5f74de2ec6569527221cf94df6f7921f4bb4c9
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="ispecifypropertypagesimpl-class"></a>Classe de ISpecifyPropertyPagesImpl
Cette classe implémente **IUnknown** et fournit une implémentation par défaut de la [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217) interface.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class T>  
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl 
   : public ISpecifyPropertyPages
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Votre classe, dérivée de `ISpecifyPropertyPagesImpl`.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[ISpecifyPropertyPagesImpl::GetPages](#getpages)|Remplit un valeurs compté le tableau de UUID. Chaque UUID correspond au CLSID d’une des pages de propriétés qui peuvent être affichés dans la feuille de propriétés de l’objet.|  
  
## <a name="remarks"></a>Notes  
 Le [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217) interface permet à un client obtenir une liste de CLSID pour les pages de propriétés pris en charge par un objet. Classe `ISpecifyPropertyPagesImpl` fournit une implémentation par défaut de cette interface et implémente **IUnknown** en envoyant des informations de dump génère l’appareil en mode de débogage.  
  
> [!NOTE]
>  N’exposez pas le **ISpecifyPropertyPages** si votre objet ne prend pas en charge les pages de propriétés de l’interface.  
  
 **Articles connexes** [didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [création d’un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `ISpecifyPropertyPages`  
  
 `ISpecifyPropertyPagesImpl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
##  <a name="getpages"></a>ISpecifyPropertyPagesImpl::GetPages  
 Remplit le tableau le [CAUUID](http://msdn.microsoft.com/library/windows/desktop/ms680048) structure avec les CLSID pour les pages de propriétés qui peuvent être affichés dans la feuille de propriétés de l’objet.  
  
```
STDMETHOD(GetPages)(CAUUID* pPages);
```  
  
### <a name="remarks"></a>Notes  
 ATL utilise le mappage des propriétés de l’objet pour récupérer chaque CLSID.  
  
 Consultez la page [ISpecifyPropertyPages::GetPages](http://msdn.microsoft.com/library/windows/desktop/ms687276) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [IPropertyPageImpl (classe)](../../atl/reference/ipropertypageimpl-class.md)   
 [IPerPropertyBrowsingImpl (classe)](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

