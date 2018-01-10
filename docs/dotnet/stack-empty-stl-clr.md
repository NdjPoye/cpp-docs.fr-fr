---
title: Stack::Empty (STL/CLR) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::stack::empty
dev_langs: C++
helpviewer_keywords: empty member [STL/CLR]
ms.assetid: 30bb4ec6-e7a1-4137-99ba-0e0ebdf31baf
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2d7bffa6f62952295edf3dd8b40918b604ca41f0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="stackempty-stlclr"></a>stack::empty (STL/CLR)
Vérifie l'absence d'éléments.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
bool empty();  
```  
  
## <a name="remarks"></a>Notes  
 La fonction membre retourne la valeur true pour une séquence contrôlée vide. Elle est équivalente à [stack::size (STL/CLR)](../dotnet/stack-size-stl-clr.md)`() == 0`. Il permet de tester si la pile est vide.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_stack_empty.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.pop();   
    c1.pop();   
    c1.pop();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 3  
empty() = False  
size() = 0  
empty() = True  
```  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<cliext/stack >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [pile (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [stack::size (STL/CLR)](../dotnet/stack-size-stl-clr.md)