---
title: "list::to_array (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::to_array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "to_array (membre) (STL/CLR)"
ms.assetid: 3ea7b90c-127b-43cd-804b-019b86b77582
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# list::to_array (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Copie la séquence contrôlée dans un nouveau tableau.  
  
## Syntaxe  
  
```  
cli::array<Value>^ to_array();  
```  
  
## Notes  
 La méthode retourne un tableau qui contient la séquence contrôlée.  Vous l'utilisez pour obtenir une copie de la séquence contrôlée sous forme de tableau.  
  
## Exemple  
  
```  
// cliext_list_to_array.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// copy the container and modify it   
    cli::array<wchar_t>^ a1 = c1.to_array();   
  
    c1.push_back(L'd');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c d**  
 **a b c**   
## Configuration requise  
 **En\-tête :** \<cliext\/list\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [list](../dotnet/list-stl-clr.md)