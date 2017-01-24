---
title: "multimap::insert (STL/CLR) | Microsoft Docs"
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
  - "cliext::multimap::insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre insert [STL/CLR]"
ms.assetid: 98922ea1-c7ed-4c53-8834-8a0470b11c9e
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# multimap::insert (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ajoute les éléments.  
  
## Syntaxe  
  
```  
iterator insert(value_type val);  
iterator insert(iterator where, value_type val);  
template<typename InIter>  
    void insert(InIter first, InIter last);  
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);  
```  
  
#### Paramètres  
 premier  
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
  
 La première fonction membre insère un élément qui a la valeur `val` et retourne un itérateur qui indique l'élément récemment inséré.  Vous l'utilisez pour insérer un élément.  
  
 La deuxième fonction membre insère un élément avec la valeur `val`, à `where` comme indicateur \(pour améliorer les performances\), et retourne un itérateur qui indique l'élément nouvellement inséré.  Vous l'utilisez pour insérer un élément unique qui peut être en regard de l'élément que vous connaissez.  
  
 La troisième fonction membre insère la séquence `[``first``,` `last``)`.  Vous l'utilisez pour insérer zéro ou plusieurs éléments copiés à partir d'une autre séquence.  
  
 La quatrième fonction membre insère la séquence indiquée par `right`.  Vous l'utilisez pour insérer une séquence décrite par un énumérateur.  
  
 Chaque insertion d'élément prend un temps proportionnel au logarithme du nombre d'éléments dans la séquence contrôlée.  L'insertion peut se produire dans le temps fixe amorti, toutefois, selon un indicateur qui indique un élément en regard du point d'insertion.  
  
## Exemple  
  
```  
// cliext_multimap_insert.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value, unique and duplicate   
    Mymultimap::iterator it =   
        c1.insert(Mymultimap::make_value(L'x', 24));   
    System::Console::WriteLine("insert([L'x' 24]) = [{0} {1}]",   
        it->first, it->second);   
  
    it = c1.insert(Mymultimap::make_value(L'b', 2));   
    System::Console::WriteLine("insert([L'b' 2]) = [{0} {1}]",   
        it->first, it->second);   
  
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    it = c1.insert(c1.begin(), Mymultimap::make_value(L'y', 25));   
    System::Console::WriteLine("insert(begin(), [L'y' 25]) = [{0} {1}]",   
        it->first, it->second);   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Mymultimap c2;   
    it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (Mymultimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Mymultimap c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::   
            IEnumerable<Mymultimap::value_type>^)%c1);   
    for each (Mymultimap::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
**insertion \(\[L'x' 24\]\) \= \[x 24\]**  
**insertion \(\[L'b' 2\]\) \= \[b 2\]**  
 **\[a 1\] \[b 2\] \[b 2\] \[c 3\] \[x 24\]**  
**insertion\(debut\(\), \[L'y' 25\]\) \= \[y 25\]**  
 **\[a 1\] \[b 2\] \[b 2\] \[c 3\] \[x 24\] \[y 25\]**  
 **\[a 1\] \[b 2\] \[b 2\] \[c 3\] \[x 24\]**  
 **\[a 1\] \[b 2\] \[b 2\] \[c 3\] \[x 24\] \[y 25\]**   
## Configuration requise  
 **En\-tête :** \<cliext\/map\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [multimap](../dotnet/multimap-stl-clr.md)