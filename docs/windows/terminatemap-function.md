---
title: TerminateMap (fonction) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Details::TerminateMap
dev_langs: C++
helpviewer_keywords: TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: efe6b143c2fe9a48a008f9005244178b436d170e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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
  
## <a name="remarks"></a>Remarques  
 Arrête les fabriques de classe dans le module spécifié.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** module.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)