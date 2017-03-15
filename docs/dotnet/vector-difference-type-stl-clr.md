---
title: "vector::difference_type (STL/CLR) | Microsoft Docs"
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
  - "cliext::vector::difference_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "difference_type (membre) (STL/CLR)"
ms.assetid: 1e47c569-107b-4a44-adf4-b1473e1f8d4c
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# vector::difference_type (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les types d'une distance signée entre deux éléments.  
  
## Syntaxe  
  
```  
typedef int difference_type;  
```  
  
## Notes  
 Le type décrit un compte d'éléments signés.  
  
## Exemple  
  
```  
// cliext_vector_difference_type.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    cliext::vector<wchar_t>::difference_type diff = 0;   
    for (cliext::vector<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it) ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
  
// compute negative difference   
    diff = 0;   
    for (cliext::vector<wchar_t>::iterator it = c1.end();   
        it != c1.begin(); --it) --diff;   
    System::Console::WriteLine("begin()-end() = {0}", diff);   
    return (0);   
    }  
  
```  
  
  **a b c**  
**end\(\)\-begin\(\) \= 3**  
**begin\(\)\-end\(\) \= \-3**   
## Configuration requise  
 **En\-tête:** \<cliext\/vector\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [vecteur](../dotnet/vector-stl-clr.md)   
 [vector::size\_type](../dotnet/vector-size-type-stl-clr.md)