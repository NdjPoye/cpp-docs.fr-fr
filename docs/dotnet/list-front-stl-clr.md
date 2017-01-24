---
title: "list::front (STL/CLR) | Microsoft Docs"
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
  - "cliext::list::front"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre front [STL/CLR]"
ms.assetid: ead6aaaa-b518-4a9c-af80-7189bf872cad
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# list::front (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Accède au premier élément.  
  
## Syntaxe  
  
```  
reference front();  
```  
  
## Notes  
 La méthode retourne une référence au premier élément de la séquence contrôlée, qui doit être non vide.  Vous l'utilisez pour lire ou écrire le premier élément, lorsque vous savez qu'il existe.  
  
## Exemple  
  
```  
// cliext_list_front.cpp   
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
  
// inspect first item   
    System::Console::WriteLine("front() = {0}", c1.front());   
  
// alter first item and reinspect   
    c1.front() = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
**front\(\) \= a**  
 **x b c**   
## Configuration requise  
 **En\-tête :** \<cliext\/list\>  
  
 **Espace de nom** cliext  
  
## Voir aussi  
 [list](../dotnet/list-stl-clr.md)   
 [list::back](../dotnet/list-back-stl-clr.md)   
 [list::back\_item](../dotnet/list-back-item-stl-clr.md)   
 [list::front\_item](../dotnet/list-front-item-stl-clr.md)