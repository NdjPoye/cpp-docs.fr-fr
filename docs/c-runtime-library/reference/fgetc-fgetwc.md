---
title: "fgetc, fgetwc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fgetwc"
  - "fgetc"
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
  - "_fgettc"
  - "fgetwc"
  - "fgetc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fgettc (fonction)"
  - "caractères, lire"
  - "fgetc (fonction)"
  - "fgettc (fonction)"
  - "fgetwc (fonction)"
  - "lire des caractères dans des flux"
  - "flux, lire des caractères dans"
ms.assetid: 13348b7b-dc86-421c-9d6c-611ca79c8338
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# fgetc, fgetwc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lit un caractère à partir d'un flux de données.  
  
## Syntaxe  
  
```  
int fgetc(   
   FILE *stream   
);  
wint_t fgetwc(   
   FILE *stream   
);  
```  
  
#### Paramètres  
 `stream`  
 Pointeur vers la structure `FILE`.  
  
## Valeur de retour  
 `fgetc` retourne le caractère lu comme un `int` ou retourne`EOF` pour indiquer une erreur ou une fin de fichier.  `fgetwc`[](../../c-runtime-library/standard-types.md "Standard Types") retourne, en tant que `wint_tWEOF, le caractère élargi correspondant au caractère lu ou retourne`  pour indiquer une erreur ou fin de fichier.  Pour les deux fonctions, utilisez `feof` ou `ferror` pour différencier une erreur et une fin de fichier.  Si une erreur de lecture se produit, l'indicateur d'erreur du flux de données est défini.  Si `stream` est `NULL`, `fgetc` et `fgetwc` fait appel à un gestionnaire de paramètres invalides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` à la valeur `EINVAL` et retournent `EOF`.  
  
## Notes  
 Chacune de ces fonctions lit qu'un seul caractère de la position actuelle du fichier a associées à `stream`.  Cette fonction incrémente ensuite le pointeur de fichier associé \(si défini\) pour pointer au caractère suivant.  Si le flux est à la fin du fichier, l'indicateur de fin du flux est défini.  
  
 `fgetc` est équivalent à `getc`, mais implémenté uniquement comme une fonction plutôt que comme une fonction et une macro.  
  
 `fgetwc` lit la version à caractère large `fgetc`, cela lit `c` comme une chaîne de caractères multi\-octets ou une chaîne à caractères larges selon que `stream` est ouvert en mode texte ou en mode binaire, respectivement.  
  
 Les versions avec le suffixe `_nolock` sont identiques mais elles ne sont pas protégées contre les interférence en provenance d'autres threads.  
  
 Pour plus d'informations sur le traitement des caractères et des caractères multioctets dans les modes de texte et binaires, consultez l'[E\/S de flux de données Unicode dans les modes de texte et binaires](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_fgettc`|`fgetc`|`fgetc`|`fgetwc`|  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`fgetc`|\<stdio.h\>|  
|`fgetwc`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_fgetc.c  
// This program uses getc to read the first  
// 80 input characters (or until the end of input)  
// and place them into a string named buffer.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   FILE *stream;  
   char buffer[81];  
   int  i, ch;  
  
   // Open file to read line from:  
   fopen_s( &stream, "crt_fgetc.txt", "r" );  
   if( stream == NULL )  
      exit( 0 );  
  
   // Read in first 80 characters and place them in "buffer":   
   ch = fgetc( stream );  
   for( i=0; (i < 80 ) && ( feof( stream ) == 0 ); i++ )  
   {  
      buffer[i] = (char)ch;  
      ch = fgetc( stream );  
   }  
  
   // Add null to end string   
   buffer[i] = '\0';  
   printf( "%s\n", buffer );  
   fclose( stream );  
}  
```  
  
## Entrée : crt\_fgetc.txt  
  
```  
Line one.  
Line two.  
```  
  
### Sortie  
  
```  
Line one.  
Line two.  
```  
  
## Équivalent .NET Framework  
  
-   [System::IO::StreamReader::Read](https://msdn.microsoft.com/en-us/library/system.io.streamreader.read.aspx).  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fputc, fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)