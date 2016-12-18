---
title: "multiset::multiset (STL/CLR) | Microsoft Docs"
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
  - "cliext::multiset::multiset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "multiset (membre) (STL/CLR)"
ms.assetid: a6ddb2df-d7cd-4b12-aee7-81da1f67f57f
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# multiset::multiset (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Construit un objet container.  
  
## Syntaxe  
  
```  
multiset();  
explicit multiset(key_compare^ pred);  
multiset(multiset<Key>% right);  
multiset(multiset<Key>^ right);  
template<typename InIter>  
    multisetmultiset(InIter first, InIter last);  
template<typename InIter>  
    multiset(InIter first, InIter last,  
        key_compare^ pred);  
multiset(System::Collections::Generic::IEnumerable<GValue>^ right);  
multiset(System::Collections::Generic::IEnumerable<GValue>^ right,  
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
  
 `multiset();`  
  
 démarre la séquence contrôlée sans éléments, avec le prédicat de classement par défaut `key_compare()`.  Vous l'utilisez pour spécifier une séquence initiale contrôlée vide, avec le prédicat de classement par défaut.  
  
 Le constructeur :  
  
 `explicit multiset(key_compare^ pred);`  
  
 démarre la séquence contrôlée sans éléments, avec le prédicat de classement `pred`.  Vous l'utilisez pour spécifier une séquence initiale contrôlée vide, avec le prédicat de classement spécifié.  
  
 Le constructeur :  
  
 `multiset(multiset<Key>% right);`  
  
 démarre la séquence contrôlée par la séquence `[``right``.`[multiset::begin](../dotnet/multiset-begin-stl-clr.md)`(),` `right``.`[multiset::end](../dotnet/multiset-end-stl-clr.md)`())`, avec le prédicat de classement par défaut.  Vous l'utilisez pour spécifier une séquence initiale contrôlée qui est une copie de la séquence contrôlée par l'objet multi ensemble `right`, avec le prédicat de classement par défaut.  
  
 Le constructeur :  
  
 `multiset(multiset<Key>^ right);`  
  
 démarre la séquence contrôlée par la séquence `[``right``->`[multiset::begin](../dotnet/multiset-begin-stl-clr.md)`(),` `right``->`[multiset::end](../dotnet/multiset-end-stl-clr.md)`())`, avec le prédicat de classement par défaut.  Vous l'utilisez pour spécifier une séquence initiale contrôlée qui est une copie de la séquence contrôlée par l'objet multi ensemble `right`, avec le prédicat de classement par défaut.  
  
 Le constructeur :  
  
 `template<typename InIter>`  
  
 `multiset(InIter first, InIter last);`  
  
 démarre la séquence contrôlée par la séquence `[``first``,` `last``)`, avec le prédicat de classement par défaut.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence, avec le prédicat de classement par défaut.  
  
 Le constructeur :  
  
 `template<typename InIter>`  
  
 `multiset(InIter first, InIter last,`  
  
 `key_compare^ pred);`  
  
 démarre la séquence contrôlée par la séquence `[``first``,` `last``)`, avec le prédicat de classement par défaut `pred`.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence, avec le prédicat de classement spécifié.  
  
 Le constructeur :  
  
 `multiset(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 démarre la séquence contrôlée par la séquence désignée par l'énumérateur `right`, avec le prédicat de classement par défaut.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence décrite par un énumérateur, avec le prédicat de classement par défaut.  
  
 Le constructeur :  
  
 `multiset(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred);`  
  
 démarre la séquence contrôlée par la séquence désignée par l'énumérateur `right`, avec le prédicat de classement par défaut `pred`.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence décrite par un énumérateur, avec le prédicat de classement spécifié.  
  
## Exemple  
  
```  
// cliext_multiset_construct.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
// construct an empty container   
    Mymultiset c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mymultiset c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mymultiset c3(c1.begin(), c1.end());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mymultiset c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Mymultiset c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Mymultiset c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c6)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Mymultiset c7(c4);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mymultiset c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **a b c**  
**size\(\) \= 0**  
 **c b a**  
 **a b c**  
 **c b a**  
 **a b c**  
 **c b a**  
 **c b a**  
 **a b c**   
## Configuration requise  
 **En\-tête :** \<cliext\/set\>  
  
 **Espace de nom** cliext  
  
## Voir aussi  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::generic\_container](../dotnet/multiset-generic-container-stl-clr.md)   
 [multiset::operator\=](../dotnet/multiset-operator-assign-stl-clr.md)