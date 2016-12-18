---
title: "collection_adapter::size_type (STL/CLR) | Microsoft Docs"
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
  - "cliext::collection_adapter::size_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "size_type (membre) (STL/CLR)"
ms.assetid: 3a0270cd-02ec-422f-85e2-577c71871057
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# collection_adapter::size_type (STL/CLR)
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
// cliext_collection_adapter_size_type.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d6x(6, L'x');   
    Mycoll c1(%d6x);   
  
// display initial contents " x x x x x x"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    Mycoll::size_type size = c1.size();   
    System::Console::WriteLine("size() = {0}", size);   
    return (0);   
    }  
  
```  
  
  **x x x x x x**  
**size\(\) \= 6**   
## Configuration requise  
 **En\-tête :** \<cliext\/adapter\>  
  
 **Espace de noms :** cliext  
  
## Voir aussi  
 [collection\_adapter](../dotnet/collection-adapter-stl-clr.md)