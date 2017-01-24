---
title: "list::size_type (STL/CLR) | Microsoft Docs"
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
  - "cliext::list::size_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "size_type (membre) (STL/CLR)"
ms.assetid: bfdf869f-fd7e-47b4-9ce9-68f7146dc3ed
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# list::size_type (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le type d'une distance signée entre deux éléments.  
  
## Syntaxe  
  
```  
typedef int size_type;  
```  
  
## Notes  
 Le type décrit un décompte d'élément non négatif.  
  
## Exemple  
  
```  
// cliext_list_size_type.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    cliext::list<wchar_t>::size_type diff = 0;   
    for (cliext::list<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
    return (0);   
    }  
  
```  
  
  **a b c**  
**end\(\)\-begin\(\) \= 3**   
## Configuration requise  
 **En tête:** \<cliext\/list\>  
  
 **Espace de nom:** cliext  
  
## Voir aussi  
 [list](../dotnet/list-stl-clr.md)   
 [list::empty](../dotnet/list-empty-stl-clr.md)