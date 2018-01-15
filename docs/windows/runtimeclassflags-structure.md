---
title: RuntimeClassFlags (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::RuntimeClassFlags
dev_langs: C++
helpviewer_keywords: RuntimeClassFlags structure
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 85eb42c537845d86ce8cf3b1f20db7e9eeffe76f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags (structure)
Contient le type d’une instance d’un [RuntimeClass](../windows/runtimeclass-class.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <  
   unsigned int flags  
>  
struct RuntimeClassFlags;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `flags`  
 A [runtimeclasstype, énumération](../windows/runtimeclasstype-enumeration.md) valeur.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constants"></a>Constantes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[RuntimeClassFlags::value, constante](../windows/runtimeclassflags-value-constant.md)|Contient un [runtimeclasstype, énumération](../windows/runtimeclasstype-enumeration.md) valeur.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `RuntimeClassFlags`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** implements.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)