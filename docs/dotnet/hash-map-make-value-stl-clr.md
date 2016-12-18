---
title: "hash_map::make_value (STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_map::make_value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_value (membre) (STL/CLR)"
ms.assetid: 1fcdcacc-5edf-46b7-9481-9a4aef32b025
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_map::make_value (STL/CLR)
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
// cliext_hash_map_make_value.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    c1.insert(Myhash_map::make_value(L'a', 1));   
    c1.insert(Myhash_map::make_value(L'b', 2));   
    c1.insert(Myhash_map::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**   
## Configuration requise  
 **En\-tête :** \<cliext\/hash\_map\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_map::key\_type](../dotnet/hash-map-key-type-stl-clr.md)   
 [hash\_map::mapped\_type](../dotnet/hash-map-mapped-type-stl-clr.md)   
 [hash\_map::value\_type](../dotnet/hash-map-value-type-stl-clr.md)