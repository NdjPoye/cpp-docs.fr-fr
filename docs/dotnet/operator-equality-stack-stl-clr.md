---
title: "operator== (stack) (STL/CLR) | Microsoft Docs"
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
  - "cliext::stack::operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "opérateur== membre [STL/CLR]"
ms.assetid: 862e7130-150a-44ea-9ec4-9f091ab7653d
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator== (stack) (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Comparaison d'égalité de pile.  
  
## Syntaxe  
  
```  
template<typename Value,  
    typename Container>  
    bool operator==(stack<Value, Container>% left,  
        stack<Value, Container>% right);  
```  
  
#### Paramètres  
 left  
 Conteneur de gauche à comparer.  
  
 right  
 Conteneur de droite à comparer.  
  
## Notes  
 L'opérateur renvoie vrai uniquement si les séquences contrôlées par `left` et `right` ont la même longueur et, pour chaque position `i`, `left``[i] ==` `right``[i]`.  Vous l'utilisez pour tester si `left` est ordonné de la même façon que `right` lorsque les deux paires sont comparées élément par élément.  
  
## Exemple  
  
```  
// cliext_stack_operator_eq.cpp   
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
  
    System::Console::WriteLine("[a b c] == [a b c] is {0}",   
        c1 == c1);   
    System::Console::WriteLine("[a b c] == [a b d] is {0}",   
        c1 == c2);   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b d**  
**\[a b c\] \=\= \[a b c\] est Vrai**  
**\[a b c\] \=\= \[a b d\] est Faux**   
## Configuration requise  
 **En\-tête :** \<cliext\/stack\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [pile](../dotnet/stack-stl-clr.md)   
 [operator\!\= \(stack\)](../dotnet/operator-inequality-stack-stl-clr.md)   
 [operator\< \(stack\)](../dotnet/operator-less-than-stack-stl-clr.md)   
 [operator\>\= \(stack\)](../dotnet/operator-greater-or-equal-stack-stl-clr.md)   
 [operator\> \(stack\)](../dotnet/operator-greater-than-stack-stl-clr.md)   
 [operator\<\= \(stack\)](../dotnet/operator-less-or-equal-stack-stl-clr.md)