---
title: "stack::const_reference (STL/CLR) | Microsoft Docs"
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
  - "cliext::stack::const_reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_reference (membre) (STL/CLR)"
ms.assetid: 36be8e21-f2b8-4c2e-a00e-276e73f0d802
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# stack::const_reference (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Type d'une référence constante à un élément.  
  
## Syntaxe  
  
```  
typedef value_type% const_reference;  
```  
  
## Notes  
 The type describes a constant reference to an element.  
  
## Exemple  
  
```  
// cliext_stack_const_reference.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display reversed contents " c b a"   
    for (; !c1.empty(); c1.pop())   
        {   // get a const reference to an element   
        Mystack::const_reference cref = c1.top();   
        System::Console::Write(" {0}", cref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **c b a**   
## Configuration requise  
 **En\-tête :** \<cliext\/stack\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [pile](../dotnet/stack-stl-clr.md)   
 [stack::reference](../dotnet/stack-reference-stl-clr.md)   
 [stack::value\_type](../dotnet/stack-value-type-stl-clr.md)