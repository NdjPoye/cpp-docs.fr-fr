---
title: "set::const_reverse_iterator (STL/CLR) | Microsoft Docs"
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
  - "cliext::set::const_reverse_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_reverse_iterator (membre) (STL/CLR)"
ms.assetid: 60171be5-c4a8-4fce-89a9-6642d805bb57
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# set::const_reverse_iterator (STL/CLR)
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
// cliext_set_const_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c" reversed   
    Myset::const_reverse_iterator crit = c1.rbegin();   
    for (; crit != c1.rend(); ++crit)   
        System::Console::Write(" {0}", *crit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **c b a**   
## Configuration requise  
 **En\-tête :** \<cliext\/set\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [set](../dotnet/set-stl-clr.md)   
 [set::reverse\_iterator](../dotnet/set-reverse-iterator-stl-clr.md)