---
title: "hash_set::make_value (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_set::make_value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_value (membre) (STL/CLR)"
ms.assetid: 19819fee-d3a0-428d-92db-cba7235d37d4
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# hash_set::make_value (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Construit un objet valeur.  
  
## Syntaxe  
  
```  
static value_type make_value(key_type key);  
```  
  
#### Paramètres  
 key  
 Valeur clé à utiliser.  
  
## Notes  
 La fonction membre retourne un objet `value_type` dont la clé est `key`.  Vous l'utilisez pour composer un objet approprié à utiliser avec plusieurs autres fonctions membres.  
  
## Exemple  
  
```  
// cliext_hash_set_make_value.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(Myhash_set::make_value(L'a'));   
    c1.insert(Myhash_set::make_value(L'b'));   
    c1.insert(Myhash_set::make_value(L'c'));   
  
// display contents " a b c"   
    for each (Myhash_set::value_type elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**   
## Configuration requise  
 **En\-tête:** \<cliext\/hash\_set\>  
  
 **Espace de noms :** cliext  
  
## Voir aussi  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::key\_type](../dotnet/hash-set-key-type-stl-clr.md)   
 [hash\_set::value\_type](../dotnet/hash-set-value-type-stl-clr.md)