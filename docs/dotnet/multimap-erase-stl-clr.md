---
title: "multimap::erase (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multimap::erase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre erase [STL/CLR]"
ms.assetid: 94623cfc-4464-44a6-afd4-90a36828ac2b
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# multimap::erase (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Supprime les éléments placés aux positions spécifiées.  
  
## Syntaxe  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
bool erase(key_type key)  
```  
  
#### Paramètres  
 premier  
 Début de la plage à effacer.  
  
 key  
 Valeur de clé à supprimer.  
  
 last  
 Fin de la plage à effacer.  
  
 where  
 Élément à effacer.  
  
## Notes  
 La première fonction membre supprime l'élément de la séquence contrôlée vers laquelle pointe `where`, et retourne un itérateur qui indique le premier élément restant au delà de l'élément supprimé, ou [multimap::end](../dotnet/multimap-end-stl-clr.md)`()` si aucun tel élément n'existe.  Vous l'utilisez pour retirer un élément.  
  
 La deuxième fonction membre supprime les éléments de la séquence contrôlée dans la plage `[``first``,` `last``)`, et retourne un itérateur qui désigne le premier élément restant au delà de tous les éléments supprimés, ou `end()` si aucun tel élément n'existe.  Vous l'utilisez pour supprimer zéro ou plusieurs éléments contigus.  
  
 La troisième fonction membre supprime tout élément de la séquence contrôlée de la clé de tri équivalent à `key`, puis retourne le nombre d'éléments supprimés.  Vous l'utilisez pour supprimer et compter les éléments qui correspondent à la clé spécifiée.  
  
 Chaque suppression d'élément prend un temps proportionnel au logarithme du nombre d'éléments dans la séquence contrôlée.  
  
## Exemple  
  
```  
// cliext_multimap_erase.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    cliext::multimap<wchar_t, int> c1;   
    c1.insert(cliext::multimap<wchar_t, int>::make_value(L'a', 1));   
    c1.insert(cliext::multimap<wchar_t, int>::make_value(L'b', 2));   
    c1.insert(cliext::multimap<wchar_t, int>::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (cliext::multimap<wchar_t, int>::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    cliext::multimap<wchar_t, int>::iterator it =   
        c1.erase(c1.begin());   
    System::Console::WriteLine("erase(begin()) = [{0} {1}]",   
        it->first, it->second);   
  
// add elements and display " b c d e"   
    c1.insert(cliext::multimap<wchar_t, int>::make_value(L'd', 4));   
    c1.insert(cliext::multimap<wchar_t, int>::make_value(L'e', 5));   
    for each (cliext::multimap<wchar_t, int>::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// erase all but end   
    it = c1.end();   
    it = c1.erase(c1.begin(), --it);   
    System::Console::WriteLine("erase(begin(), end()-1) = [{0} {1}]",   
        it->first, it->second);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// erase end   
    System::Console::WriteLine("erase(L'x') = {0}", c1.erase(L'x'));   
    System::Console::WriteLine("erase(L'e') = {0}", c1.erase(L'e'));   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
**erase\(begin\(\)\) \= \[b 2\]**  
 **\[b 2\] \[c 3\] \[d 4\] \[e 5\]**  
**erase\(begin\(\), end\(\)\-1\) \= \[e 5\]**  
**size\(\) \= 1**  
**erase\(L'x'\) \= 0**  
**erase\(L'e'\) \= 1**   
## Configuration requise  
 **En\-tête :** \<cliext\/map\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multimap::clear](../dotnet/multimap-clear-stl-clr.md)