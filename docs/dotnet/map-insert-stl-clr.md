---
title: "map::insert (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::map::insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre insert [STL/CLR]"
ms.assetid: 599c702e-7db0-45b8-8247-4ff041a3639c
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# map::insert (STL/CLR)
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
 premièrement  
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
  
 La deuxième méthode insère un élément avec la valeur `val`, utilisant `where` comme indicateur \(pour améliorer les performances\), et retourne un itérateur qui indique l'élément nouvellement inséré.  Vous l'utilisez pour insérer un élément unique qui peut être en regard de l'élément que vous connaissez.  
  
 La troisième méthode insère la séquence `[``first``,` `last``)`.  Vous l'utilisez pour insérer zéro ou plusieurs éléments copiés à partir d'une autre séquence.  
  
 La quatrième méthode insère la séquence indiquée par `right`.  Vous l'utilisez pour insérer une séquence décrite par un énumérateur.  
  
 Chaque insertion d'élément prend un temps proportionnel au logarithme du nombre d'éléments dans la séquence contrôlée.  L'insertion peut se produire en temps fixe amorti, toutefois, selon un indicateur qui indique un élément en regard du point d'insertion.  
  
## Exemple  
  
```  
// cliext_map_insert.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
typedef Mymap::pair_iter_bool Pairib;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value, unique and duplicate   
// insert a single value, success and failure   
    Pairib pair1 = c1.insert(Mymap::make_value(L'x', 24));   
    System::Console::WriteLine("insert([L'x' 24]) = [[{0} {1}] {2}]",   
        pair1.first->first, pair1.first->second, pair1.second);   
  
    pair1 = c1.insert(Mymap::make_value(L'b', 2));   
    System::Console::WriteLine("insert([L'b' 2]) = [[{0} {1}] {2}]",   
        pair1.first->first, pair1.first->second, pair1.second);   
  
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    Mymap::iterator it =   
        c1.insert(c1.begin(), Mymap::make_value(L'y', 25));   
    System::Console::WriteLine("insert(begin(), [L'y' 25]) = [{0} {1}]",   
        it->first, it->second);   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Mymap c2;   
    it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (Mymap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Mymap c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::   
            IEnumerable<Mymap::value_type>^)%c1);   
    for each (Mymap::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
**insert\(\[L'x' 24\]\) \= \[\[x 24\] True\]**  
**insert\(\[L'b' 2\]\) \= \[\[b 2\] False\]**  
 **\[a 1\] \[b 2\] \[c 3\] \[x 24\]**  
**insert\(begin\(\), \[L'y' 25\]\) \= \[y 25\]**  
 **\[a 1\] \[b 2\] \[c 3\] \[x 24\] \[y 25\]**  
 **\[a 1\] \[b 2\] \[c 3\] \[x 24\]**  
 **\[a 1\] \[b 2\] \[c 3\] \[x 24\] \[y 25\]**   
## Configuration requise  
 **En\-tête :** \<cliext\/map\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [map](../dotnet/map-stl-clr.md)