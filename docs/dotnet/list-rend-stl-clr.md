---
title: "list::rend (STL/CLR) | Microsoft Docs"
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
  - "cliext::list::rend"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre rend [STL/CLR]"
ms.assetid: b51030ad-1bca-42b0-b890-db47111d2921
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# list::rend (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Désigne la fin de la séquence contrôlée inversée.  
  
## Syntaxe  
  
```  
reverse_iterator rend();  
```  
  
## Notes  
 La fonction membre retourne un membre itérateur inverse qui pointe uniquement au delà du début de la séquence contrôlée.  Par conséquent, il désigne le `end` de la séquence inverse.  Vous l'utilisez pour obtenir un itérateur qui désigne la fin `current` de la séquence contrôlée vue dans l'ordre inverse, mais son état peut changer si la longueur de la séquence contrôlée change.  
  
## Exemple  
  
```  
// cliext_list_rend.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    cliext::list<wchar_t>::reverse_iterator rit = c1.rend();   
    --rit;   
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);   
    System::Console::WriteLine("*--rend() = {0}", *++rit);   
  
// alter first two items and reinspect   
    *--rit = L'x';   
    *++rit = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
**\*\-\- \-\-rend\(\) \= b**  
**\*\-\-rend\(\) \= a**  
 **y x c**   
## Configuration requise  
 **En\-tête :** \<cliext\/list\>  
  
 **Espace de nommage** cliext  
  
## Voir aussi  
 [list](../dotnet/list-stl-clr.md)   
 [list::begin](../dotnet/list-begin-stl-clr.md)   
 [list::end](../dotnet/list-end-stl-clr.md)   
 [list::rbegin](../dotnet/list-rbegin-stl-clr.md)