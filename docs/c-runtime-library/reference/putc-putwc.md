---
title: putc, putwc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- putwc
- putc
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _puttc
- putwc
- putc
dev_langs: C++
helpviewer_keywords:
- streams, writing characters to
- characters, writing
- putwc function
- putc function
- _puttc function
- puttc function
ms.assetid: a37b2e82-9d88-4565-8190-ff8d04c0ddb9
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7a381664f64f89f2a7040b04885b1f01efe885c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="putc-putwc"></a>putc, putwc
Écrit un caractère dans un flux.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      int putc(  
   int c,  
   FILE *stream   
);  
wint_t putwc(  
   wchar_t c,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `c`  
 Caractère à écrire.  
  
 `stream`  
 Pointeur désignant la structure **FILE**.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne le caractère écrit. Pour indiquer une erreur ou une condition de fin de fichier, `putc` et `putchar` retournent `EOF` ; `putwc` et `putwchar` retournent **WEOF**. Pour les quatre routines, utilisez [ferror](../../c-runtime-library/reference/ferror.md) ou [feof](../../c-runtime-library/reference/feof.md) pour rechercher la présence d’une erreur ou d’une fin de fichier. Si un pointeur Null est transmis pour `stream`, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, ces fonctions retournent `EOF` ou **WEOF** et affectent à `errno` la valeur `EINVAL`.  
  
 Pour plus d’informations sur ces codes d’erreur et les autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 La routine `putc` écrit le caractère unique `c` dans la sortie `stream` à la position actuelle. Il est possible de passer un entier à `putc`, mais seuls les 8 bits inférieurs sont écrits. La routine `putchar` est identique à **putc(** `c`**, stdout)**. Pour chaque routine, si une erreur de lecture se produit, l’indicateur d’erreur du flux est défini. Les routines `putc` et `putchar` sont comparables, respectivement, à `fputc` et `_fputchar`, mais elles sont implémentées à la fois comme fonctions et macros (consultez [Choix entre une fonction et une macro](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)). `putwc` et `putwchar` sont, respectivement, des versions à caractères larges de `putc` et `putchar`. `putwc` et `putc` se comportent de la même façon si le flux est ouvert en mode ANSI. `putc` ne prend pas en charge la sortie vers un flux UNICODE pour l’instant.  
  
 Les versions avec suffixe **_nolock** sont identiques, à ceci près qu’elles ne sont pas protégées contre les interférences avec d’autres threads. Pour plus d’informations, consultez **_putc_nolock, _putwc_nolock**.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_puttc`|`putc`|`putc`|**putwc**|  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`putc`|\<stdio.h>|  
|`putwc`|\<stdio.h> ou \<wchar.h>|  
  
 La console n'est pas prise en charge dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] . Les handles de flux standard associés à la console (`stdin`, `stdout` et `stderr`) doivent être redirigés pour que les fonctions Runtime C puissent les utiliser dans les applications du [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]. Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_putc.c  
/* This program uses putc to write buffer  
 * to a stream. If an error occurs, the program  
 * stops before writing the entire buffer.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char *p, buffer[] = "This is the line of output\n";  
   int  ch;  
  
   ch = 0;  
   /* Make standard out the stream and write to it. */  
   stream = stdout;  
   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )  
      ch = putc( *p, stream );  
}  
```  
  
## <a name="output"></a>Sortie  
  
```  
This is the line of output  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fputc, fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)