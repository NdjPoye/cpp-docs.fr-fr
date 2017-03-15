---
title: "stack::difference_type (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::stack::difference_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "difference_type (membre) (STL/CLR)"
ms.assetid: 953a0d2a-873c-41e7-b792-15cf18e7a5b4
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# stack::difference_type (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les types d'une distance signée entre deux éléments.  
  
## Syntaxe  
  
```  
typedef int difference_type;  
```  
  
## Notes  
 Le type décrit un nombre non négatif d'éléments.  
  
## Exemple  
  
```  
// cliext_stack_difference_type.cpp   
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
  
// compute negative difference   
    Mystack::difference_type diff = c1.size();   
    c1.push(L'd');   
    c1.push(L'e');   
    diff -= c1.size();   
    System::Console::WriteLine("pushing 2 = {0}", diff);   
  
// compute positive difference   
    diff = c1.size();   
    c1.pop();   
    c1.pop();   
    c1.pop();   
    diff -= c1.size();   
    System::Console::WriteLine("popping 3 = {0}", diff);   
    return (0);   
    }  
  
```  
  
  **a b c**  
**poussant 2 \= \-2**  
**dépilant 3 \= 3**   
## Configuration requise  
 **En\-tête :** \<cliext\/stack\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [pile](../dotnet/stack-stl-clr.md)   
 [stack::size\_type](../dotnet/stack-size-type-stl-clr.md)