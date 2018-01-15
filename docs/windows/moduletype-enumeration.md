---
title: "Moduletype (énumération) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::ModuleType
dev_langs: C++
helpviewer_keywords: ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dd68d911a3734510bfb35db4b3ee0c4b8e46a4a0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="moduletype-enumeration"></a>ModuleType (énumération)
Spécifie si un module doit prendre en charge un serveur in-process ou un serveur out-of-process.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
enum ModuleType;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="values"></a>Valeurs  
  
|Nom|Description|  
|----------|-----------------|  
|`InProc`|Un serveur in-process.|  
|`OutOfProc`|Un serveur out-of-process.|  
|`DisableCaching`|Désactiver le mécanisme de mise en cache sur le Module.|  
|`InProcDisableCaching`|Combinaison de `InProc` et `DisableCaching`.|  
|`OutOfProcDisableCaching`|Combinaison de `OutOfProc` et `DisableCaching`.|  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** module.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)