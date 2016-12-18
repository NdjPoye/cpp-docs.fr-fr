---
title: "hash_multiset::rend (STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_multiset::rend"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre rend [STL/CLR]"
ms.assetid: 6d007ac9-18cc-4b51-8384-a4ff65d23e97
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_multiset::rend (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Désigne la fin de la séquence contrôlée inversée.  
  
## Syntaxe  
  
```  
reverse_iterator rend();  
```  
  
## Notes  
 La fonction membre retourne un membre itérateur inverse qui pointe juste au delà du début de la séquence contrôlée.  Par conséquent, il désigne le `end` de la séquence inverse.  Vous l'utilisez pour obtenir un itérateur qui désigne la fin `current` de la séquence contrôlée vue dans l'ordre inverse, mais son état peut changer si la longueur de la séquence contrôlée change.  
  
## Exemple  
  
```  
// cliext_hash_multiset_rend.cpp   
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
  
// inspect first two items   
    Myhash_multiset::reverse_iterator rit = c1.rend();   
    --rit;   
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);   
    System::Console::WriteLine("*--rend() = {0}", *++rit);   
    return (0);   
    }  
  
```  
  
  **a b c**  
**\*\-\- \-\-rend\(\) \= b**  
**\*\-\-rend\(\) \= a**   
## Configuration requise  
 **En\-tête :** \<cliext\/hash\_set\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_multiset::begin](../dotnet/hash-multiset-begin-stl-clr.md)   
 [hash\_multiset::end](../dotnet/hash-multiset-end-stl-clr.md)   
 [hash\_multiset::rbegin](../dotnet/hash-multiset-rbegin-stl-clr.md)