---
title: "list::merge (STL/CLR) | Microsoft Docs"
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
  - "cliext::list::merge"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre merge [STL/CLR]"
ms.assetid: f8e93cd3-bd08-4086-859b-08a2899cc9a6
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# list::merge (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fusionne deux séquences contrôlées ordonnées.  
  
## Syntaxe  
  
```  
void merge(list<Value>% right);  
template<typename Pred2>  
    void merge(list<Value>% right, Pred2 pred);  
```  
  
#### Paramètres  
 pred  
 Comparateur pour les paires d'éléments.  
  
 right  
 Conteneur dans lequel fusionner.  
  
## Notes  
 La première fonction membre supprime tous les éléments de la séquence contrôlée par `right` et les insère dans la séquence contrôlée.  Les séquences doivent être préalablement triées par `operator<` \-\- les éléments ne doivent pas diminuer de valeur lorsque vous progressez dans l'une ou l'autre des séquences.  La séquence qui en résulte est également ordonnée par `operator<`.  Vous utilisez cette fonction membre pour fusionner deux séquences qui augmentent de valeur dans une séquence qui augmente également de valeur.  
  
 La deuxième fonction membre se comporte de la même manière que la première, sauf que les séquences sont triées par `pred` \-\- `pred``(X, Y)` doit être faux pour un élément `X` qui suit l'élément `Y` de la séquence résultante.  Vous l'utilisez pour fusionner deux séquences ordonnées par une fonction de prédicat ou un délégué que vous spécifiez.  
  
 Les deux fonctions effectuent une fusion stable \-\- aucune paire d'éléments l'une ou l'autre des séquence contrôlée originale n'est inversée dans la séquence contrôlée obtenue.  Aussi, si une paire d'éléments `X` et `Y`dans la séquence obtenue contrôlée a une organisation équivalente \(`!(X < Y) && !(X < Y)` \), un élément de la séquence contrôlée originale apparaît avant un élément de la séquence contrôlée par `right`.  
  
## Exemple  
  
```  
// cliext_list_merge.cpp   
// compile with: /clr   
#include <cliext/list>   
  
typedef cliext::list<wchar_t> Mylist;   
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'c');   
    c1.push_back(L'e');   
  
// display initial contents " a c e"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    cliext::list<wchar_t> c2;   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
    c2.push_back(L'f');   
  
// display initial contents " b d f"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// merge and display   
    cliext::list<wchar_t> c3(c1);   
    c3.merge(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c2.size() = {0}", c2.size());   
  
// sort descending, merge descending, and redisplay   
    c1.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    c3.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    c3.merge(c1, cliext::greater<wchar_t>());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c1.size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
  **a c e**  
 **b d f**  
 **a b c d e f**  
**c2.size\(\) \= 0**  
 **e c a**  
 **f e d c b a**  
 **f e e d c c b a a**  
**c1.size\(\) \= 0**   
## Configuration requise  
 **En\-tête :** \<cliext\/list\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [list](../dotnet/list-stl-clr.md)   
 [list::sort](../dotnet/list-sort-stl-clr.md)   
 [list::splice](../dotnet/list-splice-stl-clr.md)