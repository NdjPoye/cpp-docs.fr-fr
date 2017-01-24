---
title: "list::begin (STL/CLR) | Microsoft Docs"
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
  - "cliext::list::begin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre begin [STL/CLR]"
ms.assetid: 3431467b-951a-498a-af8d-50f631da1646
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# list::begin (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Désigne le début de la séquence contrôlée.  
  
## Syntaxe  
  
```  
iterator begin();  
```  
  
## Notes  
 La méthode retourne un itérateur d'accès aléatoire qui désigne le premier élément de la séquence contrôlée ou la position juste après la fin d'une séquence vide.  Vous l'utilisez pour obtenir un itérateur qui désigne le début `current` de la séquence contrôlée, mais son état peut changer si la longueur de la séquence contrôlée change.  
  
## Exemple  
  
```  
// cliext_list_begin.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    cliext::list<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("*begin() = {0}", *it);   
    System::Console::WriteLine("*++begin() = {0}", *++it);   
  
// alter first two items and reinspect   
    *--it = L'x';   
    *++it = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
**\*begin\(\) \= a**  
**\*\+\+begin\(\) \= b**  
 **x y c**   
## Configuration requise  
 **En\-tête :** \<cliext\/list\>  
  
 **Espace de noms :** cliext  
  
## Voir aussi  
 [list](../dotnet/list-stl-clr.md)   
 [list::end](../dotnet/list-end-stl-clr.md)   
 [list::front](../dotnet/list-front-stl-clr.md)   
 [list::front\_item](../dotnet/list-front-item-stl-clr.md)