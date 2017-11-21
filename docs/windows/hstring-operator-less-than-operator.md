---
title: "HString::Operator&lt; opérateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HString::operator<
dev_langs: C++
ms.assetid: 48a051cb-4609-42be-b48c-d35fc99d1eab
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 84725ca0ceeb4778bec2add60c7e96eff3ab3bfb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="hstringoperatorlt-operator"></a>HString::Operator&lt; (opérateur)
Indique si le premier paramètre est inférieur au second paramètre.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
inline bool operator<(  
    const HString& lhs,   
    const HString& rhs) throw()  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 `lhs`  
 Le premier paramètre à comparer. `lhs`peut être une référence à HString.  
  
 `rhs`  
 Le deuxième paramètre à comparer. `rhs`peut être une référence à HString.  
  
## <a name="return-value"></a>Valeur de retour  
 `true`Si le `lhs` paramètre est inférieure à la `rhs` paramètre ; sinon, `false`.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** corewrappers.h  
  
 **Namespace :** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Voir aussi  
 [HString, classe](../windows/hstring-class.md)