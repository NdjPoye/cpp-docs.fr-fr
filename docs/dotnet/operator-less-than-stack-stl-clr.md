---
title: "operator&lt; (stack) (STL/CLR) | Microsoft Docs"
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
  - "cliext::stack::operator<"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator< (membre) (STL/CLR)"
ms.assetid: 77f8dd42-89d1-4ce1-a7ec-04c3a45dd3ee
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator&lt; (stack) (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Comparaison d'infériorité d'empilement  
  
## Syntaxe  
  
```  
template<typename Value,  
    typename Container>  
    bool operator<(stack<Value, Container>% left,  
        stack<Value, Container>% right);  
```  
  
#### Paramètres  
 left  
 Conteneur de gauche à comparer.  
  
 right  
 Conteneur de droite à comparer.  
  
## Notes  
 La fonction d'opérateur retourne true si, pour la position la minima `i` pour laquelle `!(``right``[i] <` `left``[i])` il est également vrai qu' `left``[i] <` `right``[i]`.  Dans le cas contraire, il retourne `left``->`[stack::size](../dotnet/stack-size-stl-clr.md)`() <` `right``->size()` Vous l'utilisez pour tester si `left` est ordonné avant `right` lorsque les deux deques sont comparés élément par élément.  
  
## Exemple  
  
```  
// cliext_stack_operator_lt.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mystack c2;   
    c2.push(L'a');   
    c2.push(L'b');   
    c2.push(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2.get_container())   
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
 **En\-tête :** \<cliext\/stack\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [pile](../dotnet/stack-stl-clr.md)   
 [operator\=\= \(stack\)](../dotnet/operator-equality-stack-stl-clr.md)   
 [operator\!\= \(stack\)](../dotnet/operator-inequality-stack-stl-clr.md)   
 [operator\>\= \(stack\)](../dotnet/operator-greater-or-equal-stack-stl-clr.md)   
 [operator\> \(stack\)](../dotnet/operator-greater-than-stack-stl-clr.md)   
 [operator\<\= \(stack\)](../dotnet/operator-less-or-equal-stack-stl-clr.md)