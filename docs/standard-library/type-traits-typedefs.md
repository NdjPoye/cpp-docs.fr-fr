---
title: '&lt;type_traits&gt;, typedefs | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- false_type
- std::false_type
- type_traits/std::false_type
- xtr1common/std::false_type
- true_type
- std::true_type
- type_traits/std::true_type
- xtr1common/std::true_type
ms.assetid: 8ac040ca-ed2d-4570-adc9-cb5626530053
caps.latest.revision: 13
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 41b445ceeeb1f37ee9873cb55f62d30d480d8718
ms.openlocfilehash: 5f1234e6a88cf9e51555453ec8bf7091f1bc58eb
ms.lasthandoff: 02/24/2017

---
# <a name="lttypetraitsgt-typedefs"></a>&lt;type_traits&gt;, typedefs
|||  
|-|-|  
|[false_type, typedef](#false_type_typedef)|[true_type, typedef](#true_type_typedef)|  
  
##  <a name="a-namefalsetypetypedefa--falsetype-typedef"></a><a name="false_type_typedef"></a>  false_type, typedef  
 Contient une constante intégrale avec la valeur false.  
  
```  
typedef integral_constant<bool, false> false_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme pour une spécialisation du modèle `integral_constant`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main() {   
    std::cout << "false_type == " << std::boolalpha   
        << std::false_type::value << std::endl;   
    std::cout << "true_type == " << std::boolalpha   
        << std::true_type::value << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
false_type == false  
true_type == true  
```  
  
##  <a name="a-nametruetypetypedefa--truetype-typedef"></a><a name="true_type_typedef"></a>  true_type, typedef  
 Contient une constante intégrale avec la valeur true.  
  
```  
typedef integral_constant<bool, true> true_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme pour une spécialisation du modèle `integral_constant`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__type_traits__true_type.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main() {   
    std::cout << "false_type == " << std::boolalpha   
        << std::false_type::value << std::endl;   
    std::cout << "true_type == " << std::boolalpha   
        << std::true_type::value << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
false_type == false  
true_type == true  
```  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)


