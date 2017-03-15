---
title: "list::pop_front (STL/CLR) | Microsoft Docs"
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
  - "cliext::list::pop_front"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre pop_front [STL/CLR]"
ms.assetid: 6a0bad42-6796-41d9-a3e9-1488b3882574
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# list::pop_front (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Supprime le premier élément.  
  
## Syntaxe  
  
```  
void pop_front();  
```  
  
## Notes  
 La méthode supprime le premier élément de la séquence contrôlée, qui doit être non\-vide.  Vous l'utilisez pour raccourcir la liste d'un élément au premier plan.  
  
## Exemple  
  
```  
// cliext_list_pop_front.cpp   
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
    c1.pop_front();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **b c**   
## Configuration requise  
 **En\-tête :** \<cliext\/list\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [list](../dotnet/list-stl-clr.md)   
 [list::pop\_back](../dotnet/list-pop-back-stl-clr.md)   
 [list::push\_back](../dotnet/list-push-back-stl-clr.md)   
 [list::push\_front](../dotnet/list-push-front-stl-clr.md)