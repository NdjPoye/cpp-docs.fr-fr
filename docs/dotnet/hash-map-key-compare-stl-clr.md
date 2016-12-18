---
title: "hash_map::key_compare (STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_map::key_compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "key_compare (membre) (STL/CLR)"
ms.assetid: 9564d049-67fc-4293-b896-c4a96e771f86
caps.latest.revision: 18
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_map::key_compare (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le classement délégué pour deux clés.  
  
## Syntaxe  
  
```  
Microsoft::VisualC::StlClr::BinaryDelegate<GKey, GKey, bool>  
    key_compare;  
```  
  
## Notes  
 Le type est un synonyme de délégué qui détermine le classement de ses arguments principaux.  
  
## Exemple  
  
```  
// cliext_hash_map_key_compare.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    Myhash_map::key_compare^ kcomp = c1.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
  
// test a different ordering rule   
    Myhash_map c2 = cliext::greater<wchar_t>();   
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
**compare\(L'a', L'b'\) \= Vrai**  
**compare\(L'b', L'a'\) \= Faux**  
**compare\(L'a', L'a'\) \= Faux**  
**compare\(L'a', L'b'\) \= Faux**  
**compare\(L'b', L'a'\) \= Vrai**   
## Configuration requise  
 **En\-tête :** \<cliext\/hash\_map\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_map::key\_comp](../dotnet/hash-map-key-comp-stl-clr.md)   
 [hash\_map::key\_type](../dotnet/hash-map-key-type-stl-clr.md)   
 [hash\_map::value\_compare](../dotnet/hash-map-value-compare-stl-clr.md)