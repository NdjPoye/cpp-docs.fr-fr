---
title: "list::value_type (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::value_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "value_type (membre) (STL/CLR)"
ms.assetid: 7013f92e-8ceb-4c99-bb44-6ba13b0d3ef3
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# list::value_type (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le type d'un élément.  
  
## Syntaxe  
  
```  
typedef Value value_type;  
```  
  
## Notes  
 Le type est un synonyme du paramètre de modèle `Value`.  
  
## Exemple  
  
```  
// cliext_list_value_type.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using value_type   
    for (cliext::list<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        {   // store element in value_type object   
        cliext::list<wchar_t>::value_type val = *it;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**   
## Configuration requise  
 **En\-tête :** \<cliext\/list\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [list](../dotnet/list-stl-clr.md)   
 [list::const\_reference](../dotnet/list-const-reference-stl-clr.md)   
 [list::reference](../dotnet/list-reference-stl-clr.md)