---
title: "va_arg, va_copy, va_end, va_start | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "va_arg"
  - "va_end"
  - "va_copy"
  - "va_start"
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
  - "va_arg"
  - "va_start"
  - "va_list"
  - "va_alist"
  - "va_dcl"
  - "va_copy"
  - "va_end"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "l’accès à des listes d’arguments variables"
  - "va_start (macro)"
  - "va_arg (macro)"
  - "va_end (macro)"
  - "arguments (C++), des listes d’arguments"
  - "va_list (macro)"
  - "va_dcl (macro)"
  - "va_alist (macro)"
  - "va_copy (macro)"
ms.assetid: a700dbbd-bfe5-4077-87b6-3a07af74a907
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# va_arg, va_copy, va_end, va_start
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Listes d’arguments variables accède.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      type va_arg(  
   va_list arg_ptr,  
   type   
);void va_copy(  
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
);  // (Pre-ANSI C89 standardization version)  
```  
  
#### <a name="parameters"></a>Paramètres  
 `type`  
 Type d’argument doit être récupéré.  
  
 `arg_ptr`  
 Pointeur vers la liste d’arguments.  
  
 `dest`  
 Pointeur vers la liste d’arguments à initialiser à partir de `src`  
  
 `src`  
 Pointeur vers la liste d’arguments à copier vers initialisée `dest`.  
  
 `prev_param`  
 Paramètre qui précède le premier argument facultatif.  
  
## <a name="return-value"></a>Valeur de retour  
 `va_arg` Retourne l’argument actuel. `va_copy`, `va_start` et `va_end` ne retournent pas de valeurs.  
  
## <a name="remarks"></a>Remarques  
 Le `va_arg`, `va_copy`, `va_end`, et `va_start` macros fournissent un moyen pratique d’accéder aux arguments d’une fonction lorsque la fonction prend un nombre variable d’arguments. Il existe deux versions des macros : les macros définies dans STDARG. H sont conformes à l’ISO C99 standard ; les macros définies dans VARARGS. H sont déconseillées, mais sont conservés pour la compatibilité descendante avec le code qui a été écrit avant le C89 ANSI standard.  
  
 Ces macros supposent que la fonction accepte un nombre fixe d’arguments, suivi d’un nombre variable d’arguments facultatifs. Les arguments requis sont déclarées en tant que paramètres ordinaires à la fonction et sont accessibles via les noms de paramètre. Les arguments facultatifs sont accessibles via les macros dans STDARG. H (ou VARARGS. H pour le code qui a été écrit avant la norme ANSI C89), qui définit un pointeur vers le premier argument facultatif dans la liste d’arguments, récupère les arguments de la liste et réinitialise le pointeur lorsque le traitement de l’argument est terminé.  
  
 Les macros standards de C, définies dans STDARG. H, sont utilisées comme suit :  
  
-   `va_start` définit `arg_ptr` pour le premier argument facultatif dans la liste d’arguments est passé à la fonction. L’argument `arg_ptr` doit avoir le `va_list` type. L’argument `prev_param` est le nom du paramètre requis qui précède immédiatement le premier argument facultatif dans la liste d’arguments. Si `prev_param` est déclarée avec la classe de stockage register, comportement de la macro n’est pas défini. `va_start` doit être utilisée avant `va_arg` est utilisé pour la première fois.  
  
-   `va_arg` Récupère une valeur de `type` à partir de l’emplacement qui est fourni par `arg_ptr`, et incrémente `arg_ptr` pour pointer vers l’argument suivant dans la liste à l’aide de la taille de `type` pour déterminer où commence l’argument suivant. `va_arg` peut être utilisée n’importe quel nombre de fois dans la fonction pour récupérer les arguments de la liste.  
  
-   `va_copy` effectue une copie d’une liste d’arguments dans son état actuel. Le `src` paramètre doit déjà être initialisé avec `va_start`; il peut avoir été mis à jour avec `va_arg` appelle, mais ne devez pas ont été réinitialisés avec `va_end`. L’argument suivant est extrait par `va_arg` de `dest` est identique à l’argument suivant est extrait de `src`.  
  
-   Une fois que tous les arguments ont été récupérées, `va_end` réinitialise le pointeur **NULL**. `va_end` doit être appelée pour chaque liste d’arguments qui est initialisée avec `va_start` ou `va_copy` avant le retour de la fonction.  
  
> [!NOTE]
>  Les macros de VARARGS. H sont obsolètes et est conservé uniquement pour assurer la compatibilité avec le code qui a été écrit avant la norme ANSI C89. Dans tous les autres cas, utilisez les macros dans STDARGS. H.  
  
 Lorsqu’elles sont compilées à l’aide de [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md), les programmes qui utilisent ces macros peuvent générer des résultats inattendus en raison de différences entre les systèmes de type natif et le common language runtime (CLR). Tenez compte de ce programme :  
  
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
}  
  
int main()  
{  
    testit(0, 0xFFFFFFFF); // 1st problem: 0xffffffff is not an int  
    testit(1, NULL);       // 2nd problem: NULL is not a char*  
}  
```  
  
 Notez que `testit` attend que son deuxième paramètre soit une `int` ou un `char*`. Les arguments passés sont 0xffffffff (une `unsigned int`, et non un `int`) et `NULL` (en fait une `int`, et non un `char*`). Lorsque le programme est compilé pour le code natif, il génère cette sortie :  
  
```Output  
-1  
  
(null)  
```  
  
 Toutefois, lorsque le programme est compilé à l’aide de **/clr : pure**, les incompatibilités de type qu’elle génère une exception. La solution consiste à utiliser des conversions explicites :  
  
```  
int main()  
{  
   testit( 0, (int)0xFFFFFFFF ); // cast unsigned to int  
   testit( 1, (char*)NULL );     // cast int to char*  
}  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \< stdio.h > et \< stdarg.h >  
  
 **En-tête obsolète :** \< varargs.h >  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions de le [les bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
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
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 [System::ParamArrayAttribute (classe)](https://msdn.microsoft.com/en-us/library/system.paramarrayattribute.aspx)  
  
## <a name="see-also"></a>Voir aussi  
 [Accès à un argument](../../c-runtime-library/argument-access.md)   
 [vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l](../../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)