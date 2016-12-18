---
title: "hash_multimap::size (STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_multimap::size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre size [STL/CLR]"
ms.assetid: 6937c980-5952-48bf-b411-81ab03b2f940
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_multimap::size (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Compte le nombre d'éléments.  
  
## Syntaxe  
  
```  
size_type size();  
```  
  
## Notes  
 La méthode retourne la longueur de la séquence contrôlée.  Vous l'utilisez pour déterminer le nombre d'éléments figurant actuellement dans la séquence contrôlée.  Si tout ce dont vous vous souciez est si la séquence a une taille différente de zéro, consultez [hash\_multimap::empty](../dotnet/hash-multimap-empty-stl-clr.md)`()`.  
  
## Exemple  
  
```  
// cliext_hash_multimap_size.cpp   
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
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0} after clearing", c1.size());   
  
// add elements and clear again   
    c1.insert(Myhash_multimap::make_value(L'd', 4));   
    c1.insert(Myhash_multimap::make_value(L'e', 5));   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
**size\(\) \= 0 après libération**  
**size\(\) \= 2 après avoir ajouté 2**   
## Configuration requise  
 **En\-tête :** \<cliext\/hash\_map\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)   
 [hash\_multimap::empty](../dotnet/hash-multimap-empty-stl-clr.md)