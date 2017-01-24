---
title: "Erreur du compilateur C2707 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2707"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2707"
ms.assetid: 3deaf45c-74da-4c9d-acc6-b82412720b74
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2707
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : contexte incorrect pour une fonction intrinsèque  
  
 Les fonctions intrinsèques de gestion structurée des exceptions ne sont pas valides dans certains contextes :  
  
-   `_exception_code()` en dehors d'un filtre d'exception ou d'un bloc `__except` ;  
  
-   `_exception_info()` en dehors d'un filtre d'exception ;  
  
-   `_abnormal_termination()`  en dehors d'un bloc `__finally` ;  
  
 Pour corriger l'erreur, vérifiez que les fonctions intrinsèques de gestion des exceptions sont placées dans le contexte adapté.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2707 :  
  
```  
// C2707.cpp  
#include <windows.h>  
#include <stdio.h>  
  
LONG MyFilter(LONG excode)   
{  
    return (excode == EXCEPTION_ACCESS_VIOLATION ?  
        EXCEPTION_EXECUTE_HANDLER : EXCEPTION_CONTINUE_SEARCH);   // OK  
}  
  
LONG func(void)   
{  
    int x, y;  
    return(GetExceptionCode() == EXCEPTION_ACCESS_VIOLATION ?  // C2707  
             EXCEPTION_EXECUTE_HANDLER : EXCEPTION_CONTINUE_SEARCH);  
  
    __try   
    {  
        y = 0;  
        x = 4 / y;  
        return 0;  
     }  
  
    __except(MyFilter(GetExceptionCode()))   
    {  
        return(GetExceptionCode() == EXCEPTION_ACCESS_VIOLATION ? // ok  
               EXCEPTION_EXECUTE_HANDLER : EXCEPTION_CONTINUE_SEARCH);  
    }  
}  
  
int main()   
{  
    __try   
    {  
        func();  
    } __except(EXCEPTION_EXECUTE_HANDLER)  
    {  
        printf_s("Caught exception\n");  
    }  
}  
```