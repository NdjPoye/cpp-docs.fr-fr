---
title: "deque::const_reverse_iterator (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::deque::const_reverse_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_reverse_iterator (membre) (STL/CLR)"
ms.assetid: fd3a99de-2721-432b-a502-412a72b98e74
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# deque::const_reverse_iterator (STL/CLR)
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
// cliext_deque_const_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" reversed   
    cliext::deque<wchar_t>::const_reverse_iterator crit = c1.rbegin();   
    cliext::deque<wchar_t>::const_reverse_iterator crend = c1.rend();   
    for (; crit != crend; ++crit)   
        System::Console::Write(" {0}", *crit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **c b a**   
## Configuration requise  
 **En\-tête :** \<cliext\/deque\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [deque](../dotnet/deque-stl-clr.md)   
 [deque::reverse\_iterator](../dotnet/deque-reverse-iterator-stl-clr.md)