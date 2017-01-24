---
title: "hash_set::lower_bound (STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_set::lower_bound"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre lower_bound [STL/CLR]"
ms.assetid: 54fe8ee5-1977-4192-9cc6-b51e84b03a16
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_set::lower_bound (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Recherche le début de la plage qui correspond à une clé spécifiée.  
  
## Syntaxe  
  
```  
iterator lower_bound(key_type key);  
```  
  
#### Paramètres  
 key  
 Valeur de clé à rechercher.  
  
## Notes  
 La fonction membre détermine le premier élément `X` de la séquence contrôlée qui est découpée dans le même compartiment que `key` et qui a un ordonnancement équivalent à `key`.  Si aucun de ces éléments n'existe, il renvoie [hash\_set::end](../dotnet/hash-set-end-stl-clr.md)`()`; sinon il renvoie un itérateur qui indique `X`.  Vous l'utilisez pour rechercher le début d'une séquence d'éléments figurant actuellement dans la séquence contrôlée qui correspond à une clé spécifiée.  
  
## Exemple  
  
```  
// cliext_hash_set_lower_bound.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
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
  
    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",   
        c1.lower_bound(L'x') == c1.end());   
  
    System::Console::WriteLine("*lower_bound(L'a') = {0}",   
        *c1.lower_bound(L'a'));   
    System::Console::WriteLine("*lower_bound(L'b') = {0}",   
        *c1.lower_bound(L'b'));   
    return (0);   
    }  
  
```  
  
  **a b c**  
**faible\_limite\(L'x'\)\=\=fin\(\) \= Vrai**  
**\*lower\_bound \(A\) \= a**  
**L'\*lower\_bound \(B\) \= b**   
## Configuration requise  
 **En\-tête:** \<cliext\/hash\_set\>  
  
 **Espace de noms :** cliext  
  
## Voir aussi  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::count](../dotnet/hash-set-count-stl-clr.md)   
 [hash\_set::equal\_range](../dotnet/hash-set-equal-range-stl-clr.md)   
 [hash\_set::find](../dotnet/hash-set-find-stl-clr.md)   
 [hash\_set::upper\_bound](../dotnet/hash-set-upper-bound-stl-clr.md)