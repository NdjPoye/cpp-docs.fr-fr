---
title: "hash_multiset::hash_delegate (STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_multiset::hash_delegate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre hash_delegate [STL/CLR]"
ms.assetid: 61ccfdfb-6a3c-40aa-902f-49e004a31a75
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_multiset::hash_delegate (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Recherche un élément qui correspond à une clé spécifiée.  
  
## Syntaxe  
  
```  
hasher^ hash_delegate();  
```  
  
## Notes  
 La fonction membre retourne le délégué utilisé pour convertir une valeur de clé en un entier.  Vous l'utilisez pour hacher une clé.  
  
## Exemple  
  
```  
// cliext_hash_multiset_hash_delegate.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    Myhash_multiset::hasher^ myhash = c1.hash_delegate();   
  
    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));   
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));   
    return (0);   
    }  
  
```  
  
  **hash\(L'a'\) \= 1616896120**  
**hash\(L'b'\) \= 570892832**   
## Configuration requise  
 **En\-tête :** \<cliext\/hash\_set\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_multiset::hasher](../dotnet/hash-multiset-hasher-stl-clr.md)