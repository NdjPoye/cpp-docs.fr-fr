---
title: "multiset::count (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multiset::count"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre count [STL/CLR]"
ms.assetid: 6c668667-0047-4101-8dfc-0f538655b3d1
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# multiset::count (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Recherche le nombre d'éléments qui correspondent à une clé spécifiée.  
  
## Syntaxe  
  
```  
size_type count(key_type key);  
```  
  
#### Paramètres  
 key  
 Valeur de clé à rechercher.  
  
## Notes  
 La fonction membre retourne le nombre d'éléments dans la séquence contrôlée dont le classement est équivalent à `key`.  Vous l'utilisez pour déterminer le nombre d'éléments actuellement dans la séquence contrôlée qui correspondent à une clé spécifiée.  
  
## Exemple  
  
```  
// cliext_multiset_count.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));   
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));   
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));   
    return (0);   
    }  
  
```  
  
  **a b c**  
**compte\(L'A'\) \= 0**  
**compte\(L'b'\) \= 1**  
**compte\(L'C'\) \= 0**   
## Configuration requise  
 **En\-tête :** \<cliext\/set\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::equal\_range](../dotnet/multiset-equal-range-stl-clr.md)