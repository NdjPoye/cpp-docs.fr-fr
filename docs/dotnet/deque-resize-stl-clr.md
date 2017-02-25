---
title: "deque::resize (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::deque::resize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre resize [STL/CLR]"
ms.assetid: c83f3c57-38b3-4706-a124-59bafbf88484
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# deque::resize (STL/CLR)
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
 Les deux fonctions membres s'assurent que [deque::size](../dotnet/deque-size-stl-clr.md)`()` retourne dorénavant `new_size`.  Si elle doit rendre la séquence contrôlée plus longue, la première fonction membre ajoute les éléments de valeur `value_type()`, tandis que la deuxième fonction membre ajoute les éléments de valeur `val`.  Pour rendre la séquence contrôlée plus courte, les deux fonctions membres effacent en pratique le dernier élément de [deque::size](../dotnet/deque-size-stl-clr.md)`() -` `new_size` fois.  Vous l'utilisez pour faire en sorte que la séquence contrôlée est de taille `new_size`, en effectuant soit du rognage, soit du remplissage de la séquence contrôlée actuelle.  
  
## Exemple  
  
```  
// cliext_deque_resize.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::deque<wchar_t> c1;   
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
 **En\-tête :** \<cliext\/deque\>  
  
 **Espace de noms :** cliext  
  
## Voir aussi  
 [deque](../dotnet/deque-stl-clr.md)   
 [deque::clear](../dotnet/deque-clear-stl-clr.md)   
 [deque::erase](../dotnet/deque-erase-stl-clr.md)   
 [deque::insert](../dotnet/deque-insert-stl-clr.md)