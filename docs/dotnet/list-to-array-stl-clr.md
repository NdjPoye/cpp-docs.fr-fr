---
title: List::to_array (STL/CLR) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list::to_array
dev_langs: C++
helpviewer_keywords: to_array member [STL/CLR]
ms.assetid: 3ea7b90c-127b-43cd-804b-019b86b77582
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 113c6330e9fd3e82c83e2d4bf018e4ea101c64c6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="listtoarray-stlclr"></a>list::to_array (STL/CLR)
Copie de la séquence contrôlée vers un nouveau tableau.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
cli::array<Value>^ to_array();  
```  
  
## <a name="remarks"></a>Remarques  
 La fonction membre retourne un tableau contenant la séquence contrôlée. Il permet d’obtenir une copie de la séquence contrôlée sous forme de tableau.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_list_to_array.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// copy the container and modify it   
    cli::array<wchar_t>^ a1 = c1.to_array();   
  
    c1.push_back(L'd');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c d  
a b c  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<cliext/liste >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [list (STL/CLR)](../dotnet/list-stl-clr.md)