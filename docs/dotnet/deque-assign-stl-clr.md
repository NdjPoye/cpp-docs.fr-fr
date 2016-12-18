---
title: "deque::assign (STL/CLR) | Microsoft Docs"
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
  - "cliext::deque::assign"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre assign [STL/CLR]"
ms.assetid: 03fafdbb-6b10-4464-b3dc-0cc5cb8ac980
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# deque::assign (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Remplace tous les éléments.  
  
## Syntaxe  
  
```  
void assign(size_type count, value_type val);  
template<typename InIt>  
    void assign(InIt first, InIt last);  
void assign(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### Paramètres  
 count  
 Nombre d'éléments à insérer.  
  
 premier  
 Début de la plage à insérer.  
  
 last  
 Fin de la plage à insérer.  
  
 right  
 Énumération à insérer.  
  
 val  
 Valeur de l'élément à insérer.  
  
## Notes  
 La première fonction membre remplace la séquence contrôlée avec une répétion d'éléments `count` de valeur `val`.  Vous l'utilisez pour remplir un conteneur avec des éléments ayant la même valeur.  
  
 Si `InIt` est un type entier, la deuxième fonction membre se comporte de la même manière que `assign((size_type)``first``, (value_type)``last``)`.  Sinon, il remplace la séquence contrôlée par la séquence `[``first``,` `last``)`.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence.  
  
 La troisième fonction membre remplace la séquence contrôlée par la séquence indiqué par l'énumérateur `right`.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une séquence décrite par un énumérateur.  
  
## Exemple  
  
```  
// cliext_deque_assign.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// assign a repetition of values   
    cliext::deque<wchar_t> c2;   
    c2.assign(6, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an iterator range   
    c2.assign(c1.begin(), c1.end() - 1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an enumeration   
    c2.assign(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **x x x x x x**  
 **a b**  
 **a b c**   
## Configuration requise  
 **En\-tête :** \<cliext\/deque\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [deque](../dotnet/deque-stl-clr.md)   
 [operator\= \(deque\)](../dotnet/operator-assign-deque-stl-clr.md)