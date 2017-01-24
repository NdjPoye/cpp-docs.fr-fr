---
title: "multiset::key_compare (STL/CLR) | Microsoft Docs"
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
  - "cliext::multiset::key_compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "key_compare (membre) (STL/CLR)"
ms.assetid: 172c1ac7-fc71-409e-898a-5521eea7201a
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# multiset::key_compare (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Délégué d'organisation de deux clés.  
  
## Syntaxe  
  
```  
Microsoft::VisualC::StlClr::BinaryDelegate<GKey, GKey, bool>  
    key_compare;  
```  
  
## Notes  
 Le type est un synonyme de délégué qui détermine le classement de ses arguments principaux.  
  
## Exemple  
  
```  
// cliext_multiset_key_compare.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    Mymultiset::key_compare^ kcomp = c1.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
  
// test a different ordering rule   
    Mymultiset c2 = cliext::greater<wchar_t>();   
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
  
  **compare\(L'a', L'a'\) \= Faux**  
**compare\(L'a', L'b'\) \= Vrai**  
**compare\(L'b', L'a'\) \= Faux**  
**compare\(L'a', L'a'\) \= Faux**  
**compare\(L'a', L'b'\) \= Faux**  
**compare\(L'b', L'a'\) \= Vrai**   
## Configuration requise  
 **Header:** \<cliext\/set\>  
  
 **Espace de noms:** cliext  
  
## Voir aussi  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::key\_comp](../dotnet/multiset-key-comp-stl-clr.md)   
 [multiset::key\_type](../dotnet/multiset-key-type-stl-clr.md)   
 [multiset::value\_compare](../dotnet/multiset-value-compare-stl-clr.md)