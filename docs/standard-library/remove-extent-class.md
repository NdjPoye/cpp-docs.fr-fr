---
title: remove_extent, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- remove_extent
- type_traits/std::remove_extent
dev_langs:
- C++
helpviewer_keywords:
- remove_extent class
- remove_extent
ms.assetid: b9320862-3891-49fc-80bc-571eb2c035cf
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 41b445ceeeb1f37ee9873cb55f62d30d480d8718
ms.openlocfilehash: 670e0b97c79fb7d022b2ca5ed08326b31c96e336
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="removeextent-class"></a>remove_extent, classe
Crée un type d'élément à partir d'un type tableau.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class T>  
struct remove_extent;  
 
template <class T>  
using remove_extent_t = typename remove_extent<T>::type;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Type à modifier.  
  
## <a name="remarks"></a>Notes  
 Une instance de `remove_extent<T>` contient un type modifié qui est `T1` quand `T` est de la forme `T1[N]`, ou `T` dans le cas contraire.  
  
## <a name="example"></a>Exemple  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "remove_extent_t<int> == "  
        << typeid(std::remove_extent_t<int>).name()  
        << std::endl;T  
    std::cout << "remove_extent_t<int[5]> == "  
        << typeid(std::remove_extent_t<int[5]>).name()  
        << std::endl;T  
    std::cout << "remove_extent_t<int[5][10]> == "  
        << typeid(std::remove_extent_t<int[5][10]>).name()  
        << std::endl;   
    return (0);   
    }  
```  
  
```Output  
remove_extent_t<int> == int  
remove_extent_t<int[5]> == int  
remove_extent_t<int[5][10]> == int [10]  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)   
 [remove_all_extents, classe](../standard-library/remove-all-extents-class.md)

