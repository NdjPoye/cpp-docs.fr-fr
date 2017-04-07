---
title: Classe de IPropertyNotifySinkCP | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPropertyNotifySinkCP
- atlctl/ATL::IPropertyNotifySinkCP
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], managing
- sinks, notifying of changes
- IPropertyNotifySinkCP class
ms.assetid: 1b41445e-bc88-4fa6-bb62-d68aacec2bd5
caps.latest.revision: 21
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: feff2467d6d72e9d0a9186dc269f48eb26cbfee2
ms.lasthandoff: 03/17/2017

---
# <a name="ipropertynotifysinkcp-class"></a>IPropertyNotifySinkCP (classe)
Cette classe expose [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) interface comme une interface sortante sur un objet connectable.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class T, class CDV = CComDynamicUnkArray>  
class IPropertyNotifySinkCP 
   : public IConnectionPointImpl<T, &IID_IPropertyNotifySink, CDV>
```    
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Votre classe, dérivée de `IPropertyNotifySinkCP`.  
  
 `CDV`  
 Une classe qui gère les connexions entre un point de connexion et ses récepteurs. La valeur par défaut est [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), ce qui permet un nombre illimité de connexions. Vous pouvez également utiliser [CComUnkArray](../../atl/reference/ccomunkarray-class.md), qui spécifie un nombre fixe de connexions.  
  
## <a name="remarks"></a>Remarques  
 `IPropertyNotifySinkCP`hérite de toutes les méthodes à sa classe de base, [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md).  
  
 Le [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) interface permet à un objet sink de recevoir des notifications sur les modifications de propriété. Classe `IPropertyNotifySinkCP` expose cette interface comme une interface sortante sur un objet connectable. Le client doit implémenter le `IPropertyNotifySink` méthodes sur le récepteur.  
  
 Dérivez votre classe de `IPropertyNotifySinkCP` lorsque vous souhaitez créer un point de connexion qui représente le `IPropertyNotifySink` interface.  
  
 Pour plus d’informations sur l’utilisation de points de connexion dans ATL, consultez l’article [Points de connexion](../../atl/atl-connection-points.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlctl.h  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)   
 [IConnectionPointContainerImpl (classe)](../../atl/reference/iconnectionpointcontainerimpl-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

