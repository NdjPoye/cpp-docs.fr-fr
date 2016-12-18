---
title: "list::unique (STL/CLR) | Microsoft Docs"
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
  - "cliext::list::unique"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre unique [STL/CLR]"
ms.assetid: c3a29e4e-0ec1-4472-b050-7a9511037132
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# list::unique (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Supprime les éléments adjacents qui réussissent un test spécifié.  
  
## Syntaxe  
  
```  
void unique();  
template<typename Pred2>  
    void unique(Pred2 pred);  
```  
  
#### Paramètres  
 pred  
 Comparateur pour les paires d'éléments.  
  
## Notes  
 La première fonction membre supprime de la séquence contrôlée \(effacements\) chaque élément qui est égal à son élément précédent \-\- si l'élément `X` précède l'élément `Y` et si `X == Y`, la fonction membre supprime `Y`.  Vous l'utilisez pour supprimer toutes les copies sauf une de chaque sous\-séquence d'éléments adjacents égaux.  Notez que si la séquence contrôlée est triée, par exemple en appelant [list::sort](../dotnet/list-sort-stl-clr.md)`()`, la fonction membre laisse uniquement les éléments avec des valeurs uniques. \(D'où le nom\).  
  
 La deuxième fonction membre se comporte de la même manière que la première, sauf qu'il supprime chaque élément `Y` suivant un élément `X` tel que `pred``(X, Y)`.  Vous l'utilisez pour supprimer toutes les copies sauf de chaque sous\-séquence d'éléments adjacents qui satisfont à une fonction de prédicat ou un délégué que vous spécifiez.  Notez que si la séquence contrôlée est triée, par exemple en appelant `sort(``pred``)`, la fonction membre laisse uniquement les éléments qui ne sont pas classés comme équivalent avec un autre élément.  
  
## Exemple  
  
```  
// cliext_list_unique.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique   
    cliext::list<wchar_t> c2(c1);   
    c2.unique();   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique(not_equal_to)   
    c2 = c1;   
    c2.unique(cliext::not_equal_to<wchar_t>());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a a b c**  
 **a b c**  
 **a a**   
## Configuration requise  
 **En\-tête :** \<cliext\/list\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [list](../dotnet/list-stl-clr.md)   
 [list::remove](../dotnet/list-remove-stl-clr.md)   
 [list::remove\_if](../dotnet/list-remove-if-stl-clr.md)   
 [list::sort](../dotnet/list-sort-stl-clr.md)