---
title: is_void, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_void
dev_langs: C++
helpviewer_keywords:
- is_void class
- is_void
ms.assetid: 99b0de3b-1b38-4949-b053-080e5363174e
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8b77866a16eabc39d96e4b66f9419bf618b725ec
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="isvoid-class"></a>is_void, classe
Teste si le type est void.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class T>  
struct is_void;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Type à interroger.  
  
## <a name="remarks"></a>Notes  
 Une instance du prédicat de type a la valeur true si le type `T` est `void` ou une forme cv-qualified de `void`. Sinon, sa valeur est false.  
  
## <a name="example"></a>Exemple  
  
```cpp  
// std__type_traits__is_void.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_void<trivial> == " << std::boolalpha   
        << std::is_void<trivial>::value << std::endl;   
    std::cout << "is_void<void()> == " << std::boolalpha   
        << std::is_void<void()>::value << std::endl;   
    std::cout << "is_void<void> == " << std::boolalpha   
        << std::is_void<void>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_void<trivial> == false  
is_void<void()> == false  
is_void<void> == true  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)
