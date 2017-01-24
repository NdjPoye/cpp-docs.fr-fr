---
title: "hash_multimap::hash_multimap (STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_multimap::hash_multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_multimap (membre) (STL/CLR)"
ms.assetid: a1d576a7-5dc7-4ad9-abef-ee7a13caaec3
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_multimap::hash_multimap (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Construit un objet container.  
  
## Syntaxe  
  
```  
hash_multimap();  
explicit hash_multimap(key_compare^ pred);  
hash_multimap(key_compare^ pred, hasher^ hashfn);  
hash_multimap(hash_multimap<Key, Mapped>% right);  
hash_multimap(hash_multimap<Key, Mapped>^ right);  
template<typename InIter>  
    hash_multimaphash_multimap(InIter first, InIter last);  
template<typename InIter>  
    hash_multimap(InIter first, InIter last,  
        key_compare^ pred);  
template<typename InIter>  
    hash_multimap(InIter first, InIter last,  
        key_compare^ pred, hasher^ hashfn);  
hash_multimap(System::Collections::Generic::IEnumerable<GValue>^ right);  
hash_multimap(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
hash_multimap(System::Collections::Generic::IEnumerable<GValue>^ right,  
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
 Le constructeur :  
  
 `hash_multimap();`  
  
 démarre la séquence contrôlée sans éléments, avec l'attribut de classement par défaut `key_compare()`, et avec la fonction de hachage par défaut.  Vous l'utilisez pour spécifier une séquence initiale contrôlée vide, avec le prédicat de classement par défaut et la fonction de hachage.  
  
 Le constructeur :  
  
 `explicit hash_multimap(key_compare^ pred);`  
  
 démarre la séquence contrôlée sans éléments, avec l'attribut de classement par défaut `pred`, et avec la fonction de hachage par défaut.  Vous l'utilisez pour spécifier une séquence initiale contrôlée vide, avec le prédicat spécifique de classement par défaut et la fonction de hachage par défaut.  
  
 Le constructeur :  
  
 `hash_multimap(key_compare^ pred, hasher^ hashfn);`  
  
 démarre la séquence contrôlée sans éléments, avec l'attribut de classement par défaut `pred`, et avec la fonction de hachage par défaut `hashfn`.  Vous l'utilisez pour spécifier une séquence initiale contrôlée vide, avec le prédicat spécifique de classement par défaut et la fonction de hachage.  
  
 Le constructeur :  
  
 `hash_multimap(hash_multimap<Key, Mapped>% right);`  
  
 démarre la séquence contrôlée sans éléments par la séquence `[``right``.`[hash\_multimap::begin](../dotnet/hash-multimap-begin-stl-clr.md)`(),` `right``.`[hash\_multimap::end](../dotnet/hash-multimap-end-stl-clr.md)`())`, avec l'attribut de classement par défaut, et avec la fonction de hachage par défaut.  Vous l'utilisez pour spécifier une séquence contrôlée initiale qui est une copie de la séquence contrôlée par le code de hachage multi mappage de l'objet `right`, Avec le défaut ordonnant le prédicat et la fonction de hachage.  
  
 Le constructeur :  
  
 `hash_multimap(hash_multimap<Key, Mapped>^ right);`  
  
 démarre la séquence contrôlée sans éléments par la séquence `[``right``->`[hash\_multimap::begin](../dotnet/hash-multimap-begin-stl-clr.md)`(),` `right``->`[hash\_multimap::end](../dotnet/hash-multimap-end-stl-clr.md)`())`, avec l'attribut de classement par défaut, et avec la fonction de hachage par défaut.  Vous l'utilisez pour spécifier une séquence contrôlée initiale qui est une copie de la séquence contrôlée par le code de hachage multi mappage de l'objet `right`, Avec le défaut ordonnant le prédicat et la fonction de hachage.  
  
 Le constructeur :  
  
 `template<typename InIter>`  
  
 `hash_multimap(InIter first, InIter last);`  
  
 démarre la séquence contrôlée sans éléments par la séquence `[``first``,` `last``)`, avec l'attribut de classement par défaut, et avec la fonction de hachage par défaut.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence, avec l'attribut et la fonction de hachage par défaut.  
  
 Le constructeur :  
  
 `template<typename InIter>`  
  
 `hash_multimap(InIter first, InIter last,`  
  
 `key_compare^ pred);`  
  
 démarre la séquence contrôlée sans éléments par la séquence `[``first``,` `last``)`, avec l'attribut de classement par défaut `pred`, et avec la fonction de hachage par défaut.  Vous l'utilisez pour faire de la séquence contrôlée d'une copie d'une autre séquence, avec l'attribut spécifique de classement et la fonction de hachage par défaut.  
  
 Le constructeur :  
  
 `template<typename InIter>`  
  
 `hash_multimap(InIter first, InIter last,`  
  
 `key_compare^ pred, hasher^ hashfn);`  
  
 Initialise la séquence contrôlée avec la séquence `[``first``,` `last``)`, avec le prédicat de classements `pred`, et avec la fonction de hachage `hashfn`.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence, avec l'attribut spécifié et la fonction de hachage par défaut.  
  
 Le constructeur :  
  
 `hash_multimap(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 démarre la séquence contrôlée par la séquence indiquée par l'énumérateur `right`, avec l'attribut par défaut, et avec la fonction de hachage par défaut.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence décrite par un énumérateur, avec le prédicat de classement par défaut et la fonction de hachage par défaut.  
  
 Le constructeur :  
  
 `hash_multimap(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred);`  
  
 démarre la séquence contrôlée par l'ordre indiqué par l'énumérateur `right`, avec l'attribut de classement par défaut `pred`, et avec la fonction de hachage par défaut.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence décrite par un énumérateur, avec le prédicat spécifié de classement par défaut et la fonction de hachage par défaut.  
  
 Le constructeur :  
  
 `hash_multimap(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred, hasher^ hashfn);`  
  
 démarre la séquence contrôlée par l'ordre indiqué par l'énumérateur `right`, avec l'attribut de classement par défaut `pred`, et avec la fonction de hachage par défaut `hashfn`.  Vous l'utilisez pour faire de la séquence contrôlée une copie d'une autre séquence décrite par un énumérateur, avec le prédicat spécifique de classement par défaut et la fonction de hachage par défaut.  
  
## Exemple  
  
```  
// cliext_hash_multimap_construct.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
int myfun(wchar_t key)   
    { // hash a key   
    return (key ^ 0xdeadbeef);   
    }   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
// construct an empty container   
    Myhash_multimap c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Myhash_multimap c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (Myhash_multimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an ordering rule and hash function   
    Myhash_multimap c2h(cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_multimap::hasher(&myfun));   
    System::Console::WriteLine("size() = {0}", c2h.size());   
  
    c2h.insert(c1.begin(), c1.end());   
    for each (Myhash_multimap::value_type elem in c2h)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Myhash_multimap c3(c1.begin(), c1.end());   
    for each (Myhash_multimap::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Myhash_multimap c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (Myhash_multimap::value_type elem in c4)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule and hash function   
    Myhash_multimap c4h(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_multimap::hasher(&myfun));   
    for each (Myhash_multimap::value_type elem in c4h)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Myhash_multimap c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Myhash_multimap::value_type>^)%c3);   
    for each (Myhash_multimap::value_type elem in c5)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Myhash_multimap c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Myhash_multimap::value_type>^)%c3,   
                cliext::greater_equal<wchar_t>());   
    for each (Myhash_multimap::value_type elem in c6)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule and hash function   
    Myhash_multimap c6h(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Myhash_multimap::value_type>^)%c3,   
                cliext::greater_equal<wchar_t>(),   
                gcnew Myhash_multimap::hasher(&myfun));   
    for each (Myhash_multimap::value_type elem in c6h)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myhash_multimap c7(c4);   
    for each (Myhash_multimap::value_type elem in c7)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    Myhash_multimap c8(%c3);   
    for each (Myhash_multimap::value_type elem in c8)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **\[a 1\] \[b 2\] \[c 3\]**  
**size\(\) \= 0**  
 **\[a 1\] \[b 2\] \[c 3\]**  
**size\(\) \= 0**  
 **\[c 3\] \[b 2\] \[a 1\]**  
 **\[a 1\] \[b 2\] \[c 3\]**  
 **\[a 1\] \[b 2\] \[c 3\]**  
 **\[c 3\] \[b 2\] \[a 1\]**  
 **\[a 1\] \[b 2\] \[c 3\]**  
 **\[a 1\] \[b 2\] \[c 3\]**  
 **\[c 3\] \[b 2\] \[a 1\]**  
 **\[a 1\] \[b 2\] \[c 3\]**  
 **\[a 1\] \[b 2\] \[c 3\]**   
## Configuration requise  
 **En\-tête :** \<cliext\/hash\_map\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)   
 [hash\_multimap::generic\_container](../dotnet/hash-multimap-generic-container-stl-clr.md)   
 [hash\_multimap::operator\=](../dotnet/hash-multimap-operator-assign-stl-clr.md)