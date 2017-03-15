---
title: "list::resize (STL/CLR) | Microsoft Docs"
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
  - "cliext::list::resize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre resize [STL/CLR]"
ms.assetid: c4b8d41f-a62b-4dbc-8568-0e0a9da24016
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# list::resize (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Change le nombre d'éléments.  
  
## Syntaxe  
  
```  
void resize(size_type new_size);  
void resize(size_type new_size, value_type val);  
```  
  
#### Paramètres  
 new\_size  
 Nouvelle taille de la séquence contrôlée.  
  
 val  
 Valeur de l'élément de remplissage.  
  
## Notes  
 Les deux fonctions membres s'assurent que [list::size](../dotnet/list-size-stl-clr.md)`()` retourne dorénavant `new_size`.  Si elle doit rendre la séquence contrôlée plus longue, la première fonction membre ajoute les éléments de valeur `value_type()`, tandis que la deuxième fonction membre ajoute les éléments de valeur `val`.  Pour rendre la séquence contrôlée plus courte, les deux fonctions membres effacent en pratique le dernier élément de [list::size](../dotnet/list-size-stl-clr.md)`() -` `new_size` fois.  Vous l'utilisez pour faire en sorte que la séquence contrôlée est de taille `new_size`, en effectuant soit du rognage, soit du remplissage de la séquence contrôlée actuelle.  
  
## Exemple  
  
```  
// cliext_list_resize.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::list<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
    c1.resize(4);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// resize to empty   
    c1.resize(0);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// resize and pad   
    c1.resize(5, L'x');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **0 0 0 0**  
**size\(\) \= 0**  
 **x x x x x**   
## Configuration requise  
 **En\-tête :** \<cliext\/list\>  
  
 **Espace de noms :** cliext  
  
## Voir aussi  
 [list](../dotnet/list-stl-clr.md)   
 [list::clear](../dotnet/list-clear-stl-clr.md)   
 [list::erase](../dotnet/list-erase-stl-clr.md)   
 [list::insert](../dotnet/list-insert-stl-clr.md)