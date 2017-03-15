---
title: "vector::pop_back (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::vector::pop_back"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre pop_back [STL/CLR]"
ms.assetid: 7e9fb72c-e733-4434-a71c-e4389629a821
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# vector::pop_back (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Supprime le dernier élément.  
  
## Syntaxe  
  
```  
void pop_back();  
```  
  
## Notes  
 La méthode supprime le dernier élément de la séquence contrôlée, qui doit être non\-vide.  Vous l'utilisez pour raccourcir le vecteur par un élément en arrière\-plan.  
  
## Exemple  
  
```  
// cliext_vector_pop_back.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
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
 **En\-tête :** \<cliext\/vector\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [vecteur](../dotnet/vector-stl-clr.md)   
 [vector::push\_back](../dotnet/vector-push-back-stl-clr.md)