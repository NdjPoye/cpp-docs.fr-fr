---
title: "multiset::clear (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multiset::clear"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre clear [STL/CLR]"
ms.assetid: 63c21716-fa08-47b9-b457-0b76052c5079
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# multiset::clear (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Supprime tous les éléments.  
  
## Syntaxe  
  
```  
void clear();  
```  
  
## Notes  
 La fonction membre appelle efficacement [multiset::erase](../dotnet/multiset-erase-stl-clr.md)`(` [multiset::begin](../dotnet/multiset-begin-stl-clr.md)`(),` [multiset::end](../dotnet/multiset-end-stl-clr.md)`())`.  Vous l'utilisez pour faire en sorte que la séquence contrôlée soit vide.  
  
## Exemple  
  
```  
// cliext_multiset_clear.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// add elements and clear again   
    c1.insert(L'a');   
    c1.insert(L'b');   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
  **a b c**  
**size\(\) \= 0**  
 **a b**  
**size\(\) \= 0**   
## Configuration requise  
 **En\-tête :** \<cliext\/set\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::erase](../dotnet/multiset-erase-stl-clr.md)