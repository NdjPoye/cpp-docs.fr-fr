---
title: "priority_queue::to_array (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::priority_queue::to_array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "to_array (membre) (STL/CLR)"
ms.assetid: f686494c-a943-4d3c-b419-0305a5716ae6
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# priority_queue::to_array (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Copie la séquence contrôlée dans un tableau.  
  
## Syntaxe  
  
```  
cli::array<Value>^ to_array();  
```  
  
## Notes  
 La fonction membre retourne un tableau qui contient la séquence contrôlée.  Vous l'utilisez pour obtenir une copie de la séquence contrôlée sous forme de tableau.  
  
## Exemple  
  
```  
// cliext_priority_queue_to_array.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// copy the container and modify it   
    cli::array<wchar_t>^ a1 = c1.to_array();   
  
    c1.push(L'd');   
    for each (wchar_t elem in c1.get_container())   
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
 **c a b**   
## Configuration requise  
 **En\-tête :** \<cliext\/queue\>  
  
 **Espace de nommage:** cliext  
  
## Voir aussi  
 [priority\_queue](../dotnet/priority-queue-stl-clr.md)