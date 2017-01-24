---
title: "hash_set::clear (STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_set::clear"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre clear [STL/CLR]"
ms.assetid: 9f38b72a-5db8-485a-b41a-7d47ac57f4a9
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_set::clear (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Supprime tous les éléments.  
  
## Syntaxe  
  
```  
void clear();  
```  
  
## Notes  
 La fonction membre appelle efficacement [hash\_set::erase](../dotnet/hash-set-erase-stl-clr.md)`(` [hash\_set::begin](../dotnet/hash-set-begin-stl-clr.md)`(),` [hash\_set::end](../dotnet/hash-set-end-stl-clr.md)`())`.  Vous l'utilisez pour faire en sorte que la séquence contrôlée est vide.  
  
## Exemple  
  
```  
// cliext_hash_set_clear.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
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
 **En\-tête:** \<cliext\/hash\_set\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::erase](../dotnet/hash-set-erase-stl-clr.md)