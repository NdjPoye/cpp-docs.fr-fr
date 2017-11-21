---
title: "Comparestringordinal, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Details::CompareStringOrdinal
dev_langs: C++
ms.assetid: ffa997fd-8cd7-40a5-b9e7-f55d40b072f4
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 17415efa6519d8e3538f869168db2040ed6e73dc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="comparestringordinal-method"></a>CompareStringOrdinal, méthode
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
inline INT32 CompareStringOrdinal(  
   HSTRING lhs,   
   HSTRING rhs)  
```  
  
#### <a name="parameters"></a>Paramètres  
 `lhs`  
 La première HSTRING à comparer.  
  
 `rhs`  
 La deuxième HSTRING à comparer.  
  
## <a name="return-value"></a>Valeur de retour  
  
|Valeur|Condition|  
|-----------|---------------|  
|-1|`lhs` est inférieur à `rhs`.|  
|0|`lhs` est égal à `rhs`.|  
|1|`lhs` est supérieur à `rhs`.|  
  
## <a name="remarks"></a>Remarques  
 Compare deux objets HSTRING spécifiés et retourne un entier qui indique leur position relative dans un ordre de tri.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** corewrappers.h  
  
 **Namespace :** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL::Wrappers::Details, espace de noms](../windows/microsoft-wrl-wrappers-details-namespace.md)