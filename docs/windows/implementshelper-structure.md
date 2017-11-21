---
title: ImplementsHelper (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::ImplementsHelper
dev_langs: C++
helpviewer_keywords: ImplementsHelper structure
ms.assetid: b857ba80-81bd-4e53-92b6-210991954243
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5bb328b93231646cd3b0ceeea42382d8f8857e21
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="implementshelper-structure"></a>ImplementsHelper (structure)
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <  
   typename RuntimeClassFlagsT,  
   typename ILst,  
   bool IsDelegateToClass  
>  
friend struct Details::ImplementsHelper;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `RuntimeClassFlagsT`  
 Un champ d’indicateurs qui spécifie un ou plusieurs [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) énumérateurs.  
  
 `ILst`  
 Liste des ID d’interface.  
  
 `IsDelegateToClass`  
 Spécifiez `true` si l’instance actuelle d’implémente est une classe de base du premier ID d’interface dans `ILst`; sinon, `false`.  
  
## <a name="remarks"></a>Remarques  
 Permet d’implémenter le [implémente](../windows/implements-structure.md) structure.  
  
 Ce modèle parcourt la liste des interfaces et les ajoute comme classes de base et que les informations nécessaires pour permettre à QueryInterface.  
  
## <a name="members"></a>Membres  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `ImplementsHelper`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** implements.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [Référence (bibliothèque Windows Runtime)](http://msdn.microsoft.com/en-us/00000000-0000-0000-0000-000000000000)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)