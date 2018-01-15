---
title: remove_pointer, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::remove_pointer
dev_langs: C++
helpviewer_keywords:
- remove_pointer class
- remove_pointer
ms.assetid: 2cd4e417-32fb-4f53-bd16-4e8a98240832
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: efc240a12835da1bda0fe840e347200a4f58bcc2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="removepointer-class"></a>remove_pointer, classe
Transforme un pointeur en type.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class T>  
struct remove_pointer;  
 
template <class T>  
using remove_pointer_t = typename remove_pointer<T>::type;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Type à modifier.  
  
## <a name="remarks"></a>Notes  
 Une instance de `remove_pointer<T>` contient un type modifié qui est `T1` quand `T` est au format `T1*`, `T1* const`, `T1* volatile` ou `T1* const volatile`. Sinon, `T`.  
  
## <a name="example"></a>Exemple  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    int *p = (std::remove_pointer_t<int *> *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "remove_pointer_t<int *> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
```  
  
```Output  
remove_pointer_t<int *> == int  
```  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)   
 [add_pointer, classe](../standard-library/add-pointer-class.md)
