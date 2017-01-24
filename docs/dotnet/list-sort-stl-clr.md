---
title: "list::sort (STL/CLR) | Microsoft Docs"
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
  - "cliext::list::sort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "member sort [STL/CLR]"
ms.assetid: f811d5f4-a19e-4194-8765-1e68097c52f0
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# list::sort (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ordonne la séquence contrôlée.  
  
## Syntaxe  
  
```  
void sort();  
template<typename Pred2>  
    void sort(Pred2 pred);  
```  
  
#### Paramètres  
 pred  
 Comparateur pour les paires d'éléments.  
  
## Notes  
 La première fonction membre organise les éléments de la séquence contrôlée de sorte qu'ils soient triés par `operator<` \-\- les éléments ne réduisent pas de valeur quand vous progressez dans la séquence.  Vous utilisez cette fonction membre pour trier la séquence dans l'ordre croissant.  
  
 La deuxième fonction membre se comporte de la même manière que la première, mais la séquence est triée par `pred` \-\- `pred``(X, Y)` est faux pour un élément `X` qui suit l'élément `Y` de la séquence résultante.  Vous l'utilisez pour trier la séquence dans un ordre que vous spécifiez par une fonction de prédicat ou un délégué.  
  
 Les deux fonctions effectuent un tri stable \-\- aucune paire d'éléments dans la séquence contrôlée originale n'est inversée dans la séquence contrôlée obtenue.  
  
## Exemple  
  
```  
// cliext_list_sort.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// sort descending and redisplay   
    c1.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// sort ascending and redisplay   
    c1.sort();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **c b a**  
 **a b c**   
## Configuration requise  
 **En\-tête :** \<cliext\/list\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [list](../dotnet/list-stl-clr.md)   
 [list::merge](../dotnet/list-merge-stl-clr.md)   
 [list::reverse](../dotnet/list-reverse-stl-clr.md)   
 [list::splice](../dotnet/list-splice-stl-clr.md)   
 [list::unique](../dotnet/list-unique-stl-clr.md)