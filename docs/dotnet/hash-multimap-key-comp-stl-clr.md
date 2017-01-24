---
title: "hash_multimap::key_comp (STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_multimap::key_comp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre key_comp [STL/CLR]"
ms.assetid: 221d0bfe-19ad-4c34-9b10-77921be32459
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_multimap::key_comp (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Copie le classement délégué pour deux clés.  
  
## Syntaxe  
  
```  
key_compare^key_comp();  
```  
  
## Notes  
 La fonction considérée retourne le délégué de classement utilisé pour ordonner la séquence contrôlée.  Vous l'utilisez pour comparer deux clés.  
  
## Exemple  
  
```  
// cliext_hash_multimap_key_comp.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    Myhash_multimap::key_compare^ kcomp = c1.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
  
// test a different ordering rule   
    Myhash_multimap c2 = cliext::greater<wchar_t>();   
    kcomp = c2.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    return (0);   
    }  
  
```  
  
  **compare \(L'a', L'a'\) \= True**  
**compare\(L'a', L'b'\) \= True**  
**compare\(L'b', L'a'\) \= False**  
**compare\(L'a', L'a'\) \= False**  
**compare\(L'a', L'b'\) \= Faux**  
**compare\(L'b', L'a'\) \= Vrai**   
## Configuration requise  
 **En\-tête :** \<cliext\/hash\_map\>  
  
 **Espace de nom** cliext  
  
## Voir aussi  
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)   
 [hash\_multimap::key\_compare](../dotnet/hash-multimap-key-compare-stl-clr.md)   
 [hash\_multimap::key\_type](../dotnet/hash-multimap-key-type-stl-clr.md)