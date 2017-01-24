---
title: "__func__ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__func__"
  - "__func___cpp"
dev_langs: 
  - "C++"
ms.assetid: a5299b8d-f0ee-4af2-91dd-8fb165e68798
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __func__
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\(C\+\+11\)** L'identificateur prédéfini \_\_func\_\_ est défini de manière implicite comme une chaîne contenant le nom non qualifié et sans ornement de la fonction englobante.  \_\_func\_\_ est géré par la norme C\+\+. Ce n'est pas une extension Microsoft.  
  
## Syntaxe  
  
```vb  
__func__  
```  
  
## Valeur de retour  
 Retourne un tableau de chaînes de type const char terminées par le caractère NULL qui contient le nom de la fonction.  
  
## Exemple  
  
```  
  
#include <string>  
#include <iostream>  
  
namespace Test  
{  
    struct Foo  
    {  
        static void DoSomething(int i, std::string s)  
        {  
           std::cout << __func__ << std::endl; // Output: DoSomething  
        }  
    };  
}  
int main()  
{  
    Test::Foo::DoSomething(42, "Hello");  
  
    return 0;  
}  
  
```  
  
## Configuration requise  
 C\+\+11