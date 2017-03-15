---
title: "vector::rbegin (STL/CLR) | Microsoft Docs"
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
  - "cliext::vector::rbegin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre rbegin [STL/CLR]"
ms.assetid: fad410b9-fe79-4820-9be5-6b7e0219a1af
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# vector::rbegin (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Désigne le début de la séquence contrôlée inversée.  
  
## Syntaxe  
  
```  
reverse_iterator rbegin();  
```  
  
## Notes  
 La fonction membre renvoie un Itérateur inverse qui désigne le dernier élément de la séquence contrôlée ou la position juste après le début d'une séquence vide.  Par conséquent, il désigne le `beginning` de la séquence inverse.  Vous l'utilisez pour obtenir un itérateur qui désigne le début `current` de la séquence contrôlée vue dans l'ordre inverse, mais son état peut changer si la longueur de la séquence contrôlée change.  
  
## Exemple  
  
```  
// cliext_vector_rbegin.cpp   
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
  
// inspect first two items in reversed sequence   
    cliext::vector<wchar_t>::reverse_iterator rit = c1.rbegin();   
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
**\*\+\+rdevient\(\) \= b**  
 **a y x**   
## Configuration requise  
 **En\-tête :** \<cliext\/vector\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [vecteur](../dotnet/vector-stl-clr.md)   
 [vector::begin](../dotnet/vector-begin-stl-clr.md)   
 [vector::end](../dotnet/vector-end-stl-clr.md)   
 [vector::rend](../dotnet/vector-rend-stl-clr.md)