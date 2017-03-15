---
title: "vector::vector (STL/CLR) | Microsoft Docs"
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
  - "cliext::vector::vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vector (membre) (STL/CLR)"
ms.assetid: a0b5e807-1ef2-422b-b772-1f96cd62fb51
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# vector::vector (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Construit un objet container.  
  
## Syntaxe  
  
```  
vector();  
vector(vector<Value>% right);  
vector(vector<Value>^ right);  
explicit vector(size_type count);  
vector(size_type count, value_type val);  
template<typename InIt>  
    vector(InIt first, InIt last);  
vector(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### Paramètres  
 count  
 Nombre d'éléments à insérer.  
  
 premier  
 Début de la plage à insérer.  
  
 last  
 Fin de la plage à insérer.  
  
 right  
 Objet ou plage à insérer.  
  
 val  
 Valeur de l'élément à insérer.  
  
## Notes  
 Le constructeur :  
  
 `vector();`  
  
 démarre la séquence contrôlée sans éléments.  Vous l'utilisez pour spécifier une séquence contrôlée par initiale vide.  
  
 Le constructeur :  
  
 `vector(vector<Value>% right);`  
  
 Initialise la séquence contrôlée avec la séquence `[``right``.`[vector::begin](../dotnet/vector-begin-stl-clr.md)`(),` `right``.`[vector::end](../dotnet/vector-end-stl-clr.md)`())`.  Vous l'utilisez pour spécifier une séquence contrôlée par initiale qui est une copie de la séquence contrôlée par l'objet vectoriel `right`.  
  
 Le constructeur :  
  
 `vector(vector<Value>^ right);`  
  
 Initialise la séquence contrôlée avec la séquence `[``right``->`[vector::begin](../dotnet/vector-begin-stl-clr.md)`(),` `right``->`[vector::end](../dotnet/vector-end-stl-clr.md)`())`.  Vous l'utilisez pour spécifier une séquence contrôlée par initiale qui est une copie de la séquence contrôlée par l'objet vectoriel dont le gestionnaire est `right`.  
  
 Le constructeur :  
  
 `explicit vector(size_type count);`  
  
 démarre la séquence contrôlée aux éléments de `count` chacune avec la valeur `value_type()`.  Vous l'utilisez pour remplir un conteneur avec des éléments ayant la même valeur par défaut.  
  
 Le constructeur :  
  
 `vector(size_type count, value_type val);`  
  
 démarre la séquence contrôlée aux éléments de `count` chacune avec la valeur `val`.  Vous l'utilisez pour remplir un conteneur avec des éléments ayant la même valeur.  
  
 Le constructeur :  
  
 `template<typename InIt>`  
  
 `vector(InIt first, InIt last);`  
  
 Initialise la séquence contrôlée avec la séquence `[``first``,` `last``)`.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence.  
  
 Le constructeur :  
  
 `vector(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 démarre la séquence contrôlée par l'ordre indiqué par l'énumérateur `right`.  Vous l'utilisez pour faire de la séquence contrôlée d'une copie d'une autre séquence décrite par un énumérateur.  
  
## Exemple  
  
```  
// cliext_vector_construct.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
// construct an empty container   
    cliext::vector<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::vector<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::vector<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::vector<wchar_t>::iterator it = c3.end();   
    cliext::vector<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::vector<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::vector<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::vector<wchar_t> c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **0 0 0**  
 **x x x x x x**  
 **x x x x x**  
 **x x x x x x**  
 **x x x x x x**  
 **x x x x x x**   
## Configuration requise  
 **En\-tête :** \<cliext\/vector\>  
  
 **Namespace:** cliext  
  
## Voir aussi  
 [vecteur](../dotnet/vector-stl-clr.md)   
 [vector::assign](../dotnet/vector-assign-stl-clr.md)   
 [vector::generic\_container](../dotnet/vector-generic-container-stl-clr.md)   
 [vector::operator\=](../dotnet/vector-operator-assign-stl-clr.md)