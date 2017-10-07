---
title: add_cv, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::add_cv
dev_langs:
- C++
helpviewer_keywords:
- add_cv class
- add_cv
ms.assetid: a5572c78-a097-45d7-b476-ed4876889dea
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 90d31b9eaa9baf3f282fb5cc57e0c75c7480e489
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="addcv-class"></a>add_cv, classe
Crée un type volatile const à partir d’un type.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class T>  
struct add_cv;  
 
template <class T>
using add_cv_t = typename add_cv<T>::type;  
```  
  
#### <a name="parameters"></a>Paramètres  
*T*  
Type à modifier.  
  
## <a name="remarks"></a>Notes  
Une instance du type modifié `add_cv<T>` a un typedef de membre `type` équivalent à *T* modifié par [add_volatile](../standard-library/add-volatile-class.md) et [add_const](../standard-library/add-const-class.md), sauf si *T* a déjà les qualificateurs cv, est une référence ou une fonction.  
  
Le type d’assistance `add_cv_t<T>` est un raccourci pour accéder au typedef de membre de `add_cv<T>` `type`.
  
## <a name="example"></a>Exemple  
  
```cpp  
// add_cv.cpp
// compile by using: cl /EHsc /W4 add_cv.cpp
#include <type_traits>   
#include <iostream>   

struct S {
    void f() { 
        std::cout << "invoked non-cv-qualified S.f()" << std::endl; 
    }
    void f() const { 
        std::cout << "invoked const S.f()" << std::endl; 
    }
    void f() volatile { 
        std::cout << "invoked volatile S.f()" << std::endl; 
    }
    void f() const volatile { 
        std::cout << "invoked const volatile S.f()" << std::endl; 
    }
};

template <class T>
void invoke() {
    T t;
    ((T *)&t)->f(); 
}

int main()
{
    invoke<S>();
    invoke<std::add_const<S>::type>();
    invoke<std::add_volatile<S>::type>();
    invoke<std::add_cv<S>::type>();
}  
```  
  
```Output  
invoked non-cv-qualified S.f()
invoked const S.f()
invoked volatile S.f()
invoked const volatile S.f()  
```  
  
## <a name="requirements"></a>Spécifications  
**En-tête :** \<type_traits>  
**Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
[<type_traits>](../standard-library/type-traits.md)   
[remove_const, classe](../standard-library/remove-const-class.md)   
[remove_volatile, classe](../standard-library/remove-volatile-class.md)

