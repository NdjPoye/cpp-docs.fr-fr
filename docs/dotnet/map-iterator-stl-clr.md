---
title: "map::iterator (STL/CLR) | Microsoft Docs"
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
  - "cliext::map::iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iterator (membre) (STL/CLR)"
ms.assetid: b2953b9b-0e6d-49f3-a28f-47d04d16d5f6
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# map::iterator (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Type d'un itérateur pour la séquence contrôlée.  
  
## Syntaxe  
  
```  
typedef T1 iterator;  
```  
  
## Notes  
 Le type décrit un objet de type non spécifié `T1` qui peut servir d'itérateur bidirectionnel pour la séquence contrôlée.  
  
## Exemple  
  
```  
// cliext_map_iterator.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    Mymap::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" [{0} {1}]", it->first, it->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**   
## Configuration requise  
 **En\-tête :** \<cliext\/map\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [map](../dotnet/map-stl-clr.md)   
 [map::const\_iterator](../dotnet/map-const-iterator-stl-clr.md)