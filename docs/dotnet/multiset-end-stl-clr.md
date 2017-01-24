---
title: "multiset::end (STL/CLR) | Microsoft Docs"
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
  - "cliext::multiset::end"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre end [STL/CLR]"
ms.assetid: 225f8b74-f9b9-47ea-9603-43ac7c9a9734
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# multiset::end (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Désigne la fin de la séquence contrôlée.  
  
## Syntaxe  
  
```  
iterator end();  
```  
  
## Notes  
 La fonction membre retourne un itérateur bidirectionnel qui pointe uniquement au delà de la fin de la séquence contrôlée.  Vous l'utilisez pour obtenir un itérateur qui désigne la fin de la séquence contrôlée, son état ne peut changer si la longueur de la séquence contrôlée change.  
  
## Exemple  
  
```  
// cliext_multiset_end.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last two items   
    Mymultiset::iterator it = c1.end();   
    --it;   
    System::Console::WriteLine("*-- --end() = {0}", *--it);   
    System::Console::WriteLine("*--end() = {0}", *++it);   
    return (0);   
    }  
  
```  
  
  **a b c**  
**\*\-\- \-\-end\(\) \= b**  
**\*\-\-end\(\) \= c**   
## Configuration requise  
 **En\-tête :** \<cliext\/set\>  
  
 **Espace de nom** cliext  
  
## Voir aussi  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::begin](../dotnet/multiset-begin-stl-clr.md)