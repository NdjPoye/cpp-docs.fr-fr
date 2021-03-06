---
title: deque::Size (STL/CLR) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::size
dev_langs:
- C++
helpviewer_keywords:
- size member [STL/CLR]
ms.assetid: 81db82c1-7fe7-4eb4-8785-6d36197e4681
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f377e64a3d6e47000eb601a1c3883204d0f2a8e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="dequesize-stlclr"></a>deque::size (STL/CLR)
Compte le nombre d'éléments.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
size_type size();  
```  
  
## <a name="remarks"></a>Notes  
 La fonction membre retourne la longueur de la séquence contrôlée. Il permet de déterminer le nombre d’éléments actuellement dans la séquence contrôlée. Si tout vous intéressent est indique si la séquence a une taille différente de zéro, consultez [deque::empty (STL/CLR)](../dotnet/deque-empty-stl-clr.md)`()`.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_deque_size.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0} after clearing", c1.size());   
  
// add elements and clear again   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 3 starting with 3  
size() = 0 after clearing  
size() = 2 after adding 2  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<cliext/deque >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::empty (STL/CLR)](../dotnet/deque-empty-stl-clr.md)