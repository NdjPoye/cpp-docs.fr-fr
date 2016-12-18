---
title: "map::const_reverse_iterator (STL/CLR) | Microsoft Docs"
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
  - "cliext::map::const_reverse_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_reverse_iterator (membre) (STL/CLR)"
ms.assetid: 056a765c-4f59-4bd8-99f4-c308a6f29c12
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# map::const_reverse_iterator (STL/CLR)
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
// cliext_map_const_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]" reversed   
    Mymap::const_reverse_iterator crit = c1.rbegin();   
    for (; crit != c1.rend(); ++crit)   
        System::Console::Write(" [{0} {1}]", crit->first, crit->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[c 3\] \[b 2\] \[a 1\]**   
## Configuration requise  
 **En\-tête :** \<cliext\/map\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [map](../dotnet/map-stl-clr.md)   
 [map::reverse\_iterator](../dotnet/map-reverse-iterator-stl-clr.md)