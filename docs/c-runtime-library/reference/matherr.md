---
title: "_matherr | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_matherr"
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
  - "_matherr"
  - "matherr"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_matherr (fonction)"
  - "matherr (fonction)"
ms.assetid: b600d66e-165a-4608-a856-8fb418d46760
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _matherr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Handles math errors.  
  
## Syntaxe  
  
```  
  
      int _matherr(  
   struct _exception *except   
);  
```  
  
#### Paramètres  
 *\_\_except*  
 Pointeur vers une structure contenant des informations sur les messages.  
  
## Valeur de retour  
 \_**matherr** retourne 0 pour indiquer une erreur ou une valeur différente de zéro pour indiquer le succès.  Si le \_**matherr** retourne 0, un message d'erreur peut s'afficher et `errno` a une valeur d'erreur appropriée.  Si le \_**matherr** retourne une valeur différente de zéro, aucun message d'erreur n'est affiché et `errno` reste inchangé.  
  
 Pour plus d'informations sur ces codes de retour et autres, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction**matherr** gère les erreurs généres par les fonctions à virgule flottante de la bibliothèque mathématique.  Ces fonctions appellent **matherr**lorsqu'une erreur est détectée.  
  
 Pour la gestion des erreurs particulières, vous pouvez fournir une autre définition de  **matherr**.  Si vous utilisez la versiondu lien dynamique ou de la bibliothèque Runtime C \(Msvcr90.dll\), vous pouvez remplacer la routine par défaut de**matherr** \_dans un fichier exécutable client par une version définie par l'utilisateur.  Toutefois, vous ne pouvez pas remplacer la routine par défaut de`_matherr` dans un client de DLL Msvcr90.dll.  
  
 Lorsqu'une erreur se produit dans une routine mathématiques, \_**matherr** est appelé avec un pointeur vers une structure de type  **\_exception** \(définie dans Math.h\) comme argument.  La structure **\_exception** contient les éléments suivants :  
  
 Type : **int**  
 Type d'exception  
  
 **char \*name**  
 Nom de la fonction où l'erreur s'est produite.  
  
 **double arg1**, **arg2**  
 Le Premier argument et le second\(le cas échéant\)à la fonction.  
  
 **double retval**  
 Valeur retournée par la fonction.  
  
 **type** Spécifie le type d'erreur mathématiques.  Elle est l'une des valeurs suivantes, défini dans Math.h.  
  
 `_DOMAIN`  
 Erreur de domaine argument.  
  
 `_SING`  
 Singularité argument.  
  
 `_OVERFLOW`  
 Erreur sur le champ de débordement.  
  
 `_PLOSS`  
 Perte partielle d'importance.  
  
 `_TLOSS`  
 Perte totale de signification.  
  
 `_UNDERFLOW`  
 Le résultat est trop petit pour être représenté. Cette propriété n'est pas prise en charge actuellement.  
  
 Le membre de structure **Nom** est un pointeur vers une chaîne terminée par le caractère NULL qui contient le nom de la fonction qui a provoqué l'erreur.  Les membres de la structure **arg1** et **arg2** spécifient les valeurs qui ont provoqué l'erreur. \(Si un seul argument est fourni, il est stocké dans **arg1**.\)  
  
 La valeur renvoyée par défaut de l'erreur est **retval**.  Si vous modifiez la valeur de retour, elle doit spécifier si une erreur a eu lieu.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_matherr`|\<math.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_matherr.c  
/* illustrates writing an error routine for math   
 * functions. The error function must be:  
 *      _matherr  
 */  
  
#include <math.h>  
#include <string.h>  
#include <stdio.h>  
  
int main()  
{  
    /* Do several math operations that cause errors. The _matherr  
     * routine handles _DOMAIN errors, but lets the system handle  
     * other errors normally.  
     */  
    printf( "log( -2.0 ) = %e\n", log( -2.0 ) );  
    printf( "log10( -5.0 ) = %e\n", log10( -5.0 ) );  
    printf( "log( 0.0 ) = %e\n", log( 0.0 ) );  
}  
  
/* Handle several math errors caused by passing a negative argument  
 * to log or log10 (_DOMAIN errors). When this happens, _matherr  
 * returns the natural or base-10 logarithm of the absolute value  
 * of the argument and suppresses the usual error message.  
 */  
int _matherr( struct _exception *except )  
{  
    /* Handle _DOMAIN errors for log or log10. */  
    if( except->type == _DOMAIN )  
    {  
        if( strcmp( except->name, "log" ) == 0 )  
        {  
            except->retval = log( -(except->arg1) );  
            printf( "Special: using absolute value: %s: _DOMAIN "  
                     "error\n", except->name );  
            return 1;  
        }  
        else if( strcmp( except->name, "log10" ) == 0 )  
        {  
            except->retval = log10( -(except->arg1) );  
            printf( "Special: using absolute value: %s: _DOMAIN "  
                     "error\n", except->name );  
            return 1;  
        }  
    }  
    printf( "Normal: " );  
    return 0;    /* Else use the default actions */  
}  
```  
  
## Sortie  
  
```  
Special: using absolute value: log: _DOMAIN error  
log( -2.0 ) = 6.931472e-001  
Special: using absolute value: log10: _DOMAIN error  
log10( -5.0 ) = 6.989700e-001  
Normal: log( 0.0 ) = -1.#INF00e+000  
```  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [Long double](../../misc/long-double.md)