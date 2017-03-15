---
title: "vector::front_item (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::vector::front_item"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre front_item [STL/CLR]"
ms.assetid: 7db87868-3e54-4c67-a06b-01bcfff3128d
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# vector::front_item (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Accède au premier élément.  
  
## Syntaxe  
  
```  
property value_type front_item;  
```  
  
## Notes  
 La propriété accède au premier élément de la séquence contrôlée, qui ne doit pas être vide.  Vous l'utilisez pour lire ou écrire le premier élément, lorsque vous savez qu'il existe.  
  
## Exemple  
  
```  
// cliext_vector_front_item.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first item   
    System::Console::WriteLine("front_item = {0}", c1.front_item);   
  
// alter first item and reinspect   
    c1.front_item = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
**front\_item \= a**  
 **x b c**   
## Configuration requise  
 **En\-tête :** \<cliext\/vector\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [vecteur](../dotnet/vector-stl-clr.md)   
 [vector::back](../dotnet/vector-back-stl-clr.md)   
 [vector::back\_item](../dotnet/vector-back-item-stl-clr.md)   
 [vector::front](../dotnet/vector-front-stl-clr.md)