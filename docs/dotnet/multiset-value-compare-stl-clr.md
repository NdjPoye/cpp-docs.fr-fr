---
title: "multiset::value_compare (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multiset::value_compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "value_compare (membre) (STL/CLR)"
ms.assetid: 962e5a3b-5841-4b44-8801-5f5349e95c8f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# multiset::value_compare (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le classement délégué pour deux valeurs d'élements.  
  
## Syntaxe  
  
```  
Microsoft::VisualC::StlClr::BinaryDelegate<generic_value, generic_value, bool>  
    value_compare;  
```  
  
## Notes  
 Le type est un synonyme de délégué qui détermine le classement de ses valeurs d'arguments.  
  
## Exemple  
  
```  
// cliext_multiset_value_compare.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    Mymultiset::value_compare^ kcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **compare\(L'a', L'a'\) \= Faux**  
**compare\(L'a', L'b'\) \= Vrai**  
**compare\(L'b', L'a'\) \= Faux**   
## Configuration requise  
 **En\-tête :** \<cliext\/set\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::key\_compare](../dotnet/multiset-key-compare-stl-clr.md)   
 [multiset::value\_comp](../dotnet/multiset-value-comp-stl-clr.md)   
 [multiset::value\_type](../dotnet/multiset-value-type-stl-clr.md)