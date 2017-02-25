---
title: "putchar, putwchar | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "putchar"
  - "putwchar"
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
  - "putchar"
  - "putwchar"
  - "_puttchar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_puttchar (fonction)"
  - "caractères, écrire"
  - "putchar (fonction)"
  - "putwchar (fonction)"
  - "sortie standard, écrire dans"
ms.assetid: 93657c7f-cca1-4032-8e3a-cd6ab6193748
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# putchar, putwchar
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Écrit un caractère à **stdout**.  
  
## Syntaxe  
  
```  
  
      int putchar(  
   int c   
);  
wint_t putwchar(  
   wchar_t c   
);  
```  
  
#### Paramètres  
 `c`  
 Caractère à écrire.  
  
## Valeur de retour  
 Retourne le caractère écrit.  Pour indiquer une erreur ou une condition fin de fichier, `putc` et `putchar` retournent `EOF`; `putwc` et retourne **WEOF**de `putwchar`.  Pour les quatre routines, utilisez [ferror](../../c-runtime-library/reference/ferror.md) ou [feof](../../c-runtime-library/reference/feof.md) pour vérifier une erreur ou une fin de fichier.  Si `stream`, [Validation de paramètre](../../c-runtime-library/parameter-validation.md), ou est un pointeur null, ces fonctions génèrent une exception paramètre invalide, comme décrit dans .  Si l'exécution est autorisée à se poursuivre, ces fonctions renvoient `EOF` ou **WEOF** et définissent `errno` avec la valeur `EINVAL`.  
  
 Consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour plus d'informations sur ces éléments et autres codes d'erreur.  
  
## Notes  
 La routine `putc` écrit le caractère unique `c` dans le `stream` de sortie à la position actuelle.  Tout entier peut être passé à `putc`, mais seuls les 8 bits de poids faible sont écrits.  La routine `putchar` est identique à **putc\(** `c`**, stdout \)**.  Pour chaque routine, si une erreur de lecture se produit, l'indicateur d'erreur pour le flux est défini.  `putc` et `putchar` sont semblables à `fputc` et `_fputchar`, respectivement, mais sont implémentés en tant que fonctions et comme macros \(consultez [Choix entre des fonctions et des macros](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)\).  `putwc` et `putwchar`, sont des versions à caractères larges de `putc` et `putchar` respectivement.  
  
 Les versions avec le suffixe **\_nolock** sont identiques mais elles ne sont pas protégées contre les interférences en provenance d'autres threads.  Elles peuvent être plus rapides car elles n'entraînent pas la charge du verrouillage des autres threads.  Utilisez ces fonctions uniquement dans les contextes thread\-safe, tels que les applications à un seul thread ou lorsque la portée appelante gère déjà l'isolation des threads.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_puttchar`|`putchar`|`putchar`|**putwchar**|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`putchar`|\<stdio.h\>|  
|`putwchar`|\<stdio.h\> ou \<wchar.h\>|  
  
 La console n'est pas prise en charge dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Les handles de flux standard associés à la console, `stdin`, `stdout` et `stderr` doivent être redirigés pour que les fonctions runtime C puissent les utiliser dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_putchar.c  
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
  
   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )  
      ch = putchar( *p );  
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