---
title: "hash_multiset::swap (STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_multiset::swap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre swap [STL/CLR]"
ms.assetid: b79372ab-ca51-494a-89cf-4e2da3ee3ff7
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_multiset::swap (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Échange le contenu de deux conteneurs.  
  
## Syntaxe  
  
```  
void swap(hash_multiset<Key>% right);  
```  
  
#### Paramètres  
 right  
 Conteneur avec lequel échanger le contenu.  
  
## Notes  
 La fonction membre permute les séquences réorganisées entre `this` et `right`.  Elle le fait en un temps constant et ne lève pas d'exception.  Vous l'utilisez comme méthode rapide d'échange du contenu de deux conteneurs.  
  
## Exemple  
  
```  
// cliext_hash_multiset_swap.cpp   
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
  
// construct another container with repetition of values   
    Myhash_multiset c2;   
    c2.insert(L'd');   
    c2.insert(L'e');   
    c2.insert(L'f');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// swap and redisplay   
    c1.swap(c2);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **d e f**  
 **d e f**  
 **a b c**   
## Configuration requise  
 **En\-tête :** \<cliext\/hash\_set\>  
  
 **Espace de nommage** cliext  
  
## Voir aussi  
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_multiset::operator\=](../dotnet/hash-multiset-operator-assign-stl-clr.md)