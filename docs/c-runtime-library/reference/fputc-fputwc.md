---
title: "fputc, fputwc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fputc"
  - "fputwc"
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
  - "fputc"
  - "fputwc"
  - "_fputtc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fputtc (fonction)"
  - "fputc (fonction)"
  - "fputtc (fonction)"
  - "fputwc (fonction)"
  - "flux, écrire des caractères dans"
ms.assetid: 5a0a593d-43f4-4fa2-a401-ec4e23de4d2f
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# fputc, fputwc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Écrit un caractère dans un flux.  
  
## Syntaxe  
  
```  
int fputc(  
   int c,  
   FILE *stream   
);  
wint_t fputwc(  
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
 Chacune de ces fonctions retourne le caractère écrit.  Pour `fputc`, une valeur de retour de `EOF` indique une erreur.  Pour `fputwc`, une valeur de retour de `WEOF` indique une erreur.  Si `stream` est `NULL`, ces fonctions appellent le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, elles retournent `EOF` et définissent `errno` à la valeur `EINVAL`.  
  
 Consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour plus d'informations sur ces éléments et autres codes d'erreur.  
  
## Notes  
 Chacune de ces fonctions écrit le caractère unique `c` dans un fichier à la position indiquée par l'indicateur de position de fichier associé \(si défini\) et avance les indicateurs comme il le faut.  Dans le cas de `fputc` et `fputwc`, le fichier est associé à `stream`*.* Si le fichier ne peut pas prendre en charge le positionnement de requêtes ou était ouvert en mode adjonction, le caractère est ajouté à la fin du flux.  
  
 Ces deux fonctions se comportent de la même façon si le flux est ouvert en mode ANSI.  `fputc` ne prend pas en charge actuellement la sortie dans un flux UNICODE.  
  
 Les versions avec le suffixe `_nolock` sont identiques mais elles ne sont pas protégées contre les interférence en provenance d'autres threads.  Pour plus d'informations, consultez[\_fputc\_nolock, \_fputwc\_nolock](../../c-runtime-library/reference/fputc-nolock-fputwc-nolock.md).  
  
 Les remarques concernant les routines sont indiquées dans la suite.  
  
|Routine|Remarques|  
|-------------|---------------|  
|`fputc`|Équivalent à `putc`, mais implémenté uniquement comme une fonction plutôt que comme une fonction et une macro.|  
|`fputwc`|Version à caractères larges de `fputc`.  Ecrit `c` comme un caractère multioctets ou caractère large selon que `stream` est ouvert en mode texte ou en mode binaire.|  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_fputtc`|`fputc`|`fputc`|`fputwc`|  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`fputc`|\<stdio.h\>|  
|`fputwc`|\<stdio.h\> ou \<wchar.h\>|  
  
 La console n'est pas prise en charge dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Les handles de flux standard associés à la console, `stdin`, `stdout` et `stderr` doivent être redirigés pour que les fonctions runtime C puissent les utiliser dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_fputc.c  
// This program uses fputc  
// to send a character array to stdout.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char strptr1[] = "This is a test of fputc!!\n";  
   char *p;  
  
   // Print line to stream using fputc.   
   p = strptr1;  
   while( (*p != '\0') && fputc( *(p++), stdout ) != EOF ) ;  
  
}  
```  
  
  **Il s'agit d'un test de fputc \!**   
## Équivalent .NET Framework  
  
-   [System::IO::StreamWriter::Write](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.write.aspx)  
  
-   [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fgetc, fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)