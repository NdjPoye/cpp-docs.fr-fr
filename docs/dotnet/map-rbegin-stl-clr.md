---
title: "map::rbegin (STL/CLR) | Microsoft Docs"
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
  - "cliext::map::rbegin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre rbegin [STL/CLR]"
ms.assetid: bd7165a3-561f-48d4-9791-7aaafc2cf3a5
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# map::rbegin (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Désigne le début de la séquence contrôlée inversée.  
  
## Syntaxe  
  
```  
reverse_iterator rbegin();  
```  
  
## Notes  
 La fonction membre renvoie un Itérateur inverse qui désigne le dernier élément de la séquence contrôlée ou la position juste après le début d'une séquence vide.  Par conséquent, il désigne le `beginning` de la séquence inverse.  Vous l'utilisez pour obtenir un itérateur qui désigne le début `current` de la séquence contrôlée vue dans l'ordre inverse, mais son état peut changer si la longueur de la séquence contrôlée change.  
  
## Exemple  
  
```  
// cliext_map_rbegin.cpp   
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
  
// inspect first two items in reversed sequence   
    Mymap::reverse_iterator rit = c1.rbegin();   
    System::Console::WriteLine("*rbegin() = [{0} {1}]",   
        rit->first, rit->second);   
    ++rit;   
    System::Console::WriteLine("*++rbegin() = [{0} {1}]",   
        rit->first, rit->second);   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
**\*rbegin\(\) \= \[c 3\]**  
**\*\+\+rbegin\(\) \= \[b 2\]**   
## Configuration requise  
 **En\-tête :** \<cliext\/map\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [map](../dotnet/map-stl-clr.md)   
 [map::begin](../dotnet/map-begin-stl-clr.md)   
 [map::end](../dotnet/map-end-stl-clr.md)   
 [map::rend](../dotnet/map-rend-stl-clr.md)