---
title: "hash_multiset::hash_multiset (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multiset::hash_multiset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_multiset (membre) (STL/CLR)"
ms.assetid: 1b224c60-b714-4ed5-9234-79b61b92a953
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# hash_multiset::hash_multiset (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Construit un objet container.  
  
## Syntaxe  
  
```  
hash_multiset();  
explicit hash_multiset(key_compare^ pred);  
hash_multiset(key_compare^ pred, hasher^ hashfn);  
hash_multiset(hash_multiset<Key>% right);  
hash_multiset(hash_multiset<Key>^ right);  
template<typename InIter>  
    hash_multiset(InIter first, InIter last);  
template<typename InIter>  
    hash_multiset(InIter first, InIter last,  
        key_compare^ pred);  
template<typename InIter>  
    hash_multiset(InIter first, InIter last,  
        key_compare^ pred, hasher^ hashfn);  
hash_multiset(System::Collections::Generic::IEnumerable<GValue>^ right);  
hash_multiset(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
hash_multiset(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred, hasher^ hashfn);  
```  
  
#### Paramètres  
 premièrement  
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
 Le constructeur :  
  
 `hash_multiset();`  
  
 démarre la séquence contrôlée sans éléments, avec l'attribut de classement par défaut `key_compare()`, et avec la fonction de hachage par défaut.  Vous l'utilisez pour spécifier une séquence initiale contrôlée vide, avec le prédicat de classement par défaut et la fonction de hachage.  
  
 Le constructeur :  
  
 `explicit hash_multiset(key_compare^ pred);`  
  
 démarre la séquence contrôlée sans éléments, avec l'attribut de classement par défaut `pred`, et avec la fonction de hachage par défaut.  Vous l'utilisez pour spécifier une séquence initiale contrôlée vide, avec le prédicat spécifique de classement par défaut et la fonction de hachage par défaut.  
  
 Le constructeur :  
  
 `hash_multiset(key_compare^ pred, hasher^ hashfn);`  
  
 démarre la séquence contrôlée sans éléments, avec l'attribut de classement par défaut `pred`, et avec la fonction de hachage par défaut `hashfn`.  Vous l'utilisez pour spécifier une séquence initiale contrôlée vide, avec le prédicat spécifique de classement par défaut et la fonction de hachage.  
  
 Le constructeur :  
  
 `hash_multiset(hash_multiset<Key>% right);`  
  
 démarre la séquence contrôlée sans éléments par la séquence `[``right``.`[hash\_multiset::begin](../dotnet/hash-multiset-begin-stl-clr.md)`(),` `right``.`[hash\_multiset::end](../dotnet/hash-multiset-end-stl-clr.md)`())`, avec l'attribut de classement par défaut, et avec la fonction de hachage par défaut.  Vous l'utilisez pour spécifier une séquence contrôlée initiale qui est une copie de la séquence contrôlée par le code de hachage multiset de l'objet `right`, Avec le défaut ordonnant le prédicat et la fonction de hachage.  
  
 Le constructeur :  
  
 `hash_multiset(hash_multiset<Key>^ right);`  
  
 démarre la séquence contrôlée sans éléments par la séquence `[``right``->`[hash\_multiset::begin](../dotnet/hash-multiset-begin-stl-clr.md)`(),` `right``->`[hash\_multiset::end](../dotnet/hash-multiset-end-stl-clr.md)`())`, avec l'attribut de classement par défaut, et avec la fonction de hachage par défaut.  Vous l'utilisez pour spécifier une séquence contrôlée initiale qui est une copie de la séquence contrôlée par le code de hachage multiset de l'objet `right`, Avec le défaut ordonnant le prédicat et la fonction de hachage.  
  
 Le constructeur :  
  
 `template<typename InIter>`  
  
 `hash_multiset(InIter first, InIter last);`  
  
 démarre la séquence contrôlée sans éléments par la séquence `[``first``,` `last``)`, avec l'attribut de classement par défaut, et avec la fonction de hachage par défaut.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence, avec l'attribut et la fonction de hachage par défaut.  
  
 Le constructeur :  
  
 `template<typename InIter>`  
  
 `hash_multiset(InIter first, InIter last,`  
  
 `key_compare^ pred);`  
  
 démarre la séquence contrôlée sans éléments par la séquence `[``first``,` `last``)`, avec l'attribut de classement par défaut `pred`, et avec la fonction de hachage par défaut.  Vous l'utilisez pour faire de la séquence contrôlée d'une copie d'une autre séquence, avec l'attribut spécifique de classement et la fonction de hachage par défaut.  
  
 Le constructeur :  
  
 `template<typename InIter>`  
  
 `hash_multiset(InIter first, InIter last,`  
  
 `key_compare^ pred, hasher^ hashfn);`  
  
 Initialise la séquence contrôlée avec la séquence `[``first``,` `last``)`, avec le prédicat de classements `pred`, et avec la fonction de hachage `hashfn`.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence, avec l'attribut spécifié et la fonction de hachage par défaut.  
  
 Le constructeur :  
  
 `hash_multiset(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 démarre la séquence contrôlée par la séquence indiquée par l'énumérateur `right`, avec l'attribut par défaut, et avec la fonction de hachage par défaut.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence décrite par un énumérateur, avec le prédicat de classement par défaut et la fonction de hachage par défaut.  
  
 Le constructeur :  
  
 `hash_multiset(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred);`  
  
 démarre la séquence contrôlée par l'ordre indiqué par l'énumérateur `right`, avec l'attribut de classement par défaut `pred`, et avec la fonction de hachage par défaut.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence décrite par un énumérateur, avec le prédicat spécifié de classement par défaut et la fonction de hachage par défaut.  
  
 Le constructeur :  
  
 `hash_multiset(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred, hasher^ hashfn);`  
  
 démarre la séquence contrôlée par l'ordre indiqué par l'énumérateur `right`, avec l'attribut de classement par défaut `pred`, et avec la fonction de hachage par défaut `hashfn`.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence décrite par un énumérateur, avec le prédicat spécifique de classement par défaut et la fonction de hachage par défaut.  
  
## Exemple  
  
```  
// cliext_hash_multiset_construct.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
int myfun(wchar_t key)   
    { // hash a key   
    return (key ^ 0xdeadbeef);   
    }   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
// construct an empty container   
    Myhash_multiset c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Myhash_multiset c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule and hash function   
    Myhash_multiset c2h(cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_multiset::hasher(&myfun));   
    System::Console::WriteLine("size() = {0}", c2h.size());   
  
    c2h.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Myhash_multiset c3(c1.begin(), c1.end());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Myhash_multiset c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule and hash function   
    Myhash_multiset c4h(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_multiset::hasher(&myfun));   
    for each (wchar_t elem in c4h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Myhash_multiset c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Myhash_multiset c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c6)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule and hash function   
    Myhash_multiset c6h(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>(),   
                gcnew Myhash_multiset::hasher(&myfun));   
    for each (wchar_t elem in c6h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Myhash_multiset c7(c4);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myhash_multiset c8(%c3);   
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
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_multiset::generic\_container](../dotnet/hash-multiset-generic-container-stl-clr.md)   
 [hash\_multiset::operator\=](../dotnet/hash-multiset-operator-assign-stl-clr.md)