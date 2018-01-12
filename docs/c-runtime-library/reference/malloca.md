---
title: _malloca | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _malloca
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- malloca
- _malloca
dev_langs: C++
helpviewer_keywords:
- memory allocation, stack
- malloca function
- _malloca function
ms.assetid: 293992df-cfca-4bc9-b313-0a733a6bb936
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fcdeab9e61eda17164be06498e9ce42695faf8ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="malloca"></a>_malloca
Alloue de la mémoire sur la pile. Il s’agit d’une version de [_alloca](../../c-runtime-library/reference/alloca.md) assortie des améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void *_malloca(   
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `size`  
 Octets à allouer à partir de la pile.  
  
## <a name="return-value"></a>Valeur de retour  
 La routine `_malloca` retourne un pointeur `void` désignant l’espace alloué, qui est obligatoirement correctement aligné pour le stockage de tout type d’objet. Si `size` a la valeur 0, `_malloca` alloue un élément de longueur nulle et retourne un pointeur valide vers cet élément.  
  
 Une exception de dépassement de capacité de pile est générée si l’espace ne peut pas être alloué. L’exception de dépassement de capacité de pile n’est pas une exception C++ ; il s’agit d’une exception structurée. Au lieu d’utiliser la gestion des exceptions C++, vous devez utiliser la [gestion des exceptions structurée](../../cpp/structured-exception-handling-c-cpp.md) (SEH).  
  
## <a name="remarks"></a>Notes  
 `_malloca` alloue `size` octets à partir de la pile du programme ou du tas si la demande dépasse une certaine taille en octets fournie par `_ALLOCA_S_THRESHOLD`. La différence entre `_malloca` et `_alloca` est que `_alloca` alloue toujours sur la pile, indépendamment de la taille. Contrairement à `_alloca`, qui n’exige ou n’autorise pas un appel à `free` pour libérer la mémoire ainsi allouée, `_malloca` nécessite l’utilisation de [_freea](../../c-runtime-library/reference/freea.md) pour libérer de la mémoire. En mode débogage, `_malloca` alloue toujours de la mémoire à partir du tas.  
  
 Des restrictions s’appliquent à l’appel explicite de `_malloca` dans un gestionnaire d’exceptions (EH). Les routines EH qui s’exécutent sur des processeurs de classe x86 opèrent dans le cadre de leur propre mémoire : elles effectuent leurs tâches dans un espace mémoire qui n’est pas basé sur l’emplacement actuel du pointeur de pile de la fonction englobante. Les implémentations les plus courantes incluent les expressions de gestion des exceptions structurées Windows NT (SEH) et les expressions de clause catch C++. Ainsi, appeler explicitement `_malloca` dans l’un des scénarios suivants entraîne l’échec du programme pendant le retour à la routine EH appelante :  
  
-   Expression de filtre d’exception SEH Windows NT : `__except` (`_malloca ()`)  
  
-   Gestionnaire d’exceptions finales SEH Windows NT : `__finally` {`_malloca ()`}  
  
-   Expression de clause catch EH C++  
  
 Toutefois, `_malloca` peut être appelée directement à partir d’une routine EH ou à partir d’un rappel fourni par l’application appelé dans le cadre d’un des scénarios EH indiqués plus haut.  
  
> [!IMPORTANT]
>  Dans Windows XP, si `_malloca` est appelée à l’intérieur d’un bloc try/catch, vous devez appeler [_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md) dans le bloc catch.  
  
 Outre les restrictions ci-dessus, quand vous utilisez l’option [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md), `_malloca` ne peut pas être utilisée dans des blocs `__except`. Pour plus d’informations, consultez [Restrictions de /clr](../../build/reference/clr-restrictions.md).  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_malloca`|\<malloc.h>|  
  
## <a name="example"></a>Exemple  
  
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
  
## <a name="example"></a>Exemple  
  
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
  
## <a name="input"></a>Entrée  
  
```  
1000  
```  
  
## <a name="sample-output"></a>Résultat de l'exemple  
  
```  
Enter the number of bytes to allocate using _malloca: 1000  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md)