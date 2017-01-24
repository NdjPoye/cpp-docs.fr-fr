---
title: "hash_multiset::max_load_factor (STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_multiset::max_load_factor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre max_load_factor [STL/CLR]"
ms.assetid: ca0a6e8e-b889-47e4-9edd-c5a321fdeb8f
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_multiset::max_load_factor (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient ou définit les éléments maximum de chaque compartiment.  
  
## Syntaxe  
  
```  
float max_load_factor();  
void max_load_factor(float new_factor);  
```  
  
#### Paramètres  
 nouveau\_facteur  
 Nouveau facteur de charge maximale à sauvegarder.  
  
## Notes  
 La première fonction membre retourne l'actuel facteur de charge maximale stocké.  Vous l'utilisez pour déterminer la taille moyenne maximale des compartiments.  
  
 La deuxième fonction membre remplace le facteur de charge maximale de stockage par `new_factor`.  Aucun nouveau hachage automatique ne se produit jusqu'a l'insertion suivante.  
  
## Exemple  
  
```  
// cliext_hash_multiset_max_load_factor.cpp   
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
  
// inspect current parameters   
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());   
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());   
    System::Console::WriteLine("max_load_factor() = {0}",   
        c1.max_load_factor());   
    System::Console::WriteLine();   
  
// change max_load_factor and redisplay   
    c1.max_load_factor(0.25f);   
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());   
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());   
    System::Console::WriteLine("max_load_factor() = {0}",   
        c1.max_load_factor());   
    System::Console::WriteLine();   
  
// rehash and redisplay   
    c1.rehash(100);   
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());   
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());   
    System::Console::WriteLine("max_load_factor() = {0}",   
        c1.max_load_factor());   
    return (0);   
    }  
  
```  
  
  **a b c**  
**bucket\_count\(\) \= 16**  
**load\_factor\(\) \= 0,1875**  
**max\_load\_factor\(\) \= 4**  
**bucket\_count\(\) \= 16**  
**load\_factor\(\) \= 0,1875**  
**max\_load\_factor\(\) \= 0,25**  
**bucket\_count\(\) \= 128**  
**load\_factor\(\) \= 0,0234375**  
**max\_load\_factor\(\) \= 0,25**   
## Configuration requise  
 **En\-tête :** \<cliext\/hash\_set\>  
  
 **Espace de nommage:** cliext  
  
## Voir aussi  
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_multiset::bucket\_count](../dotnet/hash-multiset-bucket-count-stl-clr.md)   
 [hash\_multiset::load\_factor](../dotnet/hash-multiset-load-factor-stl-clr.md)   
 [hash\_multiset::rehash](../dotnet/hash-multiset-rehash-stl-clr.md)