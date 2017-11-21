---
title: _1, objet | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _1
- std::_1
- functional/std::_1
dev_langs: C++
helpviewer_keywords: _1 object
ms.assetid: 30c3c480-ff31-4708-94be-7d0d65f243c9
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4364868619359ca23ba50802037eeeb3530c96d3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="1-object"></a>_1, objet
Espaces réservés pour les arguments remplaçables.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
namespace placeholders {  
    extern unspecified _1,
    _2, ... _M  
 } // namespace placeholders (within std)  
```  
  
## <a name="remarks"></a>Remarques  
 Les objets `_1, _2, ... _M` sont des espaces réservés désignant la première, deuxième,..., argument de mois, respectivement, dans un appel de fonction à un objet retourné par [lier](../standard-library/functional-functions.md#bind). Vous utilisez `_N` pour spécifier l’emplacement où le N-ième argument doit être inséré quand la liaison est évaluée.  
  
 Dans cette implémentation, la valeur de `M` est 20.  
  
## <a name="example"></a>Exemple  
  
```cpp  
// std__functional_placeholder.cpp   
// compile with: /EHsc   
#include <functional>   
#include <algorithm>   
#include <iostream>   
  
using namespace std::placeholders;   
  
void square(double x)   
    {   
    std::cout << x << "^2 == " << x * x << std::endl;   
    }   
  
void product(double x, double y)   
    {   
    std::cout << x << "*" << y << " == " << x * y << std::endl;   
    }   
  
int main()   
    {   
    double arg[] = {1, 2, 3};   
  
    std::for_each(&arg[0], &arg[3], square);   
    std::cout << std::endl;   
  
    std::for_each(&arg[0], &arg[3], std::bind(product, _1, 2));   
    std::cout << std::endl;   
  
    std::for_each(&arg[0], &arg[3], std::bind(square, _1));   
  
    return (0);   
    }  
  
```  
  
```Output  
1^2 == 1  
2^2 == 4  
3^2 == 9  
  
1*2 == 2  
2*2 == 4  
3*2 == 6  
  
1^2 == 1  
2^2 == 4  
3^2 == 9  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<functional>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [lier](../standard-library/functional-functions.md#bind)   
 [is_placeholder, classe](../standard-library/is-placeholder-class.md)
