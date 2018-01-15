---
title: Inspectableclass, Macro | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::InspectableClass
dev_langs: C++
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1ac1f84c76bb61d24ee25e8ca431e13620f6f85a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="inspectableclass-macro"></a>InspectableClass, macro
Définit le niveau de confiance et de nom de la classe runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
InspectableClass(  
   runtimeClassName,   
   trustLevel)  
```  
  
#### <a name="parameters"></a>Paramètres  
 `runtimeClassName`  
 Nom de la classe runtime textuel complet.  
  
 `trustLevel`  
 Parmi les [TrustLevel](http://msdn.microsoft.com/library/br224625.aspx) valeurs énumérées.  
  
## <a name="remarks"></a>Notes  
 Le `InspectableClass` macro peut être utilisée uniquement avec les types Windows Runtime.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** implements.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [RuntimeClass, classe](../windows/runtimeclass-class.md)