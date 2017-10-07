---
title: is_trivial, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- type_traits/std::is_trivial
dev_langs:
- C++
helpviewer_keywords:
- is_trivial
ms.assetid: 6beb11d4-2f38-4c7e-9959-ca5d26250df7
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: f4e57d84395ebce879187de37c7e2a59f33bfb1b
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="istrivial-class"></a>is_trivial, classe
Teste si le type est un type trivial.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T>  
struct is_trivial;
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Type à interroger.  
  
## <a name="remarks"></a>Notes  
 Une instance du prédicat de type a la valeur true si le type `T` est un type trivial. Sinon, sa valeur est false. Les types triviaux sont les types scalaires, les types de classes pouvant être copiés de façon triviale, les tableaux de ces types et les versions cv-qualified de ces types.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)




