---
title: "deque::swap (STL/CLR) | Microsoft Docs"
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
  - "cliext::deque::swap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre swap [STL/CLR]"
ms.assetid: 511e1aa8-3069-43f3-aa77-150f1de1e195
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# deque::swap (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Échange le contenu de deux conteneurs.  
  
## Syntaxe  
  
```  
void swap(deque<Value>% right);  
```  
  
#### Paramètres  
 right  
 Conteneur avec lequel échanger le contenu.  
  
## Notes  
 La méthode permute les séquences contrôlées entre `*this` et `right`.  Elle le fait en un temps constant et ne lève pas d'exception.  Vous l'utilisez comme méthode rapide d'échange du contenu de deux conteneurs.  
  
## Exemple  
  
```  
// cliext_deque_swap.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    cliext::deque<wchar_t> c2(5, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// swap and redisplay   
    c1.swap(c2);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **x x x x x**  
 **x x x x x**  
 **a b c**   
## Configuration requise  
 **En\-tête :** \<cliext\/deque\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [deque](../dotnet/deque-stl-clr.md)   
 [deque::assign](../dotnet/deque-assign-stl-clr.md)   
 [operator\= \(deque\)](../dotnet/operator-assign-deque-stl-clr.md)