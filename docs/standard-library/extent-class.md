---
title: extent, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- extent
- type_traits/std::extent
dev_langs:
- C++
helpviewer_keywords:
- extent class
- extent
ms.assetid: 6d16263d-90b2-4330-9ec7-b59ed898792d
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 23cf8230cd5b8adb7975ec21a249d9efc4d66c71
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="extent-class"></a>extent, classe
Obtient une dimension de tableau.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Ty, unsigned I = 0>  
struct extent;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Ty`  
 Type à interroger.  
  
 `I`  
 Tableau lié à interroger.  
  
## <a name="remarks"></a>Notes  
 Si `Ty` est un type tableau qui possède au moins `I` dimensions, la requête de type contient le nombre d'éléments dans la dimension spécifié par `I`. Si `Ty` n'est pas un type tableau ou si son rang est inférieur à `I`, ou si `I` est égal à zéro et que `Ty` est de type « tableau ayant des limites d'index inconnues de `U` », la requête de type contient la valeur 0.  
  
## <a name="example"></a>Exemple  
  
```cpp  
// std__type_traits__extent.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "extent 0 == "   
        << std::extent<int[5][10]>::value << std::endl;   
    std::cout << "extent 1 == "   
        << std::extent<int[5][10], 1>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
extent 0 == 5  
extent 1 == 10  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)   
 [remove_all_extents, classe](../standard-library/remove-all-extents-class.md)   
 [remove_extent, classe](../standard-library/remove-extent-class.md)

