---
title: "_fputc_nolock, _fputwc_nolock | Microsoft Docs"
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
  - "_fputwc_nolock"
  - "_fputc_nolock"
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
  - "_fputc_nolock"
  - "fputwc_nolock"
  - "fputc_nolock"
  - "fputtc_nolock"
  - "_fputwc_nolock"
  - "_fputtc_nolock"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fputc_nolock (fonction)"
  - "_fputtc_nolock (fonction)"
  - "_fputwc_nolock (fonction)"
  - "fputc_nolock (fonction)"
  - "fputtc_nolock (fonction)"
  - "fputwc_nolock (fonction)"
  - "flux, écrire des caractères dans"
ms.assetid: c63eb3ad-58fa-46d0-9249-9c25f815eab9
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fputc_nolock, _fputwc_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Écrit un caractère dans un flux sans verrouiller le thread.  
  
## Syntaxe  
  
```  
int _fputc_nolock(  
   int c,  
   FILE *stream   
);  
wint_t _fputwc_nolock(  
   wchar_t c,  
   FILE *stream   
);  
```  
  
#### Paramètres  
 `c`  
 Caractère à écrire.  
  
 `stream`  
 Pointeur vers la structure `FILE`.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne le caractère écrit.  Pour des informations sur les erreurs , consultez [fputc, fputwc](../../c-runtime-library/reference/fputc-fputwc.md).  
  
## Notes  
 `_fputc_nolock` et `_fputwc_nolock` sont identiques à `fputc` et `fputwc`, respectivement, sauf qu'ils ne sont pas protégés des interférences avec d'autres threads.  Elles peuvent être plus rapides, car elles n'entraînent pas la charge du verrouillage des autres threads.  Utilisez ces fonctions uniquement dans les contextes thread\-safe, tels que les applications à un seul thread ou lorsque la portée appelante gère déjà l'isolation des threads.  
  
 Ces deux fonctions se comportent de la même façon si le flux est ouvert en mode ANSI.  `_fputc_nolock` ne prend pas en charge actuellement la sortie dans un flux UNICODE.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_fputtc_nolock`|`_fputc_nolock`|`_fputc_nolock`|`_fputwc_nolock`|  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`_fputc_nolock`|\<stdio.h\>|  
|`_fputwc_nolock`|\<stdio.h\> ou \<wchar.h\>|  
  
 La console n'est pas prise en charge dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Les handles de flux standard associés à la console, `stdin`, `stdout` et `stderr` doivent être redirigés pour que les fonctions runtime C puissent les utiliser dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_fputc_nolock.c  
// This program uses _fputc_nolock  
// to send a character array to stdout.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char strptr1[] = "This is a test of _fputc_nolock!!\n";  
   char *p;  
  
   // Print line to stream using fputc.   
   p = strptr1;  
   while( (*p != '\0') && _fputc_nolock( *(p++), stdout ) != EOF ) ;  
  
}  
```  
  
  **Il s'agit d'un test de \_fputc\_nolock\!\!**   
## Équivalent .NET Framework  
  
-   [System::IO::StreamWriter::Write](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.write.aspx)  
  
-   [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fgetc, fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)