---
title: "map::map (STL/CLR) | Microsoft Docs"
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
  - "cliext::map::map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "map (membre) (STL/CLR)"
ms.assetid: c91f699a-4742-4859-b2b3-c2a01a750bea
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# map::map (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Construit un objet container.  
  
## Syntaxe  
  
```  
map();  
explicit map(key_compare^ pred);  
map(map<Key, Mapped>% right);  
map(map<Key, Mapped>^ right);  
template<typename InIter>  
    mapmap(InIter first, InIter last);  
template<typename InIter>  
    map(InIter first, InIter last,  
        key_compare^ pred);  
map(System::Collections::Generic::IEnumerable<GValue>^ right);  
map(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
```  
  
#### Paramètres  
 premier  
 Début de la plage à insérer.  
  
 last  
 Fin de la plage à insérer.  
  
 pred  
 Classer l'attribut de la séquence contrôlée.  
  
 right  
 Objet ou plage à insérer.  
  
## Notes  
 Le constructeur :  
  
 `map();`  
  
 démarre la séquence contrôlée sans éléments, avec le prédicat de classement par défaut `key_compare()`.  Vous l'utilisez pour spécifier une séquence initiale contrôlée vide, avec le prédicat de classement par défaut.  
  
 Le constructeur :  
  
 `explicit map(key_compare^ pred);`  
  
 démarre la séquence contrôlée sans éléments, avec le prédicat de classement `pred`.  Vous l'utilisez pour spécifier une séquence initiale contrôlée vide, avec le prédicat de classement spécifié.  
  
 Le constructeur :  
  
 `map(map<Key, Mapped>% right);`  
  
 démarre la séquence contrôlée par la séquence `[``right``.`[map::begin](../dotnet/map-begin-stl-clr.md)`(),` `right``.`[map::end](../dotnet/map-end-stl-clr.md)`())`, avec le prédicat de classement par défaut.  Vous l'utilisez pour spécifier une séquence initiale contrôlée qui est une copie de la séquence contrôlée par l'objet map `right`, avec le prédicat de classement par défaut.  
  
 Le constructeur :  
  
 `map(map<Key, Mapped>^ right);`  
  
 démarre la séquence contrôlée par la séquence `[``right``->`[map::begin](../dotnet/map-begin-stl-clr.md)`(),` `right``->`[map::end](../dotnet/map-end-stl-clr.md)`())`, avec le prédicat de classement par défaut.  Vous l'utilisez pour spécifier une séquence initiale contrôlée qui est une copie de la séquence contrôlée par l'objet map `right`, avec le prédicat de classement par défaut.  
  
 Le constructeur :  
  
 `template<typename InIter>`  
  
 `map(InIter first, InIter last);`  
  
 démarre la séquence contrôlée par la séquence `[``first``,` `last``)`, avec le prédicat de classement par défaut.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence, avec le prédicat de classement par défaut.  
  
 Le constructeur :  
  
 `template<typename InIter>`  
  
 `map(InIter first, InIter last,`  
  
 `key_compare^ pred);`  
  
 démarre la séquence contrôlée par la séquence `[``first``,` `last``)`, avec le prédicat de classement par défaut `pred`.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence, avec le prédicat de classement spécifié.  
  
 Le constructeur :  
  
 `map(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 démarre la séquence contrôlée par la séquence désignée par l'énumérateur `right`, avec le prédicat de classement par défaut.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence décrite par un énumérateur, avec le prédicat de classement par défaut.  
  
 Le constructeur :  
  
 `map(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred);`  
  
 démarre la séquence contrôlée par la séquence désignée par l'énumérateur `right`, avec le prédicat de classement par défaut `pred`.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence décrite par un énumérateur, avec le prédicat de classement spécifié.  
  
## Exemple  
  
```  
// cliext_map_construct.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
// construct an empty container   
    Mymap c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mymap c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (Mymap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mymap c3(c1.begin(), c1.end());   
    for each (Mymap::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mymap c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (Mymap::value_type elem in c4)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Mymap c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Mymap::value_type>^)%c3);   
    for each (Mymap::value_type elem in c5)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Mymap c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Mymap::value_type>^)%c3,   
                cliext::greater_equal<wchar_t>());   
    for each (Mymap::value_type elem in c6)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mymap c7(c4);   
    for each (Mymap::value_type elem in c7)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    Mymap c8(%c3);   
    for each (Mymap::value_type elem in c8)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **\[a 1\] \[b 2\] \[c 3\]**  
**size\(\) \= 0**  
 **\[c 3\] \[b 2\] \[a 1\]**  
 **\[a 1\] \[b 2\] \[c 3\]**  
 **\[c 3\] \[b 2\] \[a 1\]**  
 **\[a 1\] \[b 2\] \[c 3\]**  
 **\[c 3\] \[b 2\] \[a 1\]**  
 **\[c 3\] \[b 2\] \[a 1\]**  
 **\[a 1\] \[b 2\] \[c 3\]**   
## Configuration requise  
 **En\-tête :** \<cliext\/map\>  
  
 **Espace de noms :** cliext  
  
## Voir aussi  
 [map](../dotnet/map-stl-clr.md)   
 [map::generic\_container](../dotnet/map-generic-container-stl-clr.md)   
 [map::operator\=](../dotnet/map-operator-assign-stl-clr.md)