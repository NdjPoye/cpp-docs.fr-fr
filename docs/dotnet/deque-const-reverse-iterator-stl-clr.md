---
title: deque::const_reverse_iterator (STL/CLR) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::const_reverse_iterator
dev_langs:
- C++
helpviewer_keywords:
- const_reverse_iterator member [STL/CLR]
ms.assetid: fd3a99de-2721-432b-a502-412a72b98e74
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b435e8f1116b3b810aa468f62cdb81c814d922b4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="dequeconstreverseiterator-stlclr"></a>deque::const_reverse_iterator (STL/CLR)
Le type d’un itérateur inverse constant pour la séquence contrôlée...  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef T4 const_reverse_iterator;  
```  
  
## <a name="remarks"></a>Notes  
 Le type décrit un objet de type non spécifié `T4` qui peut servir d’un itérateur inverse constant pour la séquence contrôlée.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_deque_const_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" reversed   
    cliext::deque<wchar_t>::const_reverse_iterator crit = c1.rbegin();   
    cliext::deque<wchar_t>::const_reverse_iterator crend = c1.rend();   
    for (; crit != crend; ++crit)   
        System::Console::Write(" {0}", *crit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<cliext/deque >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::reverse_iterator (STL/CLR)](../dotnet/deque-reverse-iterator-stl-clr.md)