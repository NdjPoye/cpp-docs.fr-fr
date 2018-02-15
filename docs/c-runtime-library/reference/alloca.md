---
title: _alloca | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _alloca
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
- _alloca
- alloca
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, stack
- alloca function
- _alloca function
ms.assetid: 74488eb1-b71f-4515-88e1-cdd03b6f8225
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 104c3df4e6f69d31c5090a87c8029351accd1e1e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="alloca"></a>_alloca
Alloue de la mémoire sur la pile. Cette fonction est déconseillée, car une version plus sécurisée est disponible ; consultez [_malloca](../../c-runtime-library/reference/malloca.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void *_alloca(   
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `size`  
 Octets à allouer à partir de la pile.  
  
## <a name="return-value"></a>Valeur de retour  
 La routine `_alloca` retourne un pointeur `void` désignant l’espace alloué, qui est obligatoirement correctement aligné pour le stockage de tout type d’objet. Si `size` a la valeur 0, `_alloca` alloue un élément de longueur nulle et retourne un pointeur valide vers cet élément.  
  
 Une exception de dépassement de capacité de pile est générée si l’espace ne peut pas être alloué. L’exception de dépassement de capacité de pile n’est pas une exception C++ ; il s’agit d’une exception structurée. Au lieu d’utiliser la gestion des exceptions C++, vous devez utiliser la [gestion des exceptions structurée](../../cpp/structured-exception-handling-c-cpp.md) (SEH).  
  
## <a name="remarks"></a>Notes  
 `_alloca` alloue `size` octets à partir de la pile du programme. L’espace alloué est automatiquement libérée lorsque la fonction d’appel s’arrête (pas lors de l’allocation n’est hors de portée). Par conséquent, ne passez pas de la valeur du pointeur retournée par `_alloca` en tant qu’argument à [libre](../../c-runtime-library/reference/free.md).  
  
 Des restrictions s’appliquent à l’appel explicite de `_alloca` dans un gestionnaire d’exceptions (EH). Les routines EH qui s’exécutent sur des processeurs de classe x86 opèrent dans le cadre de leur propre mémoire : elles effectuent leurs tâches dans un espace mémoire qui n’est pas basé sur l’emplacement actuel du pointeur de pile de la fonction englobante. Les implémentations les plus courantes incluent les expressions de gestion des exceptions structurées Windows NT (SEH) et les expressions de clause catch C++. Ainsi, appeler explicitement `_alloca` dans l’un des scénarios suivants entraîne l’échec du programme pendant le retour à la routine EH appelante :  
  
-   Expression de filtre d’exception SEH Windows NT : `__except` (`_alloca ()`)  
  
-   Gestionnaire d’exceptions finales SEH Windows NT : `__finally` {`_alloca ()`}  
  
-   Expression de clause catch EH C++  
  
 Toutefois, `_alloca` peut être appelée directement à partir d’une routine EH ou à partir d’un rappel fourni par l’application appelé dans le cadre d’un des scénarios EH indiqués plus haut.  
  
> [!IMPORTANT]
>  Dans Windows XP, si `_alloca` est appelée à l’intérieur d’un bloc try/catch, vous devez appeler [_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md) dans le bloc catch.  
  
 Outre les restrictions ci-dessus, lorsque vous utilisez la[/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md) option, `_alloca` ne peut pas être utilisé dans `__except` blocs. Pour plus d'informations, consultez [/clr Restrictions](../../build/reference/clr-restrictions.md).  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_alloca`|\<malloc.h>|  
  
## <a name="example"></a>Exemple  
  
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
  
```Output  
Allocated 1000 bytes of stack at 0x0012FB50  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md)   
 [_malloca](../../c-runtime-library/reference/malloca.md)