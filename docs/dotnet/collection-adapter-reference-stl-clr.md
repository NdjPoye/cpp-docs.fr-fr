---
title: "collection_adapter::reference (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::collection_adapter::reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre de référence (STL/CLR)"
ms.assetid: 8a624db2-2ab0-4f8c-8dcb-beb190e474ca
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# collection_adapter::reference (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Type d'une référence à un élément.  
  
## Syntaxe  
  
```  
typedef value_type% reference;  
```  
  
## Notes  
 The type describes a reference to an element.  
  
## Exemple  
  
```  
// cliext_collection_adapter_reference.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    Mycoll::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        {   // get a reference to an element   
        Mycoll::reference ref = *it;   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**   
## Configuration requise  
 **Header:** \<cliext\/adapter\>  
  
 **Namespace:** cliext  
  
## Voir aussi  
 [collection\_adapter](../dotnet/collection-adapter-stl-clr.md)   
 [collection\_adapter::value\_type](../dotnet/collection-adapter-value-type-stl-clr.md)