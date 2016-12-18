---
title: "map::count (STL/CLR) | Microsoft Docs"
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
  - "cliext::map::Count"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre count [STL/CLR]"
ms.assetid: 835f5b11-cb15-4a0b-8808-cd9b36c83e0b
caps.latest.revision: 18
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# map::count (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Finds the number of elements matching a specified key.  
  
## Syntaxe  
  
```  
size_type count(key_type key);  
```  
  
#### Paramètres  
 key  
 Key value to search for.  
  
## Notes  
 The member function returns the number of elements in the controlled sequence that have equivalent ordering with `key`.  Vous l'utilisez pour déterminer le nombre d'éléments actuellement dans la séquence contrôlée qui correspondent à une clé spécifiée.  
  
## Exemple  
  
```  
// cliext_map_count.cpp   
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
  
    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));   
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));   
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
**count\(L'A'\) \= 0**  
**count\(L'b'\) \= 1**  
**count\(L'C'\) \= 0**   
## Configuration requise  
 **Header:** \<cliext\/map\>  
  
 **Namespace:** cliext  
  
## Voir aussi  
 [map](../dotnet/map-stl-clr.md)   
 [map::equal\_range](../dotnet/map-equal-range-stl-clr.md)