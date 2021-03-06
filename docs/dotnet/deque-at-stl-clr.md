---
title: deque::AT (STL/CLR) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::at
dev_langs:
- C++
helpviewer_keywords:
- at member [STL/CLR]
ms.assetid: 9af83d8a-c519-4b2a-a25f-d3dc8bbb87fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8388f6428d31cce2993e7c90db66f430564d347e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="dequeat-stlclr"></a>deque::at (STL/CLR)
Accède à un élément à une position spécifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
reference at(size_type pos);  
```  
  
#### <a name="parameters"></a>Paramètres  
 pos  
 Position de l'élément auquel accéder.  
  
## <a name="remarks"></a>Notes  
 La fonction membre retourne une référence à l’élément de la séquence contrôlée à la position `pos`. Vous l’utilisez pour lire ou écrire un élément dont la position vous connaissez.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_deque_at.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using at   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1.at(i));   
    System::Console::WriteLine();   
  
// change an entry and redisplay   
    c1.at(1) = L'x';   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1[i]);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a x c  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<cliext/deque >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::operator(STL/CLR)](../dotnet/deque-operator-stl-clr.md)