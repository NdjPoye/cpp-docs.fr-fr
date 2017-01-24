---
title: "list::erase (STL/CLR) | Microsoft Docs"
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
  - "cliext::list::erase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre erase [STL/CLR]"
ms.assetid: 78705058-1e83-441d-b267-d4fb56451c0b
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# list::erase (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Supprime les éléments placés aux positions spécifiées.  
  
## Syntaxe  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
```  
  
#### Paramètres  
 premier  
 Début de la plage à effacer.  
  
 last  
 Fin de la plage à effacer.  
  
 where  
 Élément à effacer.  
  
## Notes  
 La première fonction membre supprime l'élément de la séquence contrôlée désignée par `where`.  Vous l'utilisez pour retirer un élément.  
  
 La deuxième fonction membre supprime les éléments de la séquence contrôlée dans la plage `[``first``,` `last``)`.  Vous l'utilisez pour supprimer zéro ou plusieurs éléments contigus.  
  
 Les deux premières fonctions membres retournent un itérateur qui indique le premier élément restant au delà de tous les éléments supprimés, ou [list::end](../dotnet/list-end-stl-clr.md)`()` si aucun élément n'existe.  
  
 Lorsque vous effacez les éléments, le nombre de copies d'éléments est linéaire dans le nombre d'éléments entre la fin de l'effacement et la fin la plus proche de la séquence. \(En effaçant un ou plusieurs éléments à l'un ou l'autre bout de la séquence, la copie d'élément n'a pas lieu.\)  
  
## Exemple  
  
```  
// cliext_list_erase.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    System::Console::WriteLine("erase(begin()) = {0}",   
        *c1.erase(c1.begin()));   
  
// add elements and display " b c d e"   
    c1.push_back(L'd');   
    c1.push_back(L'e');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase all but end   
    cliext::list<wchar_t>::iterator it = c1.end();   
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",   
        *c1.erase(c1.begin(), --it));   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
  **a b c**  
**erase\(begin\(\)\) \= b**  
 **b c d e**  
**erase\(begin\(\), end\(\)\-1\) \= e**  
**size\(\) \= 1**   
## Configuration requise  
 **En\-tête :** \<cliext\/list\>  
  
 **Espace de nommage** cliext  
  
## Voir aussi  
 [list](../dotnet/list-stl-clr.md)   
 [list::clear](../dotnet/list-clear-stl-clr.md)