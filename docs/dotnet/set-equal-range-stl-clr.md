---
title: "set::equal_range (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::set::equal_range"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre equal_range [STL/CLR]"
ms.assetid: f0b20a65-f37a-44b1-a291-09c33c10c355
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# set::equal_range (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Recherche la plage qui correspond à une clé spécifiée.  
  
## Syntaxe  
  
```  
cliext::pair<iterator, iterator> equal_range(key_type key);  
```  
  
#### Paramètres  
 key  
 Valeur clé à rechercher.  
  
## Notes  
 La fonction membre retourne une paire d'itérateurs `cliext::pair<iterator, iterator>(` [set::lower\_bound](../dotnet/set-lower-bound-stl-clr.md)`(``key``),` [set::upper\_bound](../dotnet/set-upper-bound-stl-clr.md)`(``key``))`.  Vous l'utilisez pour déterminer la plage d'éléments actuellement dans la séquence contrôlée qui correspondent à une clé spécifiée.  
  
## Exemple  
  
```  
// cliext_set_equal_range.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
typedef Myset::pair_iter_iter Pairii;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display results of failed search   
    Pairii pair1 = c1.equal_range(L'x');   
    System::Console::WriteLine("equal_range(L'x') empty = {0}",   
        pair1.first == pair1.second);   
  
// display results of successful search   
    pair1 = c1.equal_range(L'b');   
    for (; pair1.first != pair1.second; ++pair1.first)   
        System::Console::Write(" {0}", *pair1.first);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
**gamme\_egale \(L'x'\) vide \= Vrai**  
 **b**   
## Configuration requise  
 **En\-tête :** \<cliext\/set\>  
  
 **Espace de nommage:** cliext  
  
## Voir aussi  
 [set](../dotnet/set-stl-clr.md)   
 [set::count](../dotnet/set-count-stl-clr.md)   
 [set::find](../dotnet/set-find-stl-clr.md)   
 [set::lower\_bound](../dotnet/set-lower-bound-stl-clr.md)   
 [set::upper\_bound](../dotnet/set-upper-bound-stl-clr.md)