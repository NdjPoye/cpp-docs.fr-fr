---
title: "not2 (STL/CLR) | Microsoft Docs"
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
  - "cliext::not2"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "not2 (fonction) (STL/CLR)"
ms.assetid: f8aedcca-e4d1-4430-93b4-83dd55579d04
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# not2 (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Génère un `binary_negate` pour un foncteur.  
  
## Syntaxe  
  
```  
template<typename Fun>  
    binary_negate<Fun> not2(Fun% functor);  
```  
  
## Template Parameters  
 Fun  
 Type du foncteur.  
  
## Paramètres de fonction  
 foncteur  
 Le foncteur à encapsuler.  
  
## Notes  
 La fonction de modèle retourne [binary\_negate](../dotnet/binary-negate-stl-clr.md)`<``Fun``>(functor)`.  Vous l'utilisez comme façon d'encapsuler un foncteur à deux argument dans un founcteur qui livre sa logique NOT.  
  
## Exemple  
  
```  
// cliext_not2.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c2;   
    c2.push_back(4);   
    c2.push_back(4);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 4 4"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::less<int> less_op;   
  
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(),   
        cliext::binary_negate<cliext::less<int> >(less_op));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::not2(less_op));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **4 3**  
 **4 4**  
 **1 0**  
 **1 0**   
## Configuration requise  
 **En\-tête :** \<cliext\/functional\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [binary\_negate](../dotnet/binary-negate-stl-clr.md)