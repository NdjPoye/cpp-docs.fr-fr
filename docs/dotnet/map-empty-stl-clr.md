---
title: "map::empty (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::map::empty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre empty [STL/CLR]"
ms.assetid: ce41d37a-2896-48df-87ea-d3f3b3e5ab45
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# map::empty (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si aucun élément n'est présent.  
  
## Syntaxe  
  
```  
bool empty();  
```  
  
## Notes  
 La fonction membre retourne vrai pour une séquence contrôlée vide.  Équivaut à [map::size](../dotnet/map-size-stl-clr.md)`() == 0`.  Vous l'utilisez pour déterminer si le tableau associatif \(map\) est vide.  
  
## Exemple  
  
```  
// cliext_map_empty.cpp   
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
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
**size\(\) \= 3**  
**vide\(\) \= faux**  
**taille\(\) \= 0**  
**vide\(\) \= Vrai**   
## Configuration requise  
 **En\-tête :** \<cliext\/map\>  
  
 **Espace de nommage** cliext  
  
## Voir aussi  
 [map](../dotnet/map-stl-clr.md)   
 [map::size](../dotnet/map-size-stl-clr.md)