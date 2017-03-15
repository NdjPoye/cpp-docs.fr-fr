---
title: Classe de CFirePropNotifyEvent | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFirePropNotifyEvent
- ATL::CFirePropNotifyEvent
- ATL.CFirePropNotifyEvent
dev_langs:
- C++
helpviewer_keywords:
- sinks, notifying of ATL events
- CFirePropNotifyEvent class
- connection points [C++], notifying of events
ms.assetid: eb7a563e-6bce-4cdf-8d20-8c6a5307781b
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
ms.openlocfilehash: 1511a9e9ba287d12aade7c393887c6b5f8880b96
ms.lasthandoff: 02/24/2017

---
# <a name="cfirepropnotifyevent-class"></a>CFirePropNotifyEvent (classe)
Cette classe fournit des méthodes pour notifier le récepteur du conteneur en ce qui concerne les modifications apportées aux propriétés de contrôle.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CFirePropNotifyEvent
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CFirePropNotifyEvent::FireOnChanged](#fireonchanged)|(Statique) Notifie le récepteur du conteneur qu’une propriété de contrôle a changé.|  
|[CFirePropNotifyEvent::FireOnRequestEdit](#fireonrequestedit)|(Statique) Notifie le récepteur du conteneur d’une propriété de contrôle est sur le point de changer.|  
  
## <a name="remarks"></a>Remarques  
 `CFirePropNotifyEvent`a deux méthodes de notification du récepteur du conteneur d’une propriété de contrôle a été modifié ou est sur le point de changer.  
  
 Si la classe qui implémente votre contrôle est dérivée `IPropertyNotifySink`, le `CFirePropNotifyEvent` les méthodes sont appelées lorsque vous appelez `FireOnRequestEdit` ou `FireOnChanged`. Si votre classe de contrôle n’est pas dérivée `IPropertyNotifySink`, les appels à ces fonctions retournent `S_OK`.  
  
 Pour plus d’informations sur la création de contrôles, consultez la [didacticiel ATL](../../atl/active-template-library-atl-tutorial.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlctl.h  
  
##  <a name="a-namefireonchangeda--cfirepropnotifyeventfireonchanged"></a><a name="fireonchanged"></a>CFirePropNotifyEvent::FireOnChanged  
 Avertit tous connectés [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) (sur chaque point de connexion de l’objet), les interfaces que la propriété de l’objet spécifié a changé.  
  
```
static HRESULT FireOnChanged(IUnknown* pUnk, DISPID dispID);
```  
  
### <a name="parameters"></a>Paramètres  
 *pUnk*  
 [in] Pointeur vers le **IUnknown** de l’objet de la notification.  
  
 *dispID*  
 [in] Identificateur de la propriété qui a changé.  
  
### <a name="return-value"></a>Valeur de retour  
 Un de la norme `HRESULT` valeurs.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction peut appeler, même si votre contrôle ne prend pas en charge les points de connexion.  
  
##  <a name="a-namefireonrequestedita--cfirepropnotifyeventfireonrequestedit"></a><a name="fireonrequestedit"></a>CFirePropNotifyEvent::FireOnRequestEdit  
 Avertit tous connectés [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) (sur chaque point de connexion de l’objet), les interfaces que la propriété de l’objet spécifié est sur le point de changer.  
  
```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```  
  
### <a name="parameters"></a>Paramètres  
 *pUnk*  
 [in] Pointeur vers le **IUnknown** de l’objet de la notification.  
  
 *dispID*  
 [in] Identificateur de la propriété va être modifiée.  
  
### <a name="return-value"></a>Valeur de retour  
 Un de la norme `HRESULT` valeurs.  
  
### <a name="remarks"></a>Notes  
 Cette fonction peut appeler, même si votre contrôle ne prend pas en charge les points de connexion.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

