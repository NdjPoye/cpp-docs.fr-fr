---
title: "hash_multiset::size (STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_multiset::size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre size [STL/CLR]"
ms.assetid: 45f1f35e-35c4-4e39-8485-0786c1de22e3
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_multiset::size (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Compte le nombre d'éléments.  
  
## Syntaxe  
  
```  
size_type size();  
```  
  
## Notes  
 La méthode retourne la longueur de la séquence contrôlée.  Vous l'utilisez pour déterminer le nombre d'éléments figurant actuellement dans la séquence contrôlée.  Si tout ce dont vous vous souciez est si la séquence a une taille différente de zéro, consultez [hash\_multiset::empty](../dotnet/hash-multiset-empty-stl-clr.md)`()`.  
  
## Exemple  
  
```  
// cliext_hash_multiset_size.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0} after clearing", c1.size());   
  
// add elements and clear again   
    c1.insert(L'a');   
    c1.insert(L'b');   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
  
```  
  
  **a b c**  
**size\(\) \= 3 à partir de 3**  
**size\(\) \= 0 après libération**  
**size\(\) \= 2 après avoir ajouté 2**   
## Configuration requise  
 **En\-tête :** \<cliext\/hash\_set\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_multiset::empty](../dotnet/hash-multiset-empty-stl-clr.md)