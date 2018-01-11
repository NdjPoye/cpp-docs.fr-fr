---
title: is_placeholder, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: functional/std::is_placeholder
dev_langs: C++
helpviewer_keywords: is_placeholder class
ms.assetid: 2b21a792-96d1-4bb8-b911-0db796510835
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9aa19cb8fceb167cd98c94583e47f2e9c1227333
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="isplaceholder-class"></a>is_placeholder, classe
Teste si le type est un espace réservé.  
  
## <a name="syntax"></a>Syntaxe  
  
struct is_placeholder {  
   static const int value;  
   };  
  
## <a name="remarks"></a>Notes  
 La valeur de constante `value` est 0 si le type `Ty` n’est pas un espace réservé ; sinon, sa valeur est la position de l’argument d’appel de fonction auquel elle est liée. Vous pouvez l’utiliser pour déterminer la valeur `N` du nième espace réservé `_N`.  
  
## <a name="example"></a>Exemple  
  
```cpp  
// std__functional__is_placeholder.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
using namespace std::placeholders;   
  
template<class Expr>
void test_for_placeholder(const Expr&)
{
    std::cout << std::is_placeholder<Expr>::value << std::endl;
}

int main()
{
    test_for_placeholder(3.0);
    test_for_placeholder(_3);

    return (0);
}  
```  
  
```Output  
0  
3  
```  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<functional>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [_1, objet](../standard-library/1-object.md)

