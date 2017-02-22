---
title: "_malloca | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_malloca"
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
  - "malloca"
  - "_malloca"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_malloca (fonction)"
  - "malloca (fonction)"
  - "allocation de mémoire, pile"
ms.assetid: 293992df-cfca-4bc9-b313-0a733a6bb936
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# _malloca
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Alloue de la mémoire sur la pile.  Il s'agit d'une version de [\_alloca](../../c-runtime-library/reference/alloca.md) avec des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
void *_malloca(   
   size_t size   
);  
```  
  
#### Paramètres  
 `size`  
 Octets à allouer de la pile.  
  
## Valeur de retour  
 La routine `_malloca` retourne un pointeur `void` à l'espace alloué, qui est garanti d'être aligné correctement pour le stockage de n'importe quel type d'objet.  Si `size` a la valeur 0, `_malloca` alloue un élément de longueur zéro et retourne un pointeur valide à cet élément.  
  
 Une exception de dépassement de capacité de la pile est générée si l'espace ne peut pas être alloué.  L'exception de dépassement de capacité de la pile n'est pas une exception C\+\+ ; il s'agit d'une exception structurée.  Au lieu d'utiliser la gestion des exceptions C\+\+, vous devez utiliser [Structurées gestion des exceptions](../../cpp/structured-exception-handling-c-cpp.md) \(ELLE\).  
  
## Notes  
 `_malloca` alloue des octets `size` de la pile de programme ou du segment de mémoire si la requête dépasse une certaine taille en octets donnée par `_ALLOCA_S_THRESHOLD`.  La différence entre `_malloca` et `_alloca` est que  `_alloca` renvoie toujours vers la pile, quelle que soit la taille.  Contrairement à `_alloca`, qui n'exige pas ou n'est pas autorisé à un appel à `free` pour libérer de la mémoire ainsi allouée, `_malloca` requiert l'utilisation de [\_freea](../../c-runtime-library/reference/freea.md) pour libérer del  la mémoire.  En mode débogage, `_malloca` toujours alloue la mémoire du segment.  
  
 Des restrictions s'appliquent dans l'appel explicite à `_malloca` dans un gestionnaire des exceptions \(EH\).  Les routines EH qui fonctionnent sur des processeurs de classe x86 s'exécutent dans leur propre cadre de mémoire : Ils effectuent des tâches dans l'espace mémoire qui n'est pas basé sur la position actuelle du pointeur de pile de la fonction englobante.  Les implémentations les plus courantes incluent des expressions de gestion des exceptions structurées \(SEH\) de Windows NT et de clause CATCH C\+\+.  Par conséquent, appeler explicitement `_malloca` dans les scénarios suivants entraîne l'échec de programme pendant le retour à la routine d'appel EH :  
  
-   Expression de filtre d'exceptions Windows NT SEH : `__except` \(`_malloca ()` \)  
  
-   Gestionnaire d'exceptions final Windows NT SEH: `__finally` {}`_malloca ()`  
  
-   Expression de la clause CATCH  C\+\+ EH  
  
 Toutefois, `_malloca` peut être appelée directement à partir d'une routine EH ou d'un rappel fourni par l'application qui est appelée par un des scénarios EH précédemment répertoriés.  
  
> [!IMPORTANT]
>  Dans Windows XP, si `_malloca` est appelée dans un bloc try\/catch, vous devez appeler [\_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md) du bloc CATCH.  
  
 En plus des restrictions précitées, quand vous utilisez l'option [\/clr \(Compilation du common langage runtime\)](../../build/reference/clr-common-language-runtime-compilation.md), `_malloca` ne peut pas être utilisé dans des blocs d'`__except`.  Pour plus d'informations, consultez [\/clr Restrictions](../../build/reference/clr-restrictions.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_malloca`|\<malloc.h\>|  
  
## Exemple  
  
```  
// crt_malloca_simple.c  
#include <stdio.h>  
#include <malloc.h>  
  
void Fn()  
{  
   char * buf = (char *)_malloca( 100 );  
   // do something with buf  
   _freea( buf );  
}  
  
int main()  
{  
   Fn();  
}  
```  
  
## Exemple  
  
```  
// crt_malloca_exception.c  
// This program demonstrates the use of  
// _malloca and trapping any exceptions  
// that may occur.  
  
#include <windows.h>  
#include <stdio.h>  
#include <malloc.h>  
  
int main()  
{  
    int     size;  
    int     numberRead = 0;  
    int     errcode = 0;  
    void    *p = NULL;  
    void    *pMarker = NULL;  
  
    while (numberRead == 0)  
    {  
        printf_s("Enter the number of bytes to allocate "  
                 "using _malloca: ");  
        numberRead = scanf_s("%d", &size);  
    }  
  
    // Do not use try/catch for _malloca,  
    // use __try/__except, since _malloca throws  
    // Structured Exceptions, not C++ exceptions.  
  
    __try  
    {  
        if (size > 0)  
        {  
            p =  _malloca( size );  
        }  
        else  
        {  
            printf_s("Size must be a positive number.");  
        }  
        _freea( p );  
    }  
  
    // Catch any exceptions that may occur.  
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )  
    {  
        printf_s("_malloca failed!\n");  
  
        // If the stack overflows, use this function to restore.  
        errcode = _resetstkoflw();  
        if (errcode)  
        {  
            printf("Could not reset the stack!");  
            _exit(1);  
        }  
    };  
}  
```  
  
## Entrée  
  
```  
1000  
```  
  
## Résultat de l'exemple  
  
```  
Enter the number of bytes to allocate using _malloca: 1000  
```  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md)