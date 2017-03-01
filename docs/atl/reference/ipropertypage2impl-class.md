---
title: Classe de IPropertyPage2Impl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPropertyPage2Impl
dev_langs:
- C++
helpviewer_keywords:
- property pages
- IPropertyPage2 ATL implementation
- IPropertyPage2Impl class
ms.assetid: e89fbe90-203a-47f0-a5de-23616697e1ce
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 43680d12febbd94137009f66242198129d4b3630
ms.lasthandoff: 02/24/2017

---
# <a name="ipropertypage2impl-class"></a>IPropertyPage2Impl (classe)
Cette classe implémente **IUnknown** et hérite de l’implémentation par défaut de [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md).  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class T>  
class IPropertyPage2Impl : public IPropertyPageImpl<T>
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Votre classe, dérivée de `IPropertyPage2Impl`.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[IPropertyPage2Impl::EditProperty](#editproperty)|Spécifie le contrôle de la propriété reçoit le focus lorsque la page de propriétés est activée. Retourne l’implémentation ATL **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Notes  
 Le [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996) interface étend [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) en ajoutant le `EditProperty` (méthode). Cette méthode permet à un client sélectionner une propriété spécifique dans un objet de page de propriétés.  
  
 Classe `IPropertyPage2Impl` renvoie simplement **E_NOTIMPL** de **IPropertyPage2::EditProperty**. Toutefois, il hérite de l’implémentation par défaut de [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) et implémente **IUnknown** en envoyant des informations de dump génère l’appareil en mode de débogage.  
  
 Lorsque vous créez une page de propriétés, votre classe est généralement dérivée `IPropertyPageImpl`. Pour fournir la prise en charge supplémentaire de **IPropertyPage2**, modifiez votre définition de classe et substituer les `EditProperty` (méthode).  
  
 **Articles connexes** [didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [création d’un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `IPropertyPage`  
  
 [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)  
  
 `IPropertyPage2Impl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlctl.h  
  
##  <a name="a-nameeditpropertya--ipropertypage2impleditproperty"></a><a name="editproperty"></a>IPropertyPage2Impl::EditProperty  
 Spécifie le contrôle de la propriété reçoit le focus lorsque la page de propriétés est activée.  
  
```
HRESULT EditProperty(DISPID dispID);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **E_NOTIMPL**.  
  
### <a name="remarks"></a>Notes  
 Consultez la page [IPropertyPage2::EditProperty](http://msdn.microsoft.com/library/windows/desktop/ms690353) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [IPerPropertyBrowsingImpl (classe)](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [Classe de ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

