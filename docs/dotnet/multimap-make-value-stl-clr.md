---
title: "multimap::make_value (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multimap::make_value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_value (membre) (STL/CLR)"
ms.assetid: 9ae5ace0-e529-4247-8cd6-4e96c0611a75
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# multimap::make_value (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Construit un objet valeur.  
  
## Syntaxe  
  
```  
static value_type make_value(key_type key, mapped_type mapped);  
```  
  
#### Paramètres  
 key  
 Valeur clé à utiliser.  
  
 Mappé  
 Valeur mappé à rechercher.  
  
## Notes  
 La fonction membre retourne un objet `value_type` dont la clé est `key` et dont la valeur mappée `mapped`.  Vous l'utilisez pour composer un objet utilisable avec plusieurs autres méthodes.  
  
## Exemple  
  
```  
// cliext_multimap_make_value.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
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
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**   
## Configuration requise  
 **En\-tête:** \<cliext\/map\>  
  
 **Espace pour le nom :** cliext  
  
## Voir aussi  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multimap::key\_type](../dotnet/multimap-key-type-stl-clr.md)   
 [multimap::mapped\_type](../dotnet/multimap-mapped-type-stl-clr.md)   
 [multimap::value\_type](../dotnet/multimap-value-type-stl-clr.md)