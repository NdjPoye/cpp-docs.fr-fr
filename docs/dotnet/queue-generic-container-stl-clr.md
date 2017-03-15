---
title: "queue::generic_container (STL/CLR) | Microsoft Docs"
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
  - "cliext::queue::generic_container"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "generic_container (membre) (STL/CLR)"
ms.assetid: 58e07f5e-a854-48fa-b505-9bb82c1cac69
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# queue::generic_container (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le type de l'interface générique pour l'adaptateur de conteneur.  
  
## Syntaxe  
  
```  
typedef Microsoft::VisualC::StlClr::IQueue<Value>  
    generic_container;  
```  
  
## Notes  
 Le type décrit l'interface générique pour cette classe d'adaptateur au conteneur de modèle.  
  
## Exemple  
  
```  
// cliext_queue_generic_container.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Myqueue::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1->get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    gc1->push(L'd');   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify original and display generic   
    c1.push(L'e');   
    for each (wchar_t elem in gc1->get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b c**  
 **a b c d**  
 **a b c d e**   
## Configuration requise  
 **En\-tête :** \<cliext\/queue\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [queue](../dotnet/queue-stl-clr.md)