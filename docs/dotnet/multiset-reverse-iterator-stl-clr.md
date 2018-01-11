---
title: multiset::reverse_iterator (STL/CLR) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::multiset::reverse_iterator
dev_langs: C++
helpviewer_keywords: reverse_iterator member [STL/CLR]
ms.assetid: dde6ad36-ca59-4728-aa53-e3d117eb4f48
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d60fdeef8bc15f29183b0a32b19c7f38750e5250
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="multisetreverseiterator-stlclr"></a>multiset::reverse_iterator (STL/CLR)
Type d'un itérateur inverse pour la séquence contrôlée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef T3 reverse_iterator;  
```  
  
## <a name="remarks"></a>Notes  
 Le type décrit un objet de type non spécifié `T3` qui peut servir d’itérateur inverse pour la séquence contrôlée.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_multiset_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c" reversed   
    Mymultiset::reverse_iterator rit = c1.rbegin();   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<cliext/set >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [multiset::const_iterator (STL/CLR)](../dotnet/multiset-const-iterator-stl-clr.md)   
 [multiset::const_reverse_iterator (STL/CLR)](../dotnet/multiset-const-reverse-iterator-stl-clr.md)   
 [multiset::iterator (STL/CLR)](../dotnet/multiset-iterator-stl-clr.md)