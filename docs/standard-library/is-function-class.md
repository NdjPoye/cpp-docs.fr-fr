---
title: is_function, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_function
- std::is_function
- type_traits/std::is_function
dev_langs:
- C++
helpviewer_keywords:
- is_function class
- is_function
ms.assetid: e5c0dbcd-829b-415f-853f-8c5be47c5040
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 8f718f24d0751a1050b76f8fb2cab09b0b970647
ms.lasthandoff: 02/24/2017

---
# <a name="isfunction-class"></a>is_function, classe
Teste si le type est un type de fonction.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Ty>  
struct is_function;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Ty`  
 Type à interroger.  
  
## <a name="remarks"></a>Notes  
 Une instance du prédicat de type a la valeur true si le type `Ty` est un type de fonction. Sinon, sa valeur est false.  
  
## <a name="example"></a>Exemple  
  
```cpp  
// std__type_traits__is_function.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
struct functional   
    {   
    int f();   
    };   
  
int main()   
    {   
    std::cout << "is_function<trivial> == " << std::boolalpha   
        << std::is_function<trivial>::value << std::endl;   
    std::cout << "is_function<functional> == " << std::boolalpha   
        << std::is_function<functional>::value << std::endl;   
    std::cout << "is_function<float()> == " << std::boolalpha   
        << std::is_function<float()>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_function<trivial> == false  
is_function<functional> == false  
is_function<float()> == true  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)   
 [is_object, classe](../standard-library/is-object-class.md)

