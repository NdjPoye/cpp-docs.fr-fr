---
title: "_fgetc_nolock, _fgetwc_nolock | Microsoft Docs"
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
  - "_fgetc_nolock"
  - "_fgetwc_nolock"
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
  - "_fgetwc_nolock"
  - "fgettc_nolock"
  - "fgetwc_nolock"
  - "_fgetc_nolock"
  - "_fgettc_nolock"
  - "fgetc_nolock"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fgetc_nolock (fonction)"
  - "_fgettc_nolock (fonction)"
  - "_fgetwc_nolock (fonction)"
  - "caractères, lire"
  - "fgetc_nolock (fonction)"
  - "fgettc_nolock (fonction)"
  - "fgetwc_nolock (fonction)"
  - "lire des caractères dans des flux"
  - "flux, lire des caractères dans"
ms.assetid: fb8e7c5b-4503-493a-879e-6a1db75aa114
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fgetc_nolock, _fgetwc_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lit un caractère d'un flux de données sans verrouiller le thread.  
  
## Syntaxe  
  
```  
int _fgetc_nolock(   
   FILE *stream   
);  
wint_t _fgetwc_nolock(   
   FILE *stream   
);  
```  
  
#### Paramètres  
 `stream`  
 Pointeur vers la structure `FILE`.  
  
## Valeur de retour  
 Consultez [fgetc, fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md).  
  
## Notes  
 `_fgetc_nolock` et `_fgetwc_nolock` sont identiques à `fgetc` et `fgetwc`, respectivement, sauf qu'ils ne sont pas protégés des interférences avec d'autres threads.  Elles peuvent être plus rapides, car elles n'entraînent pas la charge du verrouillage des autres threads.  Utilisez ces fonctions uniquement dans les contextes thread\-safe, tels que les applications à un seul thread ou lorsque la portée appelante gère déjà l'isolation des threads.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_fgettc_nolock`|`_fgetc_nolock`|`_fgetc_nolock`|`_fgetwc_nolock`|  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`_fgetc_nolock`|\<stdio.h\>|  
|`_fgetwc_nolock`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_fgetc_nolock.c  
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
   if( fopen_s( &stream, "crt_fgetc_nolock.txt", "r" ) != 0 )  
      exit( 0 );  
  
   // Read in first 80 characters and place them in "buffer":  
   ch = fgetc( stream );  
   for( i=0; (i < 80 ) && ( feof( stream ) == 0 ); i++ )  
   {  
      buffer[i] = (char)ch;  
      ch = _fgetc_nolock( stream );  
   }  
  
   // Add null to end string   
   buffer[i] = '\0';  
   printf( "%s\n", buffer );  
   fclose( stream );  
}  
```  
  
## Entrée : crt\_fgetc\_nolock.txt  
  
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