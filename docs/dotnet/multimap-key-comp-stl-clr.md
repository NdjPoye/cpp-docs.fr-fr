---
title: "multimap::key_comp (STL/CLR) | Microsoft Docs"
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
  - "cliext::multimap::key_comp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre key_comp [STL/CLR]"
ms.assetid: 05250549-d589-4e1d-8ae9-321ff4ad384b
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# multimap::key_comp (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Copie le délégué de classement pour deux clés.  
  
## Syntaxe  
  
```  
key_compare^key_comp();  
```  
  
## Notes  
 La fonction considérée retourne le délégué de classement utilisé pour ordonner la séquence contrôlée.  Vous l'utilisez pour comparer deux clés.  
  
## Exemple  
  
```  
// cliext_multimap_key_comp.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    Mymultimap::key_compare^ kcomp = c1.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
  
// test a different ordering rule   
    Mymultimap c2 = cliext::greater<wchar_t>();   
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
 **En\-tête :** \<cliext\/map\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multimap::key\_compare](../dotnet/multimap-key-compare-stl-clr.md)   
 [multimap::key\_type](../dotnet/multimap-key-type-stl-clr.md)