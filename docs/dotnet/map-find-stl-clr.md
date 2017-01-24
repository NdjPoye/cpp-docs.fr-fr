---
title: "map::find (STL/CLR) | Microsoft Docs"
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
  - "cliext::map::find"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre find [STL/CLR]"
ms.assetid: 779dcbee-d584-4fbd-b788-481e094ece9d
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# map::find (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Recherche un élément qui correspond à une clé spécifiée.  
  
## Syntaxe  
  
```  
iterator find(key_type key);  
```  
  
#### Paramètres  
 key  
 Valeur clé à rechercher.  
  
## Notes  
 Si au moins un élément dans la séquence contrôlée à un classement équivalent à `key`, la fonction membre retourne un itérateur indiquant un de ces éléments ; sinon il renvoie [map::end](../dotnet/map-end-stl-clr.md)`()`.  Vous l'utilisez pour localiser un élément actuellement dans la séquence contrôlée qui correspond à une clé spécifiée.  
  
## Exemple  
  
```  
// cliext_map_find.cpp   
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
  
    System::Console::WriteLine("find {0} = {1}",   
        L'A', c1.find(L'A') != c1.end());   
  
    Mymap::iterator it = c1.find(L'b');   
    System::Console::WriteLine("find {0} = [{1} {2}]",   
        L'b', it->first, it->second);   
  
    System::Console::WriteLine("find {0} = {1}",   
        L'C', c1.find(L'C') != c1.end());   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
**find A \= False**  
**find b \= \[b 2\]**  
**find C \= False**   
## Description  
 Notez que `find` ne garantit pas quel élément il trouve parmi plusieurs.  
  
## Configuration requise  
 **En\-tête :** \<cliext\/map\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [map](../dotnet/map-stl-clr.md)   
 [map::equal\_range](../dotnet/map-equal-range-stl-clr.md)   
 [map::lower\_bound](../dotnet/map-lower-bound-stl-clr.md)   
 [map::upper\_bound](../dotnet/map-upper-bound-stl-clr.md)