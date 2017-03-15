---
title: "hash_set::hash_set (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_set::hash_set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_set (membre) (STL/CLR)"
ms.assetid: 006414ed-db5a-4c08-ac81-4a8ae57d0aad
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# hash_set::hash_set (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Construit un objet container.  
  
## Syntaxe  
  
```  
hash_set();  
explicit hash_set(key_compare^ pred);  
hash_set(key_compare^ pred, hasher^ hashfn);  
hash_set(hash_set<Key>% right);  
hash_set(hash_set<Key>^ right);  
template<typename InIter>  
    hash_sethash_set(InIter first, InIter last);  
template<typename InIter>  
    hash_set(InIter first, InIter last,  
        key_compare^ pred);  
template<typename InIter>  
    hash_set(InIter first, InIter last,  
        key_compare^ pred, hasher^ hashfn);  
hash_set(System::Collections::Generic::IEnumerable<GValue>^ right);  
hash_set(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
hash_set(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred, hasher^ hashfn);  
```  
  
#### Paramètres  
 premier  
 Début de la plage à insérer.  
  
 hashfn  
 Fonction de hachage pour faire correspondre les clés aux compartiments correspondants.  
  
 last  
 Fin de la plage à insérer.  
  
 pred  
 Classer l'attribut de la séquence contrôlée.  
  
 right  
 Objet ou plage à insérer.  
  
## Notes  
 Le constructeur:  
  
 `hash_set();`  
  
 démarre la séquence contrôlée sans éléments, avec l'attribut de classement par défaut `key_compare()`, et avec la fonction de hachage par défaut.  Vous l'utilisez pour spécifier une séquence initiale contrôlée vide, avec le prédicat de classement par défaut et la fonction de hachage.  
  
 Le constructeur :  
  
 `explicit hash_set(key_compare^ pred);`  
  
 démarre la séquence contrôlée sans éléments, avec l'attribut de classement par défaut `pred`, et avec la fonction de hachage par défaut.  Vous l'utilisez pour spécifier une séquence initiale contrôlée vide, avec le prédicat spécifique de classement par défaut et la fonction de hachage par défaut.  
  
 Le constructeur :  
  
 `hash_set(key_compare^ pred, hasher^ hashfn);`  
  
 démarre la séquence contrôlée sans éléments, avec l'attribut de classement par défaut `pred`, et avec la fonction de hachage par défaut `hashfn`.  Vous l'utilisez pour spécifier une séquence initiale contrôlée vide, avec le prédicat spécifique de classement par défaut et la fonction de hachage.  
  
 Le constructeur :  
  
 `hash_set(hash_set<Key>% right);`  
  
 démarre la séquence contrôlée sans éléments par la séquence `[``right``.`[hash\_set::begin](../dotnet/hash-set-begin-stl-clr.md)`(),` `right``.`[hash\_set::end](../dotnet/hash-set-end-stl-clr.md)`())`, avec l'attribut de classement par défaut, et avec la fonction de hachage par défaut.  Vous l'utilisez pour spécifier une séquence initiale contrôlée qui est une copie de la séquence contrôlée par l'objet hash\_set `right`, avec le prédicat de classement par défaut et la fonction de hachage.  
  
 Le constructeur :  
  
 `hash_set(hash_set<Key>^ right);`  
  
 démarre la séquence contrôlée sans éléments par la séquence `[``right``->`[hash\_set::begin](../dotnet/hash-set-begin-stl-clr.md)`(),` `right``->`[hash\_set::end](../dotnet/hash-set-end-stl-clr.md)`())`, avec l'attribut de classement par défaut, et avec la fonction de hachage par défaut.  Vous l'utilisez pour spécifier une séquence initiale contrôlée qui est une copie de la séquence contrôlée par l'objet hash\_set `right`, avec le prédicat de classement par défaut et la fonction de hachage.  
  
 Le constructeur :  
  
 `template<typename InIter>`  
  
 `hash_set(InIter first, InIter last);`  
  
 démarre la séquence contrôlée sans éléments par la séquence `[``first``,` `last``)`, avec l'attribut de classement par défaut, et avec la fonction de hachage par défaut.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence, avec l'attribut et la fonction de hachage par défaut.  
  
 Le constructeur :  
  
 `template<typename InIter>`  
  
 `hash_set(InIter first, InIter last,`  
  
 `key_compare^ pred);`  
  
 démarre la séquence contrôlée sans éléments par la séquence `[``first``,` `last``)`, avec l'attribut de classement par défaut `pred`, et avec la fonction de hachage par défaut.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence, l'attribut spécifique de classement et la fonction de hachage étants par défaut.  
  
 Le constructeur :  
  
 `template<typename InIter>`  
  
 `hash_set(InIter first, InIter last,`  
  
 `key_compare^ pred, hasher^ hashfn);`  
  
 Initialise la séquence contrôlée avec la séquence `[``first``,` `last``)`, avec le prédicat de classements `pred`, et avec la fonction de hachage `hashfn`.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence, avec l'attribut spécifié et la fonction de hachage par défaut.  
  
 Le constructeur :  
  
 `hash_set(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 démarre la séquence contrôlée par la séquence indiquée par l'énumérateur `right`, avec l'attribut par défaut, et avec la fonction de hachage par défaut.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence décrite par un énumérateur, avec le prédicat de classement par défaut et la fonction de hachage par défaut.  
  
 Le constructeur :  
  
 `hash_set(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred);`  
  
 démarre la séquence contrôlée par l'ordre indiqué par l'énumérateur `right`, avec l'attribut de classement par défaut `pred`, et avec la fonction de hachage par défaut.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence décrite par un énumérateur, avec le prédicat spécifié de classement par défaut et la fonction de hachage par défaut.  
  
 Le constructeur :  
  
 `hash_set(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred, hasher^ hashfn);`  
  
 démarre la séquence contrôlée par l'ordre indiqué par l'énumérateur `right`, avec l'attribut de classement par défaut `pred`, et avec la fonction de hachage par défaut `hashfn`.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence décrite par un énumérateur, avec le prédicat spécifique de classement par défaut et la fonction de hachage par défaut.  
  
## Exemple  
  
```  
// cliext_hash_set_construct.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
int myfun(wchar_t key)   
    { // hash a key   
    return (key ^ 0xdeadbeef);   
    }   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
// construct an empty container   
    Myhash_set c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Myhash_set c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule and hash function   
    Myhash_set c2h(cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_set::hasher(&myfun));   
    System::Console::WriteLine("size() = {0}", c2h.size());   
  
    c2h.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Myhash_set c3(c1.begin(), c1.end());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Myhash_set c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule and hash function   
    Myhash_set c4h(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_set::hasher(&myfun));   
    for each (wchar_t elem in c4h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Myhash_set c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Myhash_set c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c6)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule and hash function   
    Myhash_set c6h(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>(),   
                gcnew Myhash_set::hasher(&myfun));   
    for each (wchar_t elem in c6h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Myhash_set c7(c4);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myhash_set c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **a b c**  
**size\(\) \= 0**  
 **a b c**  
**size\(\) \= 0**  
 **c b a**  
 **a b c**  
 **a b c**  
 **c b a**  
 **a b c**  
 **a b c**  
 **c b a**  
 **a b c**  
 **a b c**   
## Configuration requise  
 **En\-tête :** \<cliext\/hash\_set\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::generic\_container](../dotnet/hash-set-generic-container-stl-clr.md)   
 [hash\_set::operator\=](../dotnet/hash-set-operator-assign-stl-clr.md)