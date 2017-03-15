---
title: "operator&lt; (deque) (STL/CLR) | Microsoft Docs"
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
  - "cliext::deque::operator<"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator< (membre) (STL/CLR)"
ms.assetid: f2fa1bb1-bc0a-4e9e-826b-6b72a5543b29
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator&lt; (deque) (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Comparaison structurelle d'infériorité  
  
## Syntaxe  
  
```  
template<typename Value>  
    bool operator<(deque<Value>% left,  
        deque<Value>% right);  
```  
  
#### Paramètres  
 left  
 Conteneur de gauche à comparer.  
  
 right  
 Conteneur de droite à comparer.  
  
## Notes  
 La fonction d'opérateur retourne true si, pour la position la minima `i` pour laquelle `!(``right``[i] <` `left``[i])` il est également vrai qu' `left``[i] <` `right``[i]`.  Dans le cas contraire, il retourne `left``->size() <` `right``->size()` Vous l'utilisez pour tester si `left` est ordonné avant `->size() <`  lorsque les deux modes sont comparées élément par élément.  
  
## Exemple  
  
```  
// cliext_deque_operator_lt.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::deque<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] < [a b c] is {0}",   
        c1 < c1);   
    System::Console::WriteLine("[a b c] < [a b d] is {0}",   
        c1 < c2);   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b d**  
**\[a b c\] \< \[a b c\] est Faux**  
**\[a b c\] \< \[a b d\] est Vrai**   
## Configuration requise  
 **En\-tête :** \<cliext\/deque\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [deque](../dotnet/deque-stl-clr.md)   
 [operator\=\= \(deque\)](../dotnet/operator-equality-deque-stl-clr.md)   
 [deque::operator\!\=](../dotnet/deque-operator-inequality-stl-clr.md)   
 [operator\>\= \(deque\)](../dotnet/operator-greater-or-equal-deque-stl-clr.md)   
 [operator\> \(deque\)](../dotnet/operator-greater-than-deque-stl-clr.md)   
 [operator\<\= \(deque\)](../dotnet/operator-less-or-equal-deque-stl-clr.md)