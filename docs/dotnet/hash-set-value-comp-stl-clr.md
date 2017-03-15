---
title: "hash_set::value_comp (STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_set::value_comp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "membre value_comp [STL/CLR]"
ms.assetid: 7ef381ea-438b-48ce-b0cb-96d844ea5df7
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_set::value_comp (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Copie le classement délégué pour deux valeurs d'éléments.  
  
## Syntaxe  
  
```  
value_compare^ value_comp();  
```  
  
## Notes  
 La méthode retourne le délégué de tri utilisé pour trier la séquence contrôlée.  Vous l'utilisez pour comparer les valeurs de deux éléments.  
  
## Exemple  
  
```  
// cliext_hash_set_value_comp.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    Myhash_set::value_compare^ kcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **compare \(L'a', L'a'\) \= True**  
**compare\(L'a', L'b'\) \= True**  
**compare\(L'b', L'a'\) \= False**   
## Configuration requise  
 **En\-tête :** \<cliext\/hash\_set\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::value\_compare](../dotnet/hash-set-value-compare-stl-clr.md)   
 [hash\_set::value\_type](../dotnet/hash-set-value-type-stl-clr.md)