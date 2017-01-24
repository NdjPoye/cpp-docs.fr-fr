---
title: "hash_set::insert (STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_set::insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre insert [STL/CLR]"
ms.assetid: 0a9bc9aa-012e-4101-9e8c-f1f4b6b76af7
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_set::insert (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ajoute les éléments.  
  
## Syntaxe  
  
```  
cliext::pair<iterator, bool> insert(value_type val);  
iterator insert(iterator where, value_type val);  
template<typename InIter>  
    void insert(InIter first, InIter last);  
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);  
```  
  
#### Paramètres  
 first  
 Début de la plage à insérer.  
  
 last  
 Fin de la plage à insérer.  
  
 right  
 Énumération à insérer.  
  
 val  
 Valeur clé à insérer.  
  
 where  
 Où insérer dans le conteneur \(indice uniquement\).  
  
## Notes  
 Chacune des fonctions membres insère une séquence spécifiée par les opérandes restants.  
  
 La première fonction membre essaie d'insérer un élément avec la valeur `val`, et retourne une paire de valeurs `X`.  Si `X.second` a la valeur true, `X.first` désigne l'élément nouvellement inséré ; dans le cas contraire, `X.first` désigne un élément avec un classement équivalent qui existe déjà et aucun nouvel élément n'est inséré.  Vous l'utilisez pour insérer un élément.  
  
 La deuxième fonction membre insère un élément avec la valeur `val`, à `where` comme indicateur \(pour améliorer les performances\), et retourne un itérateur qui indique l'élément nouvellement inséré.  Vous l'utilisez pour insérer un élément unique qui peut être en regard de l'élément que vous connaissez.  
  
 La troisième fonction membre insère la séquence `[``first``,` `last``)`.  Vous l'utilisez pour insérer zéro ou plusieurs éléments copiés à partir d'une autre séquence.  
  
 La quatrième fonction membre insère la séquence indiquée par `right`.  Vous l'utilisez pour insérer une séquence décrite par un énumérateur.  
  
 Chaque insertion d'élément prend un temps proportionnel au logarithme du nombre d'éléments dans la séquence contrôlée.  L'insertion peut se produire dans le temps fixe amorti, toutefois, selon un indicateur qui indique un élément en regard du point d'insertion.  
  
## Exemple  
  
```  
// cliext_hash_set_insert.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
typedef Myhash_set::pair_iter_bool Pairib;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value, unique and duplicate   
    Pairib pair1 = c1.insert(L'x');   
    System::Console::WriteLine("insert(L'x') = [{0} {1}]",   
        *pair1.first, pair1.second);   
  
    pair1 = c1.insert(L'b');   
    System::Console::WriteLine("insert(L'b') = [{0} {1}]",   
        *pair1.first, pair1.second);   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    System::Console::WriteLine("insert(begin(), L'y') = {0}",   
        *c1.insert(c1.begin(), L'y'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Myhash_set c2;   
    Myhash_set::iterator it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Myhash_set c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
**insertion \(L'x'\) \= \[x Vrai\]**  
**insertion \(L'b'\) \= \[b Faux\]**  
 **a b c x**  
**insert\(begin\(\), L'y'\) \= y**  
 **a b c x y**  
 **a b c x**  
 **a b c x y**   
## Configuration requise  
 **En\-tête:** \<cliext\/hash\_set\>  
  
 **Espace de noms:** cliext  
  
## Voir aussi  
 [hash\_set](../dotnet/hash-set-stl-clr.md)