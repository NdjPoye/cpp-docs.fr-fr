---
title: "hash_multiset::const_reverse_iterator (STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_multiset::const_reverse_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_reverse_iterator (membre) (STL/CLR)"
ms.assetid: 55214d17-94c3-4517-8996-ae28ff37225b
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_multiset::const_reverse_iterator (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le type d'un itérateur inverse constant pour la séquence contrôlée.  
  
## Syntaxe  
  
```  
typedef T4 const_reverse_iterator;  
```  
  
## Notes  
 Le type décrit un objet de type non spécifié `T4` qui peut servir d'itérateur inverse constant pour la séquence contrôlée.  
  
## Exemple  
  
```  
// cliext_hash_multiset_const_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c" reversed   
    Myhash_multiset::const_reverse_iterator crit = c1.rbegin();   
    for (; crit != c1.rend(); ++crit)   
        System::Console::Write(" {0}", *crit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **c b a**   
## Configuration requise  
 **En\-tête :** \<cliext\/hash\_set\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_multiset::reverse\_iterator](../dotnet/hash-multiset-reverse-iterator-stl-clr.md)