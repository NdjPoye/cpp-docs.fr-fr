---
title: "stack::operator= (STL/CLR) | Microsoft Docs"
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
  - "cliext::stack::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "opérateur= membre [STL/CLR]"
ms.assetid: 6f23b5fc-667e-4c6c-b43a-88b30da2ecac
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# stack::operator= (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Remplace la séquence contrôlée.  
  
## Syntaxe  
  
```  
stack <Value, Container>% operator=(stack <Value, Container>% right);  
```  
  
#### Paramètres  
 right  
 Adaptateur de conteneur à copier.  
  
## Notes  
 L'opérateur membre copie `right` dans l'objet, puis retourne `*this`.  Vous l'utilisez pour remplacer la séquence contrôlée par une copie de la séquence contrôlée dans `right`.  
  
## Exemple  
  
```  
// cliext_stack_operator_as.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mystack c2;   
    c2 = c1;   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b c**   
## Configuration requise  
 **En\-tête :** \<cliext\/stack\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [pile](../dotnet/stack-stl-clr.md)   
 [stack::assign](../dotnet/stack-assign-stl-clr.md)