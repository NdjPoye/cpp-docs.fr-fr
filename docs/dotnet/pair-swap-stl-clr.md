---
title: "pair::swap (STL/CLR) | Microsoft Docs"
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
  - "cliext::pair::swap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre swap [STL/CLR]"
ms.assetid: 7f5cbfa0-3702-40ab-a3f4-ffde02126095
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# pair::swap (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Échange le contenu de deux paires.  
  
## Syntaxe  
  
```  
void swap(pair<Value1, Value2>% right);  
```  
  
#### Paramètres  
 right  
 Paire avec laquelle échanger le contenu.  
  
## Notes  
 La fonction membre permute les paires de valeurs stockées entre `*this` et `right`.  
  
## Exemple  
  
```  
// cliext_pair_swap.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    cliext::deque<wchar_t> d2(5, L'x');   
    Mycoll c2(%d2);   
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
 **En\-tête :** \<cliext\/utility\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [paire](../dotnet/pair-stl-clr.md)   
 [pair::operator\=](../dotnet/pair-operator-assign-stl-clr.md)