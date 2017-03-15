---
title: "multimap::equal_range (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multimap::equal_range"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre equal_range [STL/CLR]"
ms.assetid: f1008d89-7442-429b-9eca-4ef7ee704766
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# multimap::equal_range (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Recherche la plage qui correspond à une clé spécifiée.  
  
## Syntaxe  
  
```  
pair_iter_iter equal_range(key_type _Keyval);  
```  
  
#### Paramètres  
 `_Keyval`  
 Valeur clé à rechercher.  
  
## Notes  
 La méthode retourne une paire d'itérateurs `-` [multimap::lower\_bound](../dotnet/multimap-lower-bound-stl-clr.md)`(``_Keyval``),` [multimap::upper\_bound](../dotnet/multimap-upper-bound-stl-clr.md)`(``_Keyval``)`.  Vous l'utilisez pour déterminer la plage d'éléments actuellement dans la séquence contrôlée qui correspondent à une clé spécifiée.  
  
## Exemple  
  
```  
// cliext_multimap_equal_range.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
typedef Mymultimap::pair_iter_iter Pairii;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// display results of failed search   
    Pairii pair1 = c1.equal_range(L'x');   
    System::Console::WriteLine("equal_range(L'x') empty = {0}",   
        pair1.first == pair1.second);   
  
// display results of successful search   
    pair1 = c1.equal_range(L'b');   
    for (; pair1.first != pair1.second; ++pair1.first)   
        System::Console::Write(" [{0} {1}]",   
            pair1.first->first, pair1.first->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
**gamme\_egale \(L'x'\) vide \= Vrai**  
 **\[b 2\]**   
## Configuration requise  
 **En\-tête :** \<cliext\/map\>  
  
 **Espace de nom** cliext  
  
## Voir aussi  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multimap::count](../dotnet/multimap-count-stl-clr.md)   
 [multimap::find](../dotnet/multimap-find-stl-clr.md)   
 [multimap::lower\_bound](../dotnet/multimap-lower-bound-stl-clr.md)   
 [multimap::upper\_bound](../dotnet/multimap-upper-bound-stl-clr.md)