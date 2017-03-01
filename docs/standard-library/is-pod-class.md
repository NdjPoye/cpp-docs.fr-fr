---
title: is_pod, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_pod
- std::is_pod
- type_traits/std::is_pod
dev_langs:
- C++
helpviewer_keywords:
- is_pod class
- is_pod
ms.assetid: d73ebdee-746b-4082-9fa4-2db71432eb0e
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
translationtype: Machine Translation
ms.sourcegitcommit: 28baed4badda4f2c1d7e5b20235fe8d40c2a7195
ms.openlocfilehash: 2236d6a9796b1353b919a63620606242cde169bd
ms.lasthandoff: 02/24/2017

---
# <a name="ispod-class"></a>is_pod, classe
Teste si le type est POD.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T>
struct is_pod;
```  
  
#### <a name="parameters"></a>Paramètres  
*T*  
Type à interroger.  
  
## <a name="remarks"></a>Notes  
`is_pod<T>::value` est `true` si le type *T* est Plain Old Data (POD). Sinon, il est `false`.  
  
Les types arithmétiques, les types énumération, les types pointeur et les pointeurs vers des types de membres sont des types POD.  
  
Une version cv-qualified d'un type POD est elle-même un type POD.  
  
Un tableau de POD est lui-même POD.  
  
Une structure ou une union, dont tous les membres de données non statiques sont POD, est elle-même POD si elle n'a :  
  
-   aucun constructeur déclaré par l'utilisateur ;  
  
-   aucun membre de données non statiques privé ou protégé ;  
  
-   aucune classe de base ;  
  
-   aucune fonction virtuelle ;  
  
-   aucun membre de données non statiques de type référence ;  
  
-   aucun opérateur d'assignation de copie défini par l'utilisateur ;  
  
-   aucun destructeur défini par l'utilisateur.  
  
Par conséquent, vous pouvez générer de manière récursive des structs et des tableaux POD qui contiennent des structs et des tableaux POD.  
  
## <a name="example"></a>Exemple  
  
```cpp  
// std__type_traits__is_pod.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial {   
    int val;   
};   
  
struct throws {   
    throws() {}  // User-declared ctor, so not POD
  
    int val;   
};   
  
int main() {   
    std::cout << "is_pod<trivial> == " << std::boolalpha   
        << std::is_pod<trivial>::value << std::endl;   
    std::cout << "is_pod<int> == " << std::boolalpha   
        << std::is_pod<int>::value << std::endl;   
    std::cout << "is_pod<throws> == " << std::boolalpha   
        << std::is_pod<throws>::value << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
is_pod<trivial> == true  
is_pod<int> == true  
is_pod<throws> == false  
```  
  
## <a name="requirements"></a>Spécifications  
**En-tête :** \<type_traits>  
  
**Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
[<type_traits>](../standard-library/type-traits.md)




