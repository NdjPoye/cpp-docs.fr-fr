---
title: "multimap::const_reverse_iterator (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multimap::const_reverse_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_reverse_iterator (membre) (STL/CLR)"
ms.assetid: edc5129e-f2ca-4d3a-a898-365ad0a587e4
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# multimap::const_reverse_iterator (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Type d'un itérateur inverse constant pour la séquence contrôlée.  
  
## Syntaxe  
  
```  
typedef T4 const_reverse_iterator;  
```  
  
## Notes  
 Le type décrit un objet de type non spécifié `T4` qui peut servir d'itérateur inverse constant pour la séquence contrôlée.  
  
## Exemple  
  
```  
// cliext_multimap_const_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]" reversed   
    Mymultimap::const_reverse_iterator crit = c1.rbegin();   
    for (; crit != c1.rend(); ++crit)   
        System::Console::Write(" [{0} {1}]", crit->first, crit->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[c 3\] \[b 2\] \[a 1\]**   
## Configuration requise  
 **En\-tête :** \<cliext\/map\>  
  
 **Espace de nommage:** cliext  
  
## Voir aussi  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multimap::reverse\_iterator](../dotnet/multimap-reverse-iterator-stl-clr.md)