---
title: deque::iterator (STL/CLR) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::iterator
dev_langs:
- C++
helpviewer_keywords:
- iterator member [STL/CLR]
ms.assetid: 3529e793-5d56-4cb2-898d-fdedb90b5c0c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0e854d0e195273382233e963131e950b593a95cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="dequeiterator-stlclr"></a>deque::iterator (STL/CLR)
Type d'un itérateur pour la séquence contrôlée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef T1 iterator;  
```  
  
## <a name="remarks"></a>Notes  
 Le type décrit un objet de type non spécifié `T1` qui peut servir d’itérateur à accès aléatoire pour la séquence contrôlée.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_deque_iterator.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    cliext::deque<wchar_t>::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
  
// alter first element and redisplay   
    it = c1.begin();   
    *it = L'x';   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
x b c  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<cliext/deque >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::const_iterator (STL/CLR)](../dotnet/deque-const-iterator-stl-clr.md)