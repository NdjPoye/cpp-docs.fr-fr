---
title: deque::pop_front (STL/CLR) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::pop_front
dev_langs:
- C++
helpviewer_keywords:
- pop_front member [STL/CLR]
ms.assetid: 5042df47-b226-4b16-982e-6a4543b8e00b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d52387bc3de6da5808ea135ddc5b75e03c3fa3f8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="dequepopfront-stlclr"></a>deque::pop_front (STL/CLR)
Supprime le premier élément.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void pop_front();  
```  
  
## <a name="remarks"></a>Notes  
 La fonction membre supprime le premier élément de la séquence contrôlée, qui doit être vide. Il permet de raccourcir la deque d’un élément au début.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_deque_pop_front.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// pop an element and redisplay   
    c1.pop_front();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
b c  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<cliext/deque >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::pop_back (STL/CLR)](../dotnet/deque-pop-back-stl-clr.md)   
 [deque::push_back (STL/CLR)](../dotnet/deque-push-back-stl-clr.md)   
 [deque::push_front (STL/CLR)](../dotnet/deque-push-front-stl-clr.md)