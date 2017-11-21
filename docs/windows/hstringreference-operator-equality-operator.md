---
title: "HStringReference::Operator ==, opérateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator==
dev_langs: C++
ms.assetid: cad3d52d-cd67-4194-a270-5239b1121a09
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 630a10fe751593736fef39d2ca9ba8a56c1d5bed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="hstringreferenceoperator-operator"></a>HStringReference::Operator==, opérateur
Indique si les deux paramètres sont égaux.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
inline bool operator==(  
               const HStringReference& lhs,   
               const HStringReference& rhs) throw()  
  
inline bool operator==(  
               const HSTRING& lhs,   
               const HStringReference& rhs) throw()  
  
inline bool operator==(  
               const HStringReference& lhs,   
               const HSTRING& rhs) throw()  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 `lhs`  
 Le premier paramètre à comparer. `lhs`peut être un objet HStringReference ou un handle HSTRING.  
  
 `rhs`  
 Le deuxième paramètre à comparer.  `rhs`peut être un objet HStringReference ou un handle HSTRING.  
  
## <a name="return-value"></a>Valeur de retour  
 `true`Si le `lhs` et `rhs` paramètres sont égaux ; sinon, `false`.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** corewrappers.h  
  
 **Namespace :** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Voir aussi  
 [HStringReference, classe](../windows/hstringreference-class.md)