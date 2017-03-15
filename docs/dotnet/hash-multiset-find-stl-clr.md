---
title: "hash_multiset::find (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multiset::find"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre find [STL/CLR]"
ms.assetid: fbedeb37-242e-4c2a-b1f8-234bcfd9cd25
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# hash_multiset::find (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Recherche un élément qui correspond à une clé spécifiée.  
  
## Syntaxe  
  
```  
iterator find(key_type key);  
```  
  
#### Paramètres  
 key  
 Valeur de clé à rechercher.  
  
## Notes  
 Si au moins un élément dans la séquence contrôlée à un classement équivalent à `key`, la fonction membre retourne un itérateur indiquant un de ces éléments ; sinon il renvoie [hash\_multiset::end](../dotnet/hash-multiset-end-stl-clr.md)`()`.  Vous l'utilisez pour localiser un élément actuellement dans la séquence contrôlée qui correspond à une clé spécifiée.  
  
## Exemple  
  
```  
// cliext_hash_multiset_find.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("find {0} = {1}",   
        L'A', c1.find(L'A') != c1.end());   
    System::Console::WriteLine("find {0} = {1}",   
        L'b', *c1.find(L'b'));   
    System::Console::WriteLine("find {0} = {1}",   
        L'C', c1.find(L'C') != c1.end());   
    return (0);   
    }  
  
```  
  
  **a b c**  
**find A \= False**  
**find b \= b**  
**find C \= False**   
## Description  
 Remarquez que `find` ne garantit pas quel élément il trouve parmi plusieurs.  
  
## Configuration requise  
 **En\-tête :** \<cliext\/hash\_set\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_multiset::equal\_range](../dotnet/hash-multiset-equal-range-stl-clr.md)   
 [hash\_multiset::lower\_bound](../dotnet/hash-multiset-lower-bound-stl-clr.md)   
 [hash\_multiset::upper\_bound](../dotnet/hash-multiset-upper-bound-stl-clr.md)