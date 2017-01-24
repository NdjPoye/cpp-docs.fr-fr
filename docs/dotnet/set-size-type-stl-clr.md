---
title: "set::size_type (STL/CLR) | Microsoft Docs"
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
  - "cliext::set::size_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "size_type (membre) (STL/CLR)"
ms.assetid: df478b73-b2e6-4add-b22a-39a216753037
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# set::size_type (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le type d'une distance signée entre deux éléments.  
  
## Syntaxe  
  
```  
typedef int size_type;  
```  
  
## Notes  
 Le type décrit un nombre non négatif d'éléments.  
  
## Exemple  
  
```  
// cliext_set_size_type.cpp   
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
  
// compute positive difference   
    Myset::size_type diff = 0;   
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)   
        ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
    return (0);   
    }  
  
```  
  
  **a b c**  
**end\(\)\-begin\(\) \= 3**   
## Configuration requise  
 **En\-tête :** \<cliext\/set\>  
  
 **Espace de nommage :** cliext  
  
## Voir aussi  
 [set](../dotnet/set-stl-clr.md)   
 [set::empty](../dotnet/set-empty-stl-clr.md)