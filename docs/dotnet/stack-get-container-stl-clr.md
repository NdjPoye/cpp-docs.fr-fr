---
title: Stack::get_container (STL/CLR) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::stack::get_container
dev_langs:
- C++
helpviewer_keywords:
- get_container member [STL/CLR]
ms.assetid: ba6fc541-fc18-4d1c-8e3f-6baaed427cbb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 29dbc993f38a7cc0663f67487656a0330650537e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="stackgetcontainer-stlclr"></a>stack::get_container (STL/CLR)
Accède au conteneur sous-jacent.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
container_type^ get_container();  
```  
  
## <a name="remarks"></a>Notes  
 La fonction membre retourne un handle pour le conteneur sous-jacent. Il permet de contourner les restrictions imposées par le wrapper de conteneur.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_stack_get_container.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c" using container_type   
    Mystack::container_type wc1 = c1.get_container();   
    for each (wchar_t elem in wc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<cliext/stack >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [pile (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [stack::container_type (STL/CLR)](../dotnet/stack-container-type-stl-clr.md)