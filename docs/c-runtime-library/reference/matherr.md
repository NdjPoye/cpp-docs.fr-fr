---
title: _matherr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _matherr
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
- _matherr
- matherr
dev_langs: C++
helpviewer_keywords:
- _matherr function
- matherr function
ms.assetid: b600d66e-165a-4608-a856-8fb418d46760
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b1c7aa22479630605279b0d1364317d479bd1eac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="matherr"></a>_matherr
Gère les erreurs mathématiques.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      int _matherr(  
   struct _exception *except   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 *except*  
 Pointeur vers la structure contenant des informations sur l’erreur.  
  
## <a name="return-value"></a>Valeur de retour  
 _**matherr** retourne 0 pour indiquer une erreur, ou une valeur différente de zéro en cas de réussite. Si \_**matherr** retourne 0, un message d’erreur peut être affiché et `errno` est défini sur une valeur d’erreur appropriée. Si \_**matherr** retourne une valeur différente de zéro, aucun message d’erreur ne s’affiche et `errno` reste inchangé.  
  
 Pour plus d’informations sur ces codes de retour, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 La fonction _**matherr** traite les erreurs générées par les fonctions à virgule flottante de la bibliothèque mathématique. Ces fonctions appellent \_**matherr** si une erreur est détectée.  
  
 Pour une gestion particulière des erreurs, vous pouvez fournir une autre définition de _**matherr**. Si vous utilisez la version à liaison dynamique de la bibliothèque Runtime C (Msvcr90.dll), vous pouvez remplacer la routine \_**matherr** par défaut dans un fichier exécutable client par une version définie par l’utilisateur. Toutefois, vous ne pouvez pas remplacer la routine `_matherr` par défaut dans un client DLL de Msvcr90.dll.  
  
 Quand une erreur se produit dans une routine mathématique, _**matherr** est appelée avec un pointeur désignant une structure de type **_exception** (définie dans Math.h) comme argument. La structure **_exception** contient les éléments suivants.  
  
 **int type**  
 Type d’exception.  
  
 **char \*name**  
 Nom de la fonction où l’erreur s’est produite.  
  
 **double arg1**, **arg2**  
 Premier et second (le cas échéant) arguments de la fonction.  
  
 **double retval**  
 Valeur que la fonction doit retourner.  
  
 Le **type** spécifie le type d’erreur mathématique. Il a une des valeurs suivantes, définies dans Math.h.  
  
 `_DOMAIN`  
 Erreur de domaine d’argument.  
  
 `_SING`  
 Singularité de l’argument.  
  
 `_OVERFLOW`  
 Erreur de plage avec dépassement.  
  
 `_PLOSS`  
 Perte partielle de précision.  
  
 `_TLOSS`  
 Perte totale de précision.  
  
 `_UNDERFLOW`  
 Le résultat est trop petit pour être représenté. (Cette condition n’est pas prise en charge.)  
  
 Le membre de structure **name** est un pointeur désignant une chaîne terminée par le caractère Null qui contient le nom de la fonction ayant provoqué l’erreur. Les membres de structure **arg1** et **arg2** spécifient les valeurs qui ont provoqué l’erreur. (Si un seul argument est fourni, il est stocké dans **arg1**.)  
  
 La valeur de retour par défaut pour l’erreur donnée est **retval**. Si vous modifiez la valeur de retour, elle doit spécifier si une erreur s’est effectivement produite.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_matherr`|\<math.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
  
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
  
## <a name="output"></a>Sortie  
  
```  
Special: using absolute value: log: _DOMAIN error  
log( -2.0 ) = 6.931472e-001  
Special: using absolute value: log10: _DOMAIN error  
log10( -5.0 ) = 6.989700e-001  
Normal: log( 0.0 ) = -1.#INF00e+000  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   