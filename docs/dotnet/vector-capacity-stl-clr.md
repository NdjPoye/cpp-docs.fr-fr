---
title: "vector::capacity (STL/CLR) | Microsoft Docs"
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
  - "cliext::vector::capacity"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre capacity [STL/CLR]"
ms.assetid: f82d8da9-8b4d-4288-8d18-8e9ca5911d87
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# vector::capacity (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Signale la taille de l'espace de stockage alloué pour le conteneur.  
  
## Syntaxe  
  
```  
size_type capacity();  
```  
  
## Notes  
 La fonction membre retourne l'espace actuellement alloué pour contenir la séquence contrôlée, une valeur au moins égale à [vector::size](../dotnet/vector-size-stl-clr.md)`()`.  Vous l'utilisez pour déterminer la quantité avec laquelle le conteneur peut croître avant qu'il doive réallouer le stockage de la séquence contrôlée.  
  
## Exemple  
  
```  
// cliext_vector_capacity.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1.at(i));   
    System::Console::WriteLine();   
  
// increase capacity   
    cliext::vector<wchar_t>::size_type cap = c1.capacity();   
    System::Console::WriteLine("capacity() = {0}, ok = {1}",   
        cap, c1.size() <= cap);   
    c1.reserve(cap + 5);   
    System::Console::WriteLine("capacity() = {0}, ok = {1}",   
        c1.capacity(), cap + 5 <= c1.capacity());   
    return (0);   
    }  
  
```  
  
  **a b c**  
**capacity\(\) \= 4, ok \= True**  
**capacity\(\) \= 9, ok \= True**   
## Description  
 Notez que les capacités réelles peuvent différer des valeurs présentées ici, à condition que tous les tests `ok` affichent vrai.  
  
## Configuration requise  
 **En\-tête :** \<cliext\/vector\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [vecteur](../dotnet/vector-stl-clr.md)   
 [vector::reserve](../dotnet/vector-reserve-stl-clr.md)