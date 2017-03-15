---
title: "hash_map::insert (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_map::insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre insert [STL/CLR]"
ms.assetid: 52926ec7-ad4e-4791-a043-46136ee40a69
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# hash_map::insert (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ajoute des éléments.  
  
## Syntaxe  
  
```  
cliext::pair<iterator, bool> insert(value_type val);  
iterator insert(iterator where, value_type val);  
template<typename InIter>  
    void insert(InIter first, InIter last);  
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);  
```  
  
#### Paramètres  
 premièrement  
 Début de la série à insérer.  
  
 last  
 Fin de la série à insérer.  
  
 right  
 Enumération à insérer.  
  
 val  
 Valeur clé à insérer.  
  
 where  
 Endroit dans le conteneur où insérer \(indication seulement\).  
  
## Notes  
 Chacune des fonctions membres insère une séquence spécifiée par les opérandes restantes.  
  
 La première fonction membre s'efforce d'insérer un élément avec la valeur `val`, et renvoie une paire de valeurs `X`.  Si `X.second` est vrai, `X.first` désigne un élément récemment ajouté ; sinon `X.first` désigne un élément avec un ordonnement équivalent qui existe déjà et aucun élément déjà inséré.  Vous l'utilisez pour insérer un élément seul.  
  
 La deuxième fonction membre insère un élément avec la valeur `val`, en utilisant `where` comme indice \(pour améliorer les performances\), et renvoie un itérateur qui désigne l'élément dernièrement inséré.  Vous l'utilisez pour insérer un seul élément qui peut être adjacent à un élément que vous connaissez.  
  
 La troisième fonction membre insère une séquence `[``first``,` `last``)`.  Vous l'utilisez pour insérer zéro ou plus d'éléments copiés à partir d'une autre séquence.  
  
 La quatrième fonction membre insère la séquence désignée par `right`.  Utilisez\-le pour insérer une séquence décrite par l'énumérateur.  
  
 Chaque d'insertion d'élément prend un temps proportionnel au logarithme du nombre d'éléments dans la séquence contrôlée.  L'insertion peut arriver dans un temps constant amorti, malgré le fait que l'indication désigne un élément adjacent au point d'insertion.  
  
## Exemple  
  
```  
// cliext_hash_map_insert.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
typedef Myhash_map::pair_iter_bool Pairib;   
int main()   
    {   
    Myhash_map c1;   
    c1.insert(Myhash_map::make_value(L'a', 1));   
    c1.insert(Myhash_map::make_value(L'b', 2));   
    c1.insert(Myhash_map::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value, unique and duplicate   
    Pairib pair1 =   
        c1.insert(Myhash_map::make_value(L'x', 24));   
    System::Console::WriteLine("insert([L'x' 24]) = [{0} {1}] {2}",   
        pair1.first->first, pair1.first->second, pair1.second);   
  
    pair1 = c1.insert(Myhash_map::make_value(L'b', 2));   
    System::Console::WriteLine("insert([L'b' 2]) = [{0} {1}] {2}",   
        pair1.first->first, pair1.first->second, pair1.second);   
  
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    Myhash_map::iterator it =   
        c1.insert(c1.begin(), Myhash_map::make_value(L'y', 25));   
    System::Console::WriteLine("insert(begin(), [L'y' 25]) = [{0} {1}]",   
        it->first, it->second);   
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Myhash_map c2;   
    it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (Myhash_map::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Myhash_map c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::   
            IEnumerable<Myhash_map::value_type>^)%c1);   
    for each (Myhash_map::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
**insert\(\[L'x' 24\]\) \= \[x 24\] True**  
**insert\(\[L'b' 2\]\) \= \[b 2\] False**  
 **\[a 1\] \[b 2\] \[c 3\] \[x 24\]**  
**insert\(begin\(\), \[L'y' 25\]\) \= \[y 25\]**  
 **\[a 1\] \[b 2\] \[c 3\] \[x 24\] \[y 25\]**  
 **\[a 1\] \[b 2\] \[c 3\] \[x 24\]**  
 **\[a 1\] \[b 2\] \[c 3\] \[x 24\] \[y 25\]**   
## Configuration requise  
 **En\-tête :** \<cliext\/hash\_map\>  
  
 **Espace de noms:** cliext  
  
## Voir aussi  
 [hash\_map](../dotnet/hash-map-stl-clr.md)