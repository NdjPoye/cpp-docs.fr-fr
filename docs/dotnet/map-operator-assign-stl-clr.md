---
title: "map::operator= (STL/CLR) | Microsoft Docs"
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
  - "cliext::map::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "opérateur= membre [STL/CLR]"
ms.assetid: d27d42c3-9910-407c-8b35-e09641345940
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# map::operator= (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Remplace la séquence contrôlée.  
  
## Syntaxe  
  
```  
map<Key, Mapped>% operator=(map<Key, Mapped>% right);  
```  
  
#### Paramètres  
 right  
 Conteneur à copier.  
  
## Notes  
 L'opérateur copie `right` dans l'objet, puis retourne `*this`.  Vous l'utilisez pour remplacer la séquence contrôlée par une copie de la séquence contrôlée dans `right`.  
  
## Exemple  
  
```  
// cliext_map_operator_as.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymap c2;   
    c2 = c1;   
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
 **\[a 1\] \[b 2\] \[c 3\]**   
## Configuration requise  
 **En\-tête:** \<cliext\/map\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [map](../dotnet/map-stl-clr.md)