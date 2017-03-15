---
title: "list::splice (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::splice"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre splice [STL/CLR]"
ms.assetid: ebc424b9-8341-4a88-b101-86d56324f5ac
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# list::splice (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Liens de Restitches entre les nœuds.  
  
## Syntaxe  
  
```  
void splice(iterator where, list<Value>% right);  
void splice(iterator where, list<Value>% right,  
    iterator first);  
void splice(iterator where, list<Value>% right,  
    iterator first, iterator last);  
```  
  
#### Paramètres  
 first  
 Début de la plage à épisser.  
  
 last  
 Fin de la plage à épisser.  
  
 right  
 Conteneur à partir duquel effectuer l'opération splice.  
  
 where  
 Où dans le conteneur épisser avant.  
  
## Notes  
 La première fonction membre insère la séquence contrôlée par `right` avant l'élément dans la séquence contrôlée est référencé par `where`.  Elle supprime également tous les éléments d'`right`. \(`%``right` ne doit pas être égal `this`.\) Vous l'utilisez pour épisser toute la liste dans une autre.  
  
 La deuxième fonction membre supprime l'élément référencé par `first` dans la séquence contrôlée par `right` et l'insère avant l'élément dans la séquence contrôlée est référencé par `where`. \(Si `where` `==` `first` `||` `where` `== ++``first`, aucune modification se produit.\) Vous l'utilisez pour épisser un élément unique dans une liste dans une autre.  
  
 La troisième fonction membre insère le sous\-plage indiqué par `[``first``,` `last``)` de la séquence contrôlée par `right` avant l'élément dans la séquence contrôlée est référencé par `where`.  Elle supprime également le sous\-plage d'origine de la séquence contrôlée par `right`. \(Si `right` `==` `this`, la plage `[``first``,` `last``)` ne doit pas inclure l'élément référencé par `where`.\) Vous l'utilisez pour épisser une sous\-séquence de zéro ou plusieurs éléments d'une liste dans une autre.  
  
## Exemple  
  
```  
// cliext_list_splice.cpp   
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
  
// splice to a new list   
    cliext::list<wchar_t> c2;   
    c2.splice(c2.begin(), c1);   
    System::Console::WriteLine("c1.size() = {0}", c1.size());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// return one element   
    c1.splice(c1.end(), c2, c2.begin());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// return remaining elements   
    c1.splice(c1.begin(), c2, c2.begin(), c2.end());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c2.size() = {0}", c2.size());   
    return (0);   
    }  
  
```  
  
  **a b c**  
**c1.size\(\) \= 0**  
 **a b c**  
 **a**  
 **b c**  
 **&#124; a b c &#124;**  
**c2.size\(\) \= 0**   
## Configuration requise  
 **En\-tête :** \<cliext\/list\>  
  
 **Espace de nom** cliext  
  
## Voir aussi  
 [list](../dotnet/list-stl-clr.md)   
 [list::assign](../dotnet/list-assign-stl-clr.md)   
 [list::insert](../dotnet/list-insert-stl-clr.md)   
 [list::merge](../dotnet/list-merge-stl-clr.md)