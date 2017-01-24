---
title: "bad_weak_ptr, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "memory/std::tr1::bad_weak_ptr"
  - "std::tr1::bad_weak_ptr"
  - "bad_weak_ptr"
  - "tr1::bad_weak_ptr"
  - "tr1.bad_weak_ptr"
  - "std.tr1.bad_weak_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_weak_ptr (classe)"
  - "bad_weak_ptr (classe) (TR1)"
ms.assetid: a09336d5-7237-4480-ab6b-3787e0e6025e
caps.latest.revision: 20
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# bad_weak_ptr, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Signale une exception weak\_ptr incorrecte.  
  
## Syntaxe  
  
```  
class bad_weak_ptr  
    : public std::exception {  
public:  
    bad_weak_ptr();  
    const char *what() throw();  
    };  
```  
  
## Notes  
 La classe décrit une exception qui peut être levée à partir du constructeur [shared\_ptr, classe](../standard-library/shared-ptr-class.md) qui accepte un argument de type [weak\_ptr, classe](../standard-library/weak-ptr-class.md).  La fonction membre `what` retourne `"bad_weak_ptr"`.  
  
## Exemple  
  
```  
// std_tr1__memory__bad_weak_ptr.cpp   
// compile with: /EHsc   
#include <memory>   
#include <iostream>   
  
int main()   
    {   
    std::weak_ptr<int> wp;   
  
     {   
    std::shared_ptr<int> sp(new int);   
    wp = sp;   
     }   
  
    try   
        {   
        std::shared_ptr<int> sp1(wp); // weak_ptr has expired   
        }   
    catch (const std::bad_weak_ptr&)   
        {   
        std::cout << "bad weak pointer" << std::endl;   
        }   
    catch (...)   
        {   
        std::cout << "unknown exception" << std::endl;   
        }   
  
    return (0);   
    }  
  
```  
  
  **pointeur faible incorrect**   
## Configuration requise  
 **En\-tête :** \<memory\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [weak\_ptr, classe](../standard-library/weak-ptr-class.md)