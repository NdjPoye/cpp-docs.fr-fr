---
title: "deque::reverse_iterator (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::deque::reverse_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reverse_iterator (membre) (STL/CLR)"
ms.assetid: 82bdfda7-496d-4f8a-8eb8-96bee83b5708
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# deque::reverse_iterator (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The type of a reverse iterator for the controlled sequence.  
  
## Syntaxe  
  
```  
typedef T3 reverse_iterator;  
```  
  
## Notes  
 The type describes an object of unspecified type `T3` that can serve as a reverse iterator for the controlled sequence.  
  
## Exemple  
  
```  
// cliext_deque_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" reversed   
    cliext::deque<wchar_t>::reverse_iterator rit = c1.rbegin();   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
  
// alter first element and redisplay   
    rit = c1.rbegin();   
    *rit = L'x';   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **c b a**  
 **x b a**   
## Configuration requise  
 **Header:** \<cliext\/deque\>  
  
 **Namespace:** cliext  
  
## Voir aussi  
 [deque](../dotnet/deque-stl-clr.md)   
 [deque::const\_iterator](../dotnet/deque-const-iterator-stl-clr.md)   
 [deque::const\_reverse\_iterator](../dotnet/deque-const-reverse-iterator-stl-clr.md)   
 [deque::iterator](../dotnet/deque-iterator-stl-clr.md)