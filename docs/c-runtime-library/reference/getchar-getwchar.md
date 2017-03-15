---
title: "getchar, getwchar | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "getchar"
  - "getwchar"
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
  - "getwchar"
  - "GetChar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_gettchar (fonction)"
  - "caractères, lire"
  - "gettchar (fonction)"
  - "getwchar (fonction)"
  - "entrée standard, lire dans"
ms.assetid: 19fda588-3e33-415c-bb60-dd73c028086a
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# getchar, getwchar
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lit un caractère depuis une entrée standard.  
  
## Syntaxe  
  
```  
int getchar();  
wint_t getwchar();  
```  
  
## Valeur de retour  
 Retourne le caractère lu.  Pour indiquer une erreur de lecture ou une condition fin de fichier, `getchar` `returns EOF`, et `getwchar` retourne `WEOF`.  Pour `getchar`, utilisez `ferror` ou `feof` afin de repérer d'éventuelles erreurs ou la fin du fichier.  
  
## Notes  
 Chaque routine lit un caractère unique de `stdin` et incrémente le pointeur de fichier associé pour indiquer le caractère suivant.  `getchar` est identique à [\_fgetchar](../../c-runtime-library/reference/fgetc-fgetwc.md), mais il est implémenté en tant que fonction et en tant que macro.  
  
 Ces fonctions verrouillent le thread appelant et sont donc thread\-safe.  Pour une version non verrouillante, consultez [\_getchar\_nolock, \_getwchar\_nolock](../../c-runtime-library/reference/getchar-nolock-getwchar-nolock.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_gettchar`|`getchar`|`getchar`|`getwchar`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`getchar`|\<stdio.h\>|  
|`getwchar`|\<stdio.h\> ou \<wchar.h\>|  
  
 La console n'est pas prise en charge dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Les handles de flux standard associés à la console, `stdin`, `stdout` et `stderr` doivent être redirigés pour que les fonctions runtime C puissent les utiliser dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_getchar.c  
// Use getchar to read a line from stdin.  
  
#include <stdio.h>  
  
int main()  
{  
    char buffer[81];  
    int i, ch;  
  
    for (i = 0; (i < 80) && ((ch = getchar()) != EOF)  
                         && (ch != '\n'); i++)  
    {  
        buffer[i] = (char) ch;  
    }  
  
    // Terminate string with a null character   
    buffer[i] = '\0';  
    printf( "Input was: %s\n", buffer);  
}  
```  
  
  **`L'entrée de ce texte`était : Ce texte**   
## Équivalent .NET Framework  
  
-   [System::IO::StreamReader::Read](https://msdn.microsoft.com/en-us/library/system.io.streamreader.read.aspx).  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)   
 [fgetc, fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md)   
 [\_getch, \_getwch](../../c-runtime-library/reference/getch-getwch.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)   
 [ungetc, ungetwc](../../c-runtime-library/reference/ungetc-ungetwc.md)