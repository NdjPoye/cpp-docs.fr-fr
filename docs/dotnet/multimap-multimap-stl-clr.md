---
title: "multimap::multimap (STL/CLR) | Microsoft Docs"
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
  - "cliext::multimap::multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "multimap (membre) (STL/CLR)"
ms.assetid: cdf9c5dc-774c-424e-aeea-7554643e401c
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# multimap::multimap (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Construit un objet container.  
  
## Syntaxe  
  
```  
multimap();  
explicit multimap(key_compare^ pred);  
multimap(multimap<Key, Mapped>% right);  
multimap(multimap<Key, Mapped>^ right);  
template<typename InIter>  
    multimapmultimap(InIter first, InIter last);  
template<typename InIter>  
    multimap(InIter first, InIter last,  
        key_compare^ pred);  
multimap(System::Collections::Generic::IEnumerable<GValue>^ right);  
multimap(System::Collections::Generic::IEnumerable<GValue>^ right,  
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
  
 `multimap();`  
  
 démarre la séquence contrôlée sans éléments, avec le prédicat de classement par défaut `key_compare()`.  Vous l'utilisez pour spécifier une séquence initiale contrôlée vide, avec le prédicat de classement par défaut.  
  
 Le constructeur :  
  
 `explicit multimap(key_compare^ pred);`  
  
 démarre la séquence contrôlée sans éléments, avec le prédicat de classement `pred`.  Vous l'utilisez pour spécifier une séquence initiale contrôlée vide, avec le prédicat de classement spécifié.  
  
 Le constructeur :  
  
 `multimap(multimap<Key, Mapped>% right);`  
  
 démarre la séquence contrôlée par la séquence `[``right``.`[multimap::begin](../dotnet/multimap-begin-stl-clr.md)`(),` `right``.`[multimap::end](../dotnet/multimap-end-stl-clr.md)`())`, avec le prédicat de classement par défaut.  Vous l'utilisez pour spécifier une séquence contrôlée initiale qui est une copie de la séquence contrôlée par l'objet tableau associatif \(multimap\) `right`, avec le prédicat de classement par défaut.  
  
 Le constructeur :  
  
 `multimap(multimap<Key, Mapped>^ right);`  
  
 démarre la séquence contrôlée par la séquence `[``right``->`[multimap::begin](../dotnet/multimap-begin-stl-clr.md)`(),` `right``->`[multimap::end](../dotnet/multimap-end-stl-clr.md)`())`, avec le prédicat de classement par défaut.  Vous l'utilisez pour spécifier une séquence contrôlée initiale qui est une copie de la séquence contrôlée par l'objet tableau associatif \(multimap\) `right`, avec le prédicat de classement par défaut.  
  
 Le constructeur :  
  
 `template<typename InIter>`  
  
 `multimap(InIter first, InIter last);`  
  
 démarre la séquence contrôlée par la séquence `[``first``,` `last``)`, avec le prédicat de classement par défaut.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence, avec le prédicat de classement par défaut.  
  
 Le constructeur :  
  
 `template<typename InIter>`  
  
 `multimap(InIter first, InIter last,`  
  
 `key_compare^ pred);`  
  
 démarre la séquence contrôlée par la séquence `[``first``,` `last``)`, avec le prédicat de classement par défaut `pred`.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence, avec le prédicat de classement spécifié.  
  
 Le constructeur :  
  
 `multimap(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 démarre la séquence contrôlée par la séquence désignée par l'énumérateur `right`, avec le prédicat de classement par défaut.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence décrite par un énumérateur, avec le prédicat de classement par défaut.  
  
 Le constructeur :  
  
 `multimap(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred);`  
  
 démarre la séquence contrôlée par la séquence désignée par l'énumérateur `right`, avec le prédicat de classement par défaut `pred`.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence décrite par un énumérateur, avec le prédicat de classement spécifié.  
  
## Exemple  
  
```  
// cliext_multimap_construct.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
// construct an empty container   
    Mymultimap c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mymultimap c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (Mymultimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mymultimap c3(c1.begin(), c1.end());   
    for each (Mymultimap::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mymultimap c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (Mymultimap::value_type elem in c4)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Mymultimap c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Mymultimap::value_type>^)%c3);   
    for each (Mymultimap::value_type elem in c5)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Mymultimap c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Mymultimap::value_type>^)%c3,   
                cliext::greater_equal<wchar_t>());   
    for each (Mymultimap::value_type elem in c6)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mymultimap c7(c4);   
    for each (Mymultimap::value_type elem in c7)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    Mymultimap c8(%c3);   
    for each (Mymultimap::value_type elem in c8)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **taille\(\) \= 0**  
 **\[a 1\] \[b 2\] \[c 3\]**  
**taille\(\) \= 0**  
 **\[c 3\] \[b 2\] \[a 1\]**  
 **\[a 1\] \[b 2\] \[c 3\]**  
 **\[c 3\] \[b 2\] \[a 1\]**  
 **\[a 1\] \[b 2\] \[c 3\]**  
 **\[c 3\] \[b 2\] \[a 1\]**  
 **\[c 3\] \[b 2\] \[a 1\]**  
 **\[a 1\] \[b 2\] \[c 3\]**   
## Configuration requise  
 **En\-tête :** \<cliext\/map\>  
  
 **Espace de nommage** cliext  
  
## Voir aussi  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multimap::generic\_container](../dotnet/multimap-generic-container-stl-clr.md)   
 [multimap::operator\=](../dotnet/multimap-operator-assign-stl-clr.md)