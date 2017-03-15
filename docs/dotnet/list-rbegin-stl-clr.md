---
title: "list::rbegin (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::rbegin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre rbegin [STL/CLR]"
ms.assetid: 99637376-8ac3-4e39-844a-b4f324a7c6ba
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# list::rbegin (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Désigne le début de la séquence contrôlée inversée.  
  
## Syntaxe  
  
```  
reverse_iterator rbegin();  
```  
  
## Notes  
 La fonction membre renvoie un Itérateur inversé qui désigne le dernier élément de la séquence contrôlée ou de la position juste après le début d'une séquence vide.  Par conséquent, il désigne le `beginning` de la séquence inverse.  Vous l'utilisez pour obtenir un itérateur qui désigne le début `current` de la séquence contrôlée vue dans l'ordre inverse, mais son état peut changer si la longueur de la séquence contrôlée change.  
  
## Exemple  
  
```  
// cliext_list_rbegin.cpp   
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
  
// inspect first two items in reversed sequence   
    cliext::list<wchar_t>::reverse_iterator rit = c1.rbegin();   
    System::Console::WriteLine("*rbegin() = {0}", *rit);   
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);   
  
// alter first two items and reinspect   
    *--rit = L'x';   
    *++rit = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
**\*rbegin\(\) \= c**  
**\*\+\+rbegin\(\) \= b**  
 **a y x**   
## Configuration requise  
 **En\-tête :** \<cliext\/list\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [list](../dotnet/list-stl-clr.md)   
 [list::begin](../dotnet/list-begin-stl-clr.md)   
 [list::end](../dotnet/list-end-stl-clr.md)   
 [list::rend](../dotnet/list-rend-stl-clr.md)