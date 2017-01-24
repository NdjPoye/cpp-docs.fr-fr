---
title: "vector::empty (STL/CLR) | Microsoft Docs"
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
  - "cliext::vector::empty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre empty [STL/CLR]"
ms.assetid: c09fc4a3-bd79-4458-9a36-1d9c82ac36b1
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# vector::empty (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si aucun élément n'est présent.  
  
## Syntaxe  
  
```  
bool empty();  
```  
  
## Notes  
 La fonction membre retourne la valeur true pour une séquence contrôlée vide.  Équivaut à [vector::size](../dotnet/vector-size-stl-clr.md)`() == 0`.  Vous l'utilisez pour tester si le vecteur est vide.  
  
## Exemple  
  
```  
// cliext_vector_empty.cpp   
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
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
    return (0);   
    }  
  
```  
  
  **a b c**  
**size\(\) \= 3**  
**empty\(\) \= False**  
**size\(\) \= 0**  
**empty\(\) \= True**   
## Configuration requise  
 **En\-tête :** \<cliext\/vector\>  
  
 **Espace de noms :** cliext  
  
## Voir aussi  
 [vecteur](../dotnet/vector-stl-clr.md)   
 [vector::size](../dotnet/vector-size-stl-clr.md)