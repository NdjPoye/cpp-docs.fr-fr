---
title: "hash_map::lower_bound (STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_map::lower_bound"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre lower_bound [STL/CLR]"
ms.assetid: 7c88987a-9c77-4874-8052-192a148abbf1
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_map::lower_bound (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Recherche le début de la plage qui correspond à une clé spécifiée.  
  
## Syntaxe  
  
```  
iterator lower_bound(key_type key);  
```  
  
#### Paramètres  
 key  
 Valeur clé à rechercher.  
  
## Notes  
 La fonction membre détermine le premier élément `X` de la séquence contrôlée qui est haché dans le même compartiment que `key` et qui a un classement équivalent à `key`..  Si aucun de ces élément n'existe, cela retourne [hash\_map::end](../dotnet/hash-map-end-stl-clr.md)`()`; sinon cela renvoie un itérateur qui indique `X`.  Vous l'utilisez pour rechercher le début d'une séquence d'éléments figurant actuellement dans la séquence contrôlée qui correspond à une clé spécifiée.  
  
## Exemple  
  
```  
// cliext_hash_map_lower_bound.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
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
  
    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",   
        c1.lower_bound(L'x') == c1.end());   
  
    Myhash_map::iterator it = c1.lower_bound(L'a');   
    System::Console::WriteLine("*lower_bound(L'a') = [{0} {1}]",   
        it->first, it->second);   
    it = c1.lower_bound(L'b');   
    System::Console::WriteLine("*lower_bound(L'b') = [{0} {1}]",   
        it->first, it->second);   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
**faible\_limite\(L'x'\)\=\=fin\(\) \= Vrai**  
**\*faible\_limite\(L' a'\) \= \[a 1\]**  
**\*faible\_limite\(L'b'\) \= \[b 2\]**   
## Configuration requise  
 **En\-tête :** \<cliext\/hash\_map\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_map::count](../dotnet/hash-map-count-stl-clr.md)   
 [hash\_map::equal\_range](../dotnet/hash-map-equal-range-stl-clr.md)   
 [hash\_map::find](../dotnet/hash-map-find-stl-clr.md)   
 [hash\_map::upper\_bound](../dotnet/hash-map-upper-bound-stl-clr.md)