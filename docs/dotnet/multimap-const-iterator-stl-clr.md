---
title: multimap::const_iterator (STL/CLR) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multimap::const_iterator
dev_langs:
- C++
helpviewer_keywords:
- const_iterator member [STL/CLR]
ms.assetid: 13b166c9-1dcd-4ff9-b1da-3b8ffa463735
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5cf44af574b5e39db250a2015f01b97d4ab2a1c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="multimapconstiterator-stlclr"></a>multimap::const_iterator (STL/CLR)
Type d'un itérateur constant pour la séquence contrôlée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef T2 const_iterator;  
```  
  
## <a name="remarks"></a>Notes  
 Le type décrit un objet de type non spécifié `T2` qui peut servir d’itérateur bidirectionnel constant pour la séquence contrôlée.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_multimap_const_iterator.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    Mymultimap::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        System::Console::Write(" [{0} {1}]", cit->first, cit->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3]  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<cliext/map >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [multimap::iterator (STL/CLR)](../dotnet/multimap-iterator-stl-clr.md)