---
title: "pair::pair (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::pair::pair"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre pair [STL/CLR]"
ms.assetid: 188035f3-bd37-4b46-96dd-5ceb9a16df79
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# pair::pair (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Construit un objet de paire.  
  
## Syntaxe  
  
```  
pair();  
pair(pair<Coll>% right);  
pair(pair<Coll>^ right);  
pair(Value1 val1, Value2 val2);  
```  
  
#### Paramètres  
 right  
 Paires à enregistrer.  
  
 val1  
 Première valeur à inscrire.  
  
 val2  
 La seconde valeur à inscrire.  
  
## Notes  
 Constructeur.  
  
 `pair();`  
  
 initialise les paires stockées avec des valeurs créées par défaut.  
  
 Constructeur.  
  
 `pair(pair<Value1, Value2>% right);`  
  
 initialise les paires stockées avec `right``.`[pair::first](../dotnet/pair-first-stl-clr.md) et `right``.`[pair::second](../dotnet/pair-second-stl-clr.md).  
  
 `pair(pair<Value1, Value2>^ right);`  
  
 initialise les paires stockées avec `right``->`[pair::first](../dotnet/pair-first-stl-clr.md) et `right``>`[pair::second](../dotnet/pair-second-stl-clr.md).  
  
 Constructeur.  
  
 `pair(Value1 val1, Value2 val2);`  
  
 initialise les paires stockées avec avec `val1` et `val2`.  
  
## Exemple  
  
```  
// cliext_pair_construct.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
// construct an empty container   
    cliext::pair<wchar_t, int> c1;   
    System::Console::WriteLine("[{0}, {1}]",   
        c1.first == L'\0' ? "\\0" : "??", c1.second);   
  
// construct with a pair of values   
    cliext::pair<wchar_t, int> c2(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
// construct by copying another pair   
    cliext::pair<wchar_t, int> c3(c2);   
    System::Console::WriteLine("[{0}, {1}]", c3.first, c3.second);   
  
// construct by copying a pair handle   
    cliext::pair<wchar_t, int> c4(%c3);   
    System::Console::WriteLine("[{0}, {1}]", c4.first, c4.second);   
  
    return (0);   
    }  
  
```  
  
  **\[\\0, 0\]**  
**\[x, 3\]**  
**\[x, 3\]**  
**\[x, 3\]**   
## Configuration requise  
 **Header:** \<cliext\/utility\>  
  
 **Espace de noms:** cliext  
  
## Voir aussi  
 [paire](../dotnet/pair-stl-clr.md)