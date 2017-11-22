---
title: is_bind_expression, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- functional/std::is_bind_expression
dev_langs:
- C++
helpviewer_keywords:
- is_bind_expression class
ms.assetid: 0715f9e9-2239-4778-a1cf-2c21f49dfd47
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 691a4a3d60e46fdc1ac5f98c60bd03f44065e63f
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="isbindexpression-class"></a>is_bind_expression, classe
Teste si le type est généré en appelant `bind`.  
  
## <a name="syntax"></a>Syntaxe  
  
template<class Ty>  
struct is_bind_expression {  
   static const bool value;  
   };  
  
## <a name="remarks"></a>Notes  
Le membre de constante `value` a la valeur true si le type `Ty` est un type retourné par un appel à `bind` ; sinon, false.  
  
## <a name="example"></a>Exemple  
  
```cpp  
// std__functional__is_bind_expression.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
void square(double x)
{
    std::cout << x << "^2 == " << x * x << std::endl;
}

template<class Expr>
void test_for_bind(const Expr&)
{
    std::cout << std::is_bind_expression<Expr>::value << std::endl;
}

int main()
{
    test_for_bind(3.0 * 3.0);
    test_for_bind(std::bind(square, 3));

    return (0);
}  
```  
  
```Output  
0  
1  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<functional>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [bind](../standard-library/functional-functions.md#bind)

