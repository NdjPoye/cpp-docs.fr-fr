---
title: Modulebase, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::ModuleBase
dev_langs: C++
helpviewer_keywords: ModuleBase class
ms.assetid: edce7591-6893-46f7-94a7-382827775548
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b02efe3ee61234b2439c1cbbae07827d6a879b2a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="modulebase-class"></a>ModuleBase, classe
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class ModuleBase;  
```  
  
## <a name="remarks"></a>Notes  
 Représente la classe de base de la [Module](../windows/module-class.md) classes.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[ModuleBase::ModuleBase, constructeur](../windows/modulebase-modulebase-constructor.md)|Initialise une instance de la classe de Module.|  
|[ModuleBase::~ModuleBase, destructeur](../windows/modulebase-tilde-modulebase-destructor.md)|Désinitialise l’instance actuelle de la classe de Module.|  
  
### <a name="public-methods"></a>Méthodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[ModuleBase::DecrementObjectCount, méthode](../windows/modulebase-decrementobjectcount-method.md)|En cas d’implémentation, décrémente le nombre d’objets suivis par le module.|  
|[ModuleBase::IncrementObjectCount, méthode](../windows/modulebase-incrementobjectcount-method.md)|En cas d’implémentation, incrémente le nombre d’objets suivis par le module.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `ModuleBase`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** implements.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)