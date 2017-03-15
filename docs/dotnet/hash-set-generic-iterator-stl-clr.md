---
title: "hash_set::generic_iterator (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_set::generic_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "generic_iterator (membre) (STL/CLR)"
ms.assetid: 9d6ac06d-d70c-4343-b959-553885a9cb53
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# hash_set::generic_iterator (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le type d'un itérateur pour une utilisation avec l'interface générique pour le conteneur.  
  
## Syntaxe  
  
```  
typedef Microsoft::VisualC::StlClr::Generic::  
    ContainerBidirectionalIterator<generic_value>  
    generic_iterator;  
```  
  
## Notes  
 Le type décrit un itérateur générique qui peut être utilisé avec l'interface générique pour cette classe conteneur de modèle.  
  
## Exemple  
  
```  
// cliext_hash_set_generic_iterator.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Myhash_set::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// get an element and display it   
    Myhash_set::generic_iterator gcit = gc1->begin();   
    Myhash_set::generic_value gcval = *gcit;   
    System::Console::WriteLine(" {0}", gcval);   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b c**  
 **a**   
## Configuration requise  
 **En\-tête:** \<cliext\/hash\_set\>  
  
 **Espace pour le nom :** cliext  
  
## Voir aussi  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::generic\_container](../dotnet/hash-set-generic-container-stl-clr.md)