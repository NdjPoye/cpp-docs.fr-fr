---
title: "hash_multimap::const_reference (STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_multimap::const_reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_reference (membre) (STL/CLR)"
ms.assetid: c8e461bb-64cd-4868-a63e-77c197084431
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_multimap::const_reference (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Type d'une référence constante à un élément.  
  
## Syntaxe  
  
```  
typedef value_type% const_reference;  
```  
  
## Notes  
 Ce type décrit une référence constante à un élément.  
  
## Exemple  
  
```  
// cliext_hash_multimap_const_reference.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    Myhash_multimap::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        {   // get a const reference to an element   
        Myhash_multimap::const_reference cref = *cit;   
        System::Console::Write(" [{0} {1}]", cref->first, cref->second);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**   
## Configuration requise  
 **En\-tête :** \<cliext\/hash\_map\>  
  
 **Espace de noms :** cliext  
  
## Voir aussi  
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)   
 [hash\_multimap::reference](../dotnet/hash-multimap-reference-stl-clr.md)   
 [hash\_multimap::value\_type](../dotnet/hash-multimap-value-type-stl-clr.md)