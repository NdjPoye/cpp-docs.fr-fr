---
title: is_floating_point, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_floating_point
- std::is_floating_point
- type_traits/std::is_floating_point
dev_langs:
- C++
helpviewer_keywords:
- is_floating_point class
- is_floating_point
ms.assetid: 070679c1-115b-4ee4-8ab7-f52e5d9e157f
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 28baed4badda4f2c1d7e5b20235fe8d40c2a7195
ms.openlocfilehash: fad953c57d32b7851cff3083fc133dce5fd2ef10
ms.lasthandoff: 02/24/2017

---
# <a name="isfloatingpoint-class"></a>is_floating_point, classe
Teste si le type est à virgule flottante.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Ty>  
struct is_floating_point;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Ty`  
 Type à interroger.  
  
## <a name="remarks"></a>Notes  
 Une instance du prédicat de type a la valeur true si le type `Ty` est un type à virgule flottante ou une forme `cv-qualified` d'un type à virgule flottante. Sinon, sa valeur est false.  
  
 Un type à virgule flottante est `float`, `double` ou `long double`.  
  
## <a name="example"></a>Exemple  
  
```cpp  
// std__type_traits__is_floating_point.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_floating_point<trivial> == " << std::boolalpha   
        << std::is_floating_point<trivial>::value << std::endl;   
    std::cout << "is_floating_point<int> == " << std::boolalpha   
        << std::is_floating_point<int>::value << std::endl;   
    std::cout << "is_floating_point<float> == " << std::boolalpha   
        << std::is_floating_point<float>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_floating_point<trivial> == false  
is_floating_point<int> == false  
is_floating_point<float> == true  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)   
 [is_integral, classe](../standard-library/is-integral-class.md)

