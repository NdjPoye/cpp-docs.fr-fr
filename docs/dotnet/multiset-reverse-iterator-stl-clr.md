---
title: "multiset::reverse_iterator (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multiset::reverse_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reverse_iterator (membre) (STL/CLR)"
ms.assetid: dde6ad36-ca59-4728-aa53-e3d117eb4f48
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# multiset::reverse_iterator (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le type d'un itérateur inversé pour la séquence contrôlée.  
  
## Syntaxe  
  
```  
typedef T3 reverse_iterator;  
```  
  
## Notes  
 Le type décrit un objet de type non spécifié `T3` qui peut servir d'itérateur inversé pour la séquence contrôlée.  
  
## Exemple  
  
```  
// cliext_multiset_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c" reversed   
    Mymultiset::reverse_iterator rit = c1.rbegin();   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **c b a**   
## Configuration requise  
 **En\-tête :** \<cliext\/set\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::const\_iterator](../dotnet/multiset-const-iterator-stl-clr.md)   
 [multiset::const\_reverse\_iterator](../dotnet/multiset-const-reverse-iterator-stl-clr.md)   
 [multiset::iterator](../dotnet/multiset-iterator-stl-clr.md)