---
title: "deque::deque (STL/CLR) | Microsoft Docs"
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
  - "cliext::deque::deque"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "deque (membre) (STL/CLR)"
ms.assetid: e5bc9511-619e-469c-b50a-e06858e7fce7
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# deque::deque (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Construit un objet container.  
  
## Syntaxe  
  
```  
deque();  
deque(deque<Value>% right);  
deque(deque<Value>^ right);  
explicit deque(size_type count);  
deque(size_type count, value_type val);  
template<typename InIt>  
    deque(InIt first, InIt last);  
deque(System::Collections::Generic::IEnumerable<Value>^ right);  
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
  
 `deque();`  
  
 démarre la séquence contrôlée sans éléments.  Vous l'utilisez pour spécifier une séquence contrôlée initialement vide.  
  
 Le constructeur :  
  
 `deque(deque<Value>% right);`  
  
 Initialise la séquence contrôlée avec la séquence `[``right``.`[deque::begin](../dotnet/deque-begin-stl-clr.md)`(),` `right``.`[deque::end](../dotnet/deque-end-stl-clr.md)`())`.  Vous l'utilisez pour spécifier une séquence contrôlée par initiale qui est une copie de la séquence contrôlée par l'objet vectoriel `right`.  
  
 Le constructeur :  
  
 `deque(deque<Value>^ right);`  
  
 Initialise la séquence contrôlée avec la séquence `[``right``->`[deque::begin](../dotnet/deque-begin-stl-clr.md)`(),` `right``->`[deque::end](../dotnet/deque-end-stl-clr.md)`())`.  Vous l'utilisez pour spécifier une séquence initiale contrôlée qui est une copie de la séquence contrôlée par l'objet de list dont le gestionnaire est `right`.  
  
 Le constructeur :  
  
 `explicit deque(size_type count);`  
  
 démarrez la séquence contrôlée aux éléments de `count`  chacune avec la valeur `value_type()`.  Vous l'utilisez pour remplir un conteneur avec des éléments ayant la même valeur par défaut.  
  
 Le constructeur :  
  
 `deque(size_type count, value_type val);`  
  
 démarre la séquence contrôlée aux éléments de `count` chacune avec la valeur `val`.  Vous l'utilisez pour remplir un conteneur avec des éléments ayant la même valeur.  
  
 Le constructeur :  
  
 `template<typename InIt>`  
  
 `deque(InIt first, InIt last);`  
  
 Initialise la séquence contrôlée avec la séquence `[``first``,` `last``)`.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence.  
  
 Le constructeur :  
  
 `deque(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 démarre la séquence contrôlée avec la séquence indiquée par l'énumérateur `right`.  Vous l'utilisez pour faire de la séquence contrôlée d'une copie d'une séquence décrite par un énumérateur.  
  
## Exemple  
  
```  
// cliext_deque_construct.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
// construct an empty container   
    cliext::deque<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::deque<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::deque<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::deque<wchar_t>::iterator it = c3.end();   
    cliext::deque<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::deque<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::deque<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::deque<wchar_t> c8(%c3);   
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
 **En\-tête :** \<cliext\/deque\>  
  
 **Espace de noms :** cliext  
  
## Voir aussi  
 [deque](../dotnet/deque-stl-clr.md)   
 [deque::assign](../dotnet/deque-assign-stl-clr.md)   
 [deque::generic\_container](../dotnet/deque-generic-container-stl-clr.md)   
 [operator\= \(deque\)](../dotnet/operator-assign-deque-stl-clr.md)