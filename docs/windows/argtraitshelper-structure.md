---
title: ArgTraitsHelper (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraitsHelper
dev_langs:
- C++
helpviewer_keywords:
- ArgTraitsHelper structure
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 31d9072ebf8c36453a74c75ff4a8997805d0973f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="argtraitshelper-structure"></a>ArgTraitsHelper, structure
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<  
   typename TDelegateInterface  
>  
struct ArgTraitsHelper;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `TDelegateInterface`  
 Une interface de délégué.  
  
## <a name="remarks"></a>Notes  
 Permet de définir les caractéristiques communes des arguments de délégué.  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`methodType`|Synonyme de `decltype(&TDelegateInterface::Invoke)`.|  
|`Traits`|Synonyme de `ArgTraits<methodType>`.|  
  
### <a name="public-constants"></a>Constantes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[ArgTraitsHelper::args, constante](../windows/argtraitshelper-args-constant.md)|Permet de [ArgTraits::args](../windows/argtraits-args-constant.md) conserver le nombre de paramètres de la méthode Invoke d’une interface de délégué.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `ArgTraitsHelper`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** event.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)