---
title: "collection_adapter::operator= (STL/CLR) | Microsoft Docs"
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
  - "cliext::collection_adapter::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "opérateur= membre [STL/CLR]"
ms.assetid: 45365a33-3b56-4cb7-962f-81c20d8901d3
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# collection_adapter::operator= (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Remplace le descripteur BCL stocké.  
  
## Syntaxe  
  
```  
collection_adapter<Coll>% operator=(collection_adapter<Coll>% right);  
```  
  
#### Paramètres  
 right  
 Adaptateur à copier.  
  
## Notes  
 L'opérateur membre copie `right` dans l'objet, puis retourne `*this`.  Vous l'utilisez pour remplacer le descripteur BCL stocké par une copie du descripteur BCL stocké dans `right`.  
  
## Exemple  
  
```  
// cliext_collection_adapter_operator_as.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mycoll c2;   
    c2 = c1;   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b c**   
## Configuration requise  
 **En\-tête :** \<cliext\/adapter\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [collection\_adapter](../dotnet/collection-adapter-stl-clr.md)