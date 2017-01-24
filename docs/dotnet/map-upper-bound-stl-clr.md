---
title: "map::upper_bound (STL/CLR) | Microsoft Docs"
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
  - "cliext::map::upper_bound"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre upper_bound [STL/CLR]"
ms.assetid: d772b4a8-d0dc-439a-8b5b-3c91836d9256
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# map::upper_bound (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Recherche la fin de la plage qui correspond à une clé spécifiée.  
  
## Syntaxe  
  
```  
iterator upper_bound(key_type key);  
```  
  
#### Paramètres  
 key  
 Valeur clé à rechercher.  
  
## Notes  
 La fonction membre détermine le dernier élément `X` dans la séquence contrôlée dont le classement est équivalent à `key`.  Si cet élément n'existe pas, ou si `X` est le dernier éléments de la séquence contrôlée, cela retourne [map::end](../dotnet/map-end-stl-clr.md)`()`; sinon cela renvoie un itérateur qui indique le premier élément au delà de `X`.  Vous l'utilisez pour rechercher le la fin d'une séquence d'éléments figurant actuellement dans la séquence contrôlée qui correspondent à la clé spécifiée.  
  
## Exemple  
  
```  
// cliext_map_upper_bound.cpp   
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
  
    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",   
        c1.upper_bound(L'x') == c1.end());   
  
    Mymap::iterator it = c1.upper_bound(L'a');   
    System::Console::WriteLine("*upper_bound(L'a') = [{0} {1}]",   
        it->first, it->second);   
    it = c1.upper_bound(L'b');   
    System::Console::WriteLine("*upper_bound(L'b') = [{0} {1}]",   
        it->first, it->second);   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
**upper\_bound\(L'x'\)\=\=end\(\) \= True**  
**\*upper\_bound\(L'a'\) \= \[b 2\]**  
**\*upper\_bound\(L'b'\) \= \[c 3\]**   
## Configuration requise  
 **En\-tête :** \<cliext\/map\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [map](../dotnet/map-stl-clr.md)   
 [map::count](../dotnet/map-count-stl-clr.md)   
 [map::equal\_range](../dotnet/map-equal-range-stl-clr.md)   
 [map::find](../dotnet/map-find-stl-clr.md)   
 [map::lower\_bound](../dotnet/map-lower-bound-stl-clr.md)