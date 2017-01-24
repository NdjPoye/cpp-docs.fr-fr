---
title: "_alloca | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_alloca"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_alloca"
  - "alloca"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_alloca (fonction)"
  - "alloca (fonction)"
  - "allocation de mémoire, pile"
ms.assetid: 74488eb1-b71f-4515-88e1-cdd03b6f8225
caps.latest.revision: 23
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _alloca
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Alloue de la mémoire sur la pile.  Cette fonction est déconseillée parce qu'une version plus sécurisée est disponible ; consultez [\_malloca](../../c-runtime-library/reference/malloca.md).  
  
## Syntaxe  
  
```  
void *_alloca(   
   size_t size   
);  
```  
  
#### Paramètres  
 \[in\] `size`  
 Octets à allouer de la pile.  
  
## Valeur de retour  
 La routine `_alloca` retourne un pointeur `void` à l'espace alloué, qui est garanti d'être aligné correctement pour le stockage de n'importe quel type d'objet.  Si `size` a la valeur 0, `_alloca` alloue un élément de longueur zéro et retourne un pointeur valide à cet élément.  
  
 Une exception de dépassement de capacité de la pile est générée si l'espace ne peut pas être alloué.  L'exception de dépassement de capacité de la pile n'est pas une exception C\+\+ ; il s'agit d'une exception structurée.  Au lieu d'utiliser la gestion des exceptions C\+\+, vous devez utiliser [Structurées gestion des exceptions](../../cpp/structured-exception-handling-c-cpp.md) \(ELLE\).  
  
## Notes  
 `_alloca` alloue des octets `size` depuis la pile de programme.  L'espace alloué est automatiquement libéré lorsque l'appel de la fonction existe \(pas lorsque l'allocation passe simplement en dehors de l'étendue\).  Par conséquent, ne transmettez pas la valeur du pointeur retournée par `_alloca` comme argument de [disponible](../../c-runtime-library/reference/free.md).  
  
 Des restrictions s'appliquent dans l'appel explicite à `_alloca` dans un gestionnaire des exceptions \(EH\).  Les routines EH qui fonctionnent sur des processeurs de classe x86 s'exécutent dans leur propre cadre de mémoire : Ils effectuent des tâches dans l'espace mémoire qui n'est pas basé sur la position actuelle du pointeur de pile de la fonction englobante.  Les implémentations les plus courantes incluent des expressions de gestion des exceptions structurées \(SEH\) de Windows NT et de clause CATCH C\+\+.  Par conséquent, appeler explicitement `_alloca` dans les scénarios suivants entraîne l'échec de programme pendant le retour à la routine d'appel EH :  
  
-   Expression de filtre d'exceptions Windows NT SEH : `__except` \(`_alloca ()` \)  
  
-   Gestionnaire d'exceptions final Windows NT SEH: `__finally` {}`_alloca ()`  
  
-   Expression de la clause CATCH C\+\+ EH  
  
 Toutefois, `_alloca` peut être appelée directement à partir d'une routine EH ou d'un rappel fourni par l'application qui est appelée par un des scénarios EH précédemment répertoriés.  
  
> [!IMPORTANT]
>  Dans Windows XP, si `_alloca` est appelée dans un bloc try\/catch, vous devez appeler [\_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md) du bloc CATCH.  
  
 En plus des restrictions précitées, quand vous utilisez l'option [\/clr \(Compilation du common langage runtime\)](../../build/reference/clr-common-language-runtime-compilation.md), `_alloca` ne peut pas être utilisé dans des blocs d' `__except`.  Pour plus d'informations, consultez [\/clr Restrictions](../../build/reference/clr-restrictions.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_alloca`|\<malloc.h\>|  
  
## Exemple  
  
```  
// crt_alloca.c  
// This program demonstrates the use of  
// _alloca and trapping any exceptions  
// that may occur.  
  
#include <windows.h>  
#include <stdio.h>  
#include <malloc.h>  
  
int main()  
{  
    int     size = 1000;  
    int     errcode = 0;  
    void    *pData = NULL;  
  
    // Note: Do not use try/catch for _alloca,  
    // use __try/__except, since _alloca throws  
    // Structured Exceptions, not C++ exceptions.  
  
    __try {  
        // An unbounded _alloca can easily result in a   
        // stack overflow.  
        // Checking for a size < 1024 bytes is recommended.  
        if (size > 0 && size < 1024)  
        {  
            pData = _alloca( size );  
            printf_s( "Allocated %d bytes of stack at 0x%p",  
                      size, pData);  
        }  
        else  
        {  
            printf_s("Tried to allocate too many bytes.\n");  
        }  
    }  
  
    // If an exception occured with the _alloca function  
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )  
    {  
        printf_s("_alloca failed!\n");  
  
        // If the stack overflows, use this function to restore.  
        errcode = _resetstkoflw();  
        if (errcode)  
        {  
            printf_s("Could not reset the stack!\n");  
            _exit(1);  
        }  
    };  
}  
```  
  
  **Alloué 1000 octets de pile à 0x0012FB50**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md)   
 [\_malloca](../../c-runtime-library/reference/malloca.md)