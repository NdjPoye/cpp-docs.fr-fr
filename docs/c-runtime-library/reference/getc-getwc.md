---
title: "getc, getwc | Microsoft Docs"
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
  - "getwc"
  - "getc"
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
  - "_gettc"
  - "getwc"
  - "_gettchar"
  - "getc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_gettc (fonction)"
  - "caractères, lire"
  - "getc (fonction)"
  - "gettc (fonction)"
  - "getwc (fonction)"
  - "getwchar (fonction)"
  - "lire des caractères dans des flux"
  - "flux, lire des caractères dans"
ms.assetid: 354ef514-d0c7-404b-92f5-995f6a834bb3
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# getc, getwc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lit un caractère à partir d'un flux de données.  
  
## Syntaxe  
  
```  
int getc(   
   FILE *stream   
);  
wint_t getwc(   
   FILE *stream   
);  
```  
  
#### Paramètres  
 `stream`  
 Flux d'entrée.  
  
## Valeur de retour  
 Retourne le caractère lu.  Pour indiquer une erreur de lecture ou une condition fin de fichier, `getc` retourne `EOF`, et `getwc` retourne `WEOF`.  Pour `getc`, utilisez `ferror` ou `feof` afin de repérer d'éventuelles erreurs ou la fin du fichier.  Si `stream` est `NULL`, `getc` et `getwc` fait appel à un gestionnaire de paramètres invalides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions retournent `EOF` \(or `WEOF` for`getwc`\) et définissent `errno` avec la valeur `EINVAL`.  
  
 Consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour plus d'informations sur ces éléments et autres codes d'erreur.  
  
## Notes  
 Chaque routine lit un caractère à partir d'un fichier à la position actuelle et incrémente le pointeur de fichier associé \(si défini\) pour indiquer le caractère suivant.  Le fichier est associé à cet élément `stream`.  
  
 Ces fonctions verrouillent le thread appelant et sont donc thread\-safe.  Pour une version non verrouillante, consultez [\_getc\_nolock, \_getwc\_nolock](../../c-runtime-library/reference/getc-nolock-getwc-nolock.md).  
  
 Les remarques concernant les routines sont indiquées dans la suite.  
  
|Routine|Remarques|  
|-------------|---------------|  
|`getc`|Identique à `fgetc`, mais implémenté en tant qu'une fonction et sa macro.|  
|`getwc`|Version à caractères larges de `getc`.  Lit un caractère multioctet ou un caractère large selon la manière dont `stream` est ouvert dans le mode texte ou binaire.|  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_gettc`|`getc`|`getc`|`getwc`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`getc`|\<stdio.h\>|  
|`getwc`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_getc.c  
// Use getc to read a line from a file.  
  
#include <stdio.h>  
  
int main()  
{  
    char buffer[81];  
    int i, ch;  
    FILE* fp;  
  
    // Read a single line from the file "crt_getc.txt".   
  
    fopen_s(&fp, "crt_getc.txt", "r");  
    if (!fp)  
    {  
       printf("Failed to open file crt_getc.txt.\n");  
       exit(1);  
    }  
  
    for (i = 0; (i < 80) && ((ch = getc(fp)) != EOF)  
                         && (ch != '\n'); i++)  
    {  
        buffer[i] = (char) ch;  
    }  
  
    // Terminate string with a null character   
    buffer[i] = '\0';  
    printf( "Input was: %s\n", buffer);  
  
    fclose(fp);  
}  
```  
  
## Entrée: crt\_getc.txt  
  
```  
Line one.  
Line two.  
```  
  
### Sortie  
  
```  
Input was: Line one.  
```  
  
## Équivalent .NET Framework  
  
-   [System::IO::StreamReader::Read](https://msdn.microsoft.com/en-us/library/system.io.streamreader.read.aspx).  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fgetc, fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md)   
 [\_getch, \_getwch](../../c-runtime-library/reference/getch-getwch.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)   
 [ungetc, ungetwc](../../c-runtime-library/reference/ungetc-ungetwc.md)