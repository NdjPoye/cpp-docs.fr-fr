---
title: Set::rbegin (STL/CLR) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::set::rbegin
dev_langs:
- C++
helpviewer_keywords:
- rbegin member [STL/CLR]
ms.assetid: b9da72dc-0b75-489e-b179-74c27a4bcfb7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7636c2f3722ab6e6da86de36e9876c39c047b894
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="setrbegin-stlclr"></a>set::rbegin (STL/CLR)
Désigne le début de la séquence contrôlée inverse.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
reverse_iterator rbegin();  
```  
  
## <a name="remarks"></a>Notes  
 La fonction membre retourne un itérateur inverse qui désigne le dernier élément de la séquence contrôlée, ou juste après le début d’une séquence vide. Par conséquent, il désigne le `beginning` de la séquence inverse. Vous l’utilisez pour obtenir un itérateur qui désigne le `current` début de la séquence contrôlée vue dans l’ordre inverse, mais son état peut changer si la longueur de la séquence contrôlée change.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_set_rbegin.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items in reversed sequence   
    Myset::reverse_iterator rit = c1.rbegin();   
    System::Console::WriteLine("*rbegin() = {0}", *rit);   
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*rbegin() = c  
*++rbegin() = b  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<cliext/set >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [Set (STL/CLR)](../dotnet/set-stl-clr.md)   
 [Set::Begin (STL/CLR)](../dotnet/set-begin-stl-clr.md)   
 [Set::end (STL/CLR)](../dotnet/set-end-stl-clr.md)   
 [set::rend (STL/CLR)](../dotnet/set-rend-stl-clr.md)