---
title: "list::pop_back (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::pop_back"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre pop_back [STL/CLR]"
ms.assetid: 03fe8e0e-461b-41c4-8e20-97d0d4ed0feb
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# list::pop_back (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Supprime le dernier élément sélectionné.  
  
## Syntaxe  
  
```  
void pop_back();  
```  
  
## Notes  
 La fonction membre supprime le dernier élément de la séquence contrôlée, qui doit être non\-vide.  Vous l'utilisez pour raccourcir la liste d'un élément au bout.  
  
## Exemple  
  
```  
// cliext_list_pop_back.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// pop an element and redisplay   
    c1.pop_back();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b**   
## Configuration requise  
 **En\-tête :** \<cliext\/list\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [list](../dotnet/list-stl-clr.md)   
 [list::pop\_front](../dotnet/list-pop-front-stl-clr.md)   
 [list::push\_back](../dotnet/list-push-back-stl-clr.md)   
 [list::push\_front](../dotnet/list-push-front-stl-clr.md)