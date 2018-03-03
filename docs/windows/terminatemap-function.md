---
title: TerminateMap (fonction) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::TerminateMap
dev_langs:
- C++
helpviewer_keywords:
- TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 42f71f86dce35457d5efa81c28d2a58106ba5b81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="terminatemap-function"></a>TerminateMap, fonction
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
inline bool TerminateMap(  
   _In_ ModuleBase *module,   
   _In_opt_z_ const wchar_t *serverName,   
    bool forceTerminate) throw()  
```  
  
## <a name="parameters"></a>Paramètres  
 `module`  
 A [module](../windows/module-class.md).  
  
 `serverName`  
 Le nom d’un sous-ensemble des fabriques de classes dans le module spécifié par le paramètre `module`.  
  
 `forceTerminate`  
 `true`Pour mettre fin à la classe fabriques, quelle que soit leur sont actifs ; `false` ne pas terminer les fabriques de classe si n’importe quel fabrique est active.  
  
## <a name="return-value"></a>Valeur de retour  
 `true`Si toutes les fabriques de classe ont été arrêtées ; dans le cas contraire, `false`.  
  
## <a name="remarks"></a>Notes  
 Arrête les fabriques de classe dans le module spécifié.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** module.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)