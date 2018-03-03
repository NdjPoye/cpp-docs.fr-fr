---
title: "Canceltransitionpolicy, énumération | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::CancelTransitionPolicy::TransitionFromCanceled
- module/Microsoft::WRL::CancelTransitionPolicy::RemainCanceled
- module/Microsoft::WRL::CancelTransitionPolicy
dev_langs:
- C++
helpviewer_keywords:
- CancelTransitionPolicy Enumeration
ms.assetid: 5de49f7d-e5e3-43e9-bbca-666caf226cef
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 14c3016d767e38e032a745a5957fa93d51f2dae8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="canceltransitionpolicy-enumeration"></a>CancelTransitionPolicy, énumération
Indique la façon dont une opération asynchrone tentative du passage à un état terminal de terminée ou l’erreur doit se comporter en ce qui concerne un client a demandé l’état annulé.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
enum CancelTransitionPolicy;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="values"></a>Valeurs  
  
|Nom|Description|  
|----------|-----------------|  
|`RemainCanceled`|Si l’opération asynchrone est actuellement dans un état annulé de demande du client, cela indique qu’il reste dans l’état annulé, par opposition à la transition vers un Terminal Server s’est terminée ou l’état d’erreur.|  
|`TransitionFromCanceled`|Si l’opération asynchrone est actuellement dans un état annulé de demande du client, cela indique qu’état doit passer à partir de ce à l’état terminal d’état d’annulation s’est terminée ou d’erreur tel que déterminé par l’appel qui utilise cet indicateur.|  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** async.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)