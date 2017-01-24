---
title: "putc, putwc | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "putwc"
  - "putc"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_puttc"
  - "putwc"
  - "putc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_puttc (fonction)"
  - "caractères, écrire"
  - "putc (fonction)"
  - "puttc (fonction)"
  - "putwc (fonction)"
  - "flux, écrire des caractères dans"
ms.assetid: a37b2e82-9d88-4565-8190-ff8d04c0ddb9
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# putc, putwc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Écrit un caractère dans un flux.  
  
## Syntaxe  
  
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
  
#### Paramètres  
 `c`  
 Caractère à écrire.  
  
 `stream`  
 Pointeur vers la structure **FICHIER**.  
  
## Valeur de retour  
 Retourne le caractère écrit.  Pour indiquer une erreur ou une condition fin de fichier, `putc` et `putchar` retournent `EOF`; `putwc` retourne **WEOF**, ainsi que `putwchar`.  Pour les quatre routines, utilisez [ferror](../../c-runtime-library/reference/ferror.md) ou [feof](../../c-runtime-library/reference/feof.md) pour vérifier une erreur ou une fin de fichier.  Si un pointeur nul est passé pour `stream`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md) .  Si l'exécution est autorisée à se poursuivre, ces fonctions retournent `EOF` ou **WEOF** et affectent à `errno` la valeur `EINVAL`.  
  
 Consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour plus d'informations sur ces éléments et autres codes d'erreur.  
  
## Notes  
 La routine `putc` écrit le caractère unique `c` dans la sortie `stream` à la position actuelle.  Tout entier peut être passé à `putc`, mais seuls les 8 bits de poids faible sont écrits.  La routine `putchar` est identique à **putc\(** `c`**, stdout \)**.  Pour chaque routine, si une erreur de lecture se produit, l'indicateur d'erreur pour le flux est défini.  `putc` et `putchar` sont semblables à `fputc` et `_fputchar`, respectivement, mais sont implémentés en tant que fonctions et comme macros \(consultez [Choix entre des fonctions et des macros](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)\).  `putwc` et `putwchar`, sont des versions à caractères larges de `putc` et `putchar` respectivement.  `putwc` et `putc` se comportent de la même façon si le flux est ouvert en mode ANSI.  `putc` ne prend pas en charge actuellement la sortie dans un flux UNICODE.  
  
 Les versions avec le suffixe **\_nolock** sont identiques mais elles ne sont pas protégées contre les interférences en provenance d'autres threads.  Pour plus d'informations, consultez **\_putc\_nolock, \_putwc\_nolock**.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_puttc`|`putc`|`putc`|**putwc**|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`putc`|\<stdio.h\>|  
|`putwc`|\<stdio.h\> ou \<wchar.h\>|  
  
 La console n'est pas prise en charge dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Les handles de flux standard associés à la console, `stdin`, `stdout` et `stderr` doivent être redirigés pour que les fonctions runtime C puissent les utiliser dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
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
  
## Sortie  
  
```  
This is the line of output  
```  
  
## Équivalent .NET Framework  
  
-   [System::IO::StreamWriter::Write](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.write.aspx)  
  
-   [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fputc, fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)