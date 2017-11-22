---
title: is_trivially_destructible, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: type_traits/std::is_trivially_destructible
dev_langs: C++
helpviewer_keywords: is_trivially_destructible
ms.assetid: 3f7a787d-2448-40c5-ac51-a228318e02ce
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0f2b9f29915fb2b47f84b3192b9bd90a71c92eae
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="istriviallydestructible-class"></a>is_trivially_destructible, classe
Teste si le type peut être détruit de façon triviale.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T>  
struct is_trivially_destructible;
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Type à interroger.  
  
## <a name="remarks"></a>Notes  
 Une instance du prédicat de type a la valeur true si le type `T` est un type destructible et que le destructeur est connu du compilateur comme n’utilisant aucune opération non triviale. Sinon, sa valeur est false.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)


