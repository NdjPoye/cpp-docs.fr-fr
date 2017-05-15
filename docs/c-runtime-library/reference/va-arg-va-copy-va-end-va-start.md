---
title: va_arg, va_copy, va_end, va_start | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- va_arg
- va_end
- va_copy
- va_start
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
- va_arg
- va_start
- va_list
- va_alist
- va_dcl
- va_copy
- va_end
dev_langs:
- C++
helpviewer_keywords:
- variable argument lists, accessing
- va_start macro
- va_arg macro
- va_end macro
- arguments [C++], argument lists
- va_list macro
- va_dcl macro
- va_alist macro
- va_copy macro
ms.assetid: a700dbbd-bfe5-4077-87b6-3a07af74a907
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 1b8ddbc48b00a037ae20632f4cd396e8e0ff2722
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="vaarg-vacopy-vaend-vastart"></a>va_arg, va_copy, va_end, va_start
Accède à des listes d’arguments variables.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
type va_arg(  
   va_list arg_ptr,  
   type   
);
void va_copy(  
   va_list dest,  
   va_list src  
); // (ISO C99 and later)  
void va_end(  
   va_list arg_ptr   
);  
void va_start(  
   va_list arg_ptr,  
   prev_param   
); // (ANSI C89 and later)  
void va_start(  
   arg_ptr   
);  // (deprecated Pre-ANSI C89 standardization version)  
```  
  
#### <a name="parameters"></a>Paramètres  
 `type`  
 Type d’argument à récupérer.  
  
 `arg_ptr`  
 Pointeur désignant la liste d’arguments.  
  
 `dest`  
 Pointeur désignant la liste d’arguments à initialiser à partir de `src`.  
  
 `src`  
 Pointeur désignant la liste d’arguments initialisée à copier dans `dest`.  
  
 `prev_param`  
 Paramètre qui précède le premier argument facultatif.  
  
## <a name="return-value"></a>Valeur de retour  
 `va_arg` retourne l’argument actif. `va_copy`, `va_start` et `va_end` ne retournent pas de valeurs.  
  
## <a name="remarks"></a>Notes  
 Les macros `va_arg`, `va_copy`, `va_end` et `va_start` offrent un moyen portable d’accéder aux arguments pour une fonction qui accepte un nombre variable d’arguments. Il existe deux versions de ces macros : les macros définies dans STDARG.H, qui sont conformes à la norme ISO C99, et les macros définies dans VARARGS.H qui, bien que dépréciées, sont conservées pour des besoins de compatibilité descendante avec le code qui a été écrit avant la norme ANSI C89.  
  
 Ces macros considèrent que la fonction accepte un nombre fixe d’arguments obligatoires, suivi d’un nombre variable d’arguments facultatifs. Les arguments obligatoires sont déclarés à la fonction en tant que paramètres ordinaires et sont accessibles via les noms des paramètres. Les arguments facultatifs sont accessibles via les macros contenues dans STDARG.H (ou dans VARARGS.H pour le code qui a été écrit avant la norme ANSI C89). Ils définissent le pointeur désignant le premier argument facultatif de la liste d’arguments, récupère les arguments de la liste et réinitialise le pointeur dès que le traitement de l’argument est terminé.  
  
 Les macros standard C, définies dans STDARG.H, sont utilisées comme suit :  
  
-   `va_start` définit `arg_ptr` comme étant le premier argument facultatif de la liste d’arguments à être passé à la fonction. L’argument `arg_ptr` doit être de type `va_list`. L’argument `prev_param` est le nom du paramètre obligatoire qui précède immédiatement le premier argument facultatif dans la liste d’arguments. Si `prev_param` est déclarée avec la classe de stockage register, le comportement de la macro est indéfini. `va_start` doit être utilisée avant la première utilisation de `va_arg`.  
  
-   `va_arg` récupère une valeur de `type` à partir de l’emplacement indiqué par `arg_ptr` et incrémente `arg_ptr` pour pointer vers le prochain argument de la liste en utilisant la taille de `type` pour déterminer le point de départ du prochain argument. `va_arg` peut être utilisé autant de fois que nécessaire dans la fonction pour récupérer les arguments de la liste.  
  
-   `va_copy` crée une copie d’une liste d’arguments dans son état actuel. Le paramètre `src` doit déjà être initialisé avec `va_start` ; il peut avoir été mis à jour avec des appels `va_arg`, mais il ne doit pas avoir été réinitialisé avec `va_end`. Le prochain argument à être récupéré par `va_arg` à partir de `dest` est le même que celui qui est récupéré à partir de `src`.  
  
-   Une fois que tous les arguments ont été récupérés, `va_end` réinitialise le pointeur en lui affectant la valeur **NULL**. `va_end` doit être appelé pour chaque liste d’arguments qui est initialisée avec `va_start` ou `va_copy` avant le retour de la fonction.  
  
> [!NOTE]
>  Les macros contenues dans VARARGS.H sont obsolètes et sont conservées uniquement pour assurer une compatibilité descendante avec le code qui a été écrit avant la norme ANSI C89. Dans tous les autres cas, utilisez les macros contenues dans STDARGS.H.  
  
 Quand ils sont compilés à l’aide de [/clr (compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md), les programmes qui utilisent ces macros peuvent générer des résultats inattendus en raison des différences entre les systèmes de type natif et les systèmes de type CLR (Common Language Runtime). Prenons l’exemple de ce programme :  
  
```  
#include <stdio.h>  
#include <stdarg.h>  
  
void testit (int i, ...)  
{  
    va_list argptr;  
    va_start(argptr, i);  
  
    if (i == 0)  
    {  
        int n = va_arg(argptr, int);  
        printf("%d\n", n);  
    }  
    else  
    {  
        char *s = va_arg(argptr, char*);  
        printf("%s\n", s);  
    }  

    va_end(argptr);  
}  
  
int main()  
{  
    testit(0, 0xFFFFFFFF); // 1st problem: 0xffffffff is not an int  
    testit(1, NULL);       // 2nd problem: NULL is not a char*  
}  
```  
  
 Notez que `testit` s’attend à ce que son deuxième paramètre soit un `int` ou un `char*`. Les arguments transmis sont 0xffffffff (un `unsigned int`, et non un `int`) et `NULL` (en réalité un `int`, et non un `char*`). Quand le programme est compilé pour du code natif, il génère cette sortie :  
  
```Output  
-1  
  
(null)  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<stdio.h> et \<stdarg.h>  
  
 **En-tête obsolète :** \<varargs.h>  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_va.c  
/* Compile with: cl /W3 /Tc crt_va.c  
 * The program below illustrates passing a variable  
 * number of arguments using the following macros:  
 *      va_start            va_arg              va_copy  
 *      va_end              va_list  
 */  
  
#include <stdio.h>  
#include <stdarg.h>  
#include <math.h>  
  
double deviation(int first, ...);  
  
int main( void )  
{  
    /* Call with 3 integers (-1 is used as terminator). */  
    printf("Deviation is: %f\n", deviation(2, 3, 4, -1 ));  
  
    /* Call with 4 integers. */  
    printf("Deviation is: %f\n", deviation(5, 7, 9, 11, -1));  
  
    /* Call with just -1 terminator. */  
    printf("Deviation is: %f\n", deviation(-1));  
}  
  
/* Returns the standard deviation of a variable list of integers. */  
double deviation(int first, ...)  
{  
    int count = 0, i = first;  
    double mean = 0.0, sum = 0.0;  
    va_list marker;  
    va_list copy;  
  
    va_start(marker, first);     /* Initialize variable arguments. */  
    va_copy(copy, marker);       /* Copy list for the second pass */  
    while (i != -1)  
    {  
        sum += i;  
        count++;  
        i = va_arg(marker, int);  
    }  
    va_end(marker);              /* Reset variable argument list. */  
    mean = sum ? (sum / count) : 0.0;  
  
    i = first;                  /* reset to calculate deviation */  
    sum = 0.0;  
    while (i != -1)  
    {  
        sum += (i - mean)*(i - mean);  
        i = va_arg(copy, int);  
    }  
    va_end(copy);               /* Reset copy of argument list. */  
    return count ? sqrt(sum / count) : 0.0;  
}  
  
```  
  
## <a name="output"></a>Sortie  
  
```Output  
Deviation is: 0.816497  
Deviation is: 2.236068  
Deviation is: 0.000000  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Accès à un argument](../../c-runtime-library/argument-access.md)   
 [vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l](../../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)
