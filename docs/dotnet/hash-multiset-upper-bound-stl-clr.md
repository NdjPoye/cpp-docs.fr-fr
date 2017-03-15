---
title: "hash_multiset::upper_bound (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multiset::upper_bound"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre upper_bound [STL/CLR]"
ms.assetid: d5be0d79-ae60-42bb-8a53-051bc374407d
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# hash_multiset::upper_bound (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Finds end of range that matches a specified key.  
  
## Syntaxe  
  
```  
iterator upper_bound(key_type key);  
```  
  
#### Paramètres  
 key  
 Key value to search for.  
  
## Notes  
 The member function determines the last element `X` in the controlled sequence that hashes to the same bucket as `key` and has equivalent ordering to `key`.  If no such element exists, or if `X` is the last element in the controlled sequence, it returns [hash\_multiset::end](../dotnet/hash-multiset-end-stl-clr.md)`()`; otherwise it returns an iterator that designates the first element beyond `X`.  You use it to locate the end of a sequence of elements currently in the controlled sequence that match a specified key.  
  
## Exemple  
  
```  
// cliext_hash_multiset_upper_bound.cpp   
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
  
    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",   
        c1.upper_bound(L'x') == c1.end());   
  
    System::Console::WriteLine("*upper_bound(L'a') = {0}",   
        *c1.upper_bound(L'a'));   
    System::Console::WriteLine("*upper_bound(L'b') = {0}",   
        *c1.upper_bound(L'b'));   
    return (0);   
    }  
  
```  
  
  **a b c**  
**upper\_bound\(L'x'\)\=\=end\(\) \= True**  
**\*upper\_bound\(L'a'\) \= b**  
**\*upper\_bound\(L'b'\) \= c**   
## Configuration requise  
 **Header:** \<cliext\/hash\_set\>  
  
 **Namespace:** cliext  
  
## Voir aussi  
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_multiset::count](../dotnet/hash-multiset-count-stl-clr.md)   
 [hash\_multiset::equal\_range](../dotnet/hash-multiset-equal-range-stl-clr.md)   
 [hash\_multiset::find](../dotnet/hash-multiset-find-stl-clr.md)   
 [hash\_multiset::lower\_bound](../dotnet/hash-multiset-lower-bound-stl-clr.md)