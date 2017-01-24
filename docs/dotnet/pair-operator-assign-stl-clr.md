---
title: "pair::operator= (STL/CLR) | Microsoft Docs"
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
  - "cliext::pair::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "opérateur= membre [STL/CLR]"
ms.assetid: b6228037-914e-4efa-8491-65dbb0e93f61
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# pair::operator= (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Remplace les paires de valeurs stockées.  
  
## Syntaxe  
  
```  
pair<Value1, Value2>% operator=(pair<Value1, Value2>% right);  
```  
  
#### Paramètres  
 right  
 Paires à copier.  
  
## Notes  
 L'opérateur membre copie `right` dans l'objet, puis retourne `*this`.  Vous l'utilisez pour remplacer les paires de valeurs stockées par une copie dans `right`.  
  
## Exemple  
  
```  
// cliext_pair_operator_as.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
// assign to a new pair   
    cliext::pair<wchar_t, int> c2;   
    c2 = c1;   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
    return (0);   
    }  
  
```  
  
  **\[x, 3\]**  
**\[x, 3\]**   
## Configuration requise  
 **En\-tête :** \<cliext\/utility\>  
  
 **Espace de nommage** cliext  
  
## Voir aussi  
 [paire](../dotnet/pair-stl-clr.md)