---
title: "operator= (deque) (STL/CLR) | Microsoft Docs"
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
  - "cliext::deque::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "opérateur= membre [STL/CLR]"
ms.assetid: 0851c6e2-29a2-45da-8c5a-e0b2f5357fb6
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator= (deque) (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Remplace la séquence contrôlée.  
  
## Syntaxe  
  
```  
deque<Value>% operator=(deque<Value>% right);  
```  
  
#### Paramètres  
 right  
 Conteneur à copier.  
  
## Notes  
 L'opérateur membre copie `right` dans l'objet, puis retourne `*this`.  Vous l'utilisez pour remplacer la séquence contrôlée par une copie de la séquence contrôlée dans `right`.  
  
## Exemple  
  
```  
// cliext_deque_operator_as.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::deque<wchar_t> c2;   
    c2 = c1;   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b c**   
## Configuration requise  
 **En\-tête :** \<cliext\/deque\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [deque](../dotnet/deque-stl-clr.md)   
 [deque::assign](../dotnet/deque-assign-stl-clr.md)