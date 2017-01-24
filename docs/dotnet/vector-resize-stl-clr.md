---
title: "vector::resize (STL/CLR) | Microsoft Docs"
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
  - "cliext::vector::resize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre resize [STL/CLR]"
ms.assetid: a3556fbc-67d9-463a-9ffc-cb43ee15657f
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# vector::resize (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Change le nombre d'éléments.  
  
## Syntaxe  
  
```  
void resize(size_type new_size);  
void resize(size_type new_size, value_type val);  
```  
  
#### Paramètres  
 nouvelle\_taille  
 Nouvelle taille de la séquence contrôlée.  
  
 val  
 Valeur de l'élément de remplissage.  
  
## Notes  
 Les deux fonctions membres s'assurent que [vector::size](../dotnet/vector-size-stl-clr.md)`()` retourne dorénavant `new_size`.  Si elle doit rendre la séquence contrôlée plus longue, la première fonction membre ajoute les éléments de valeur `value_type()`, tandis que la deuxième fonction membre ajoute les éléments de valeur `val`.  Pour rendre la séquence contrôlée plus courte, les deux fonctions membres effacent en pratique le dernier élément de [vector::size](../dotnet/vector-size-stl-clr.md)`() -` `new_size` fois.  Vous l'utilisez pour faire en sorte que la séquence contrôlée est de taille `new_size`, en effectuant soit du rognage, soit du remplissage de la séquence contrôlée actuelle.  
  
## Exemple  
  
```  
// cliext_vector_resize.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::vector<wchar_t> c1;   
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
  
  **taille\(\) \= 0**  
 **0 0 0 0**  
**taille\(\) \= 0**  
 **x x x x x**   
## Configuration requise  
 **En\-tête :** \<cliext\/vector\>  
  
 **Espace de nom** cliext  
  
## Voir aussi  
 [vecteur](../dotnet/vector-stl-clr.md)   
 [vector::clear](../dotnet/vector-clear-stl-clr.md)   
 [vector::erase](../dotnet/vector-erase-stl-clr.md)   
 [vector::insert](../dotnet/vector-insert-stl-clr.md)