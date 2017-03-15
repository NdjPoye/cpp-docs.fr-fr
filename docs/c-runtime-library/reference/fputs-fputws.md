---
title: "fputs, fputws | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fputs"
  - "fputws"
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
  - "fputs"
  - "fputws"
  - "_fputts"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fputts (fonction)"
  - "fputs (fonction)"
  - "fputts (fonction)"
  - "fputws (fonction)"
  - "flux, écrire des chaînes dans"
ms.assetid: d48c82b8-aa17-4830-8c7d-30442ddbb326
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# fputs, fputws
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Écrit une chaîne dans un flux.  
  
## Syntaxe  
  
```  
int fputs(   
   const char *str,  
   FILE *stream   
);  
int fputws(   
   const wchar_t *str,  
   FILE *stream   
);  
```  
  
#### Paramètres  
 `str`  
 Chaîne de sortie.  
  
 `stream`  
 Pointeur vers la structure `FILE`.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne une valeur non négative s'il est réussi.  En cas d'erreur, `fputs` et `fputws` retournent `EOF`.  Si `str` ou `stream` est un pointeur null, ces fonctions invoquent le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` avec la valeur `EINVAL` et puis `fputs` retourne `EOF`, et `fputws` retourne `WEOF`.  
  
 Consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour plus d'informations sur ces éléments et autres codes d'erreur.  
  
## Notes  
 Chacune de ces fonctions copie `str` dans le `stream` de sortie à la position actuelle.  `fputws` copie l'argument à caractère large `str` à `stream` comme une chaîne de caractères multi\-octets ou chaîne à caractères larges selon que `stream` est ouvert en mode texte ou en mode binaire, respectivement.  Aucune fonction ne copie le caractère nul de fin.  
  
 Ces deux fonctions se comportent de la même façon si le flux est ouvert en mode ANSI.  `fputs` ne prend pas en charge actuellement la sortie dans un flux UNICODE.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_fputts`|`fputs`|`fputs`|`fputws`|  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`fputs`|\<stdio.h\>|  
|`fputws`|\<stdio.h\> ou \<wchar.h\>|  
  
 La console n'est pas prise en charge dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Les handles de flux standard associés à la console, `stdin`, `stdout` et `stderr` doivent être redirigés pour que les fonctions runtime C puissent les utiliser dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_fputs.c  
// This program uses fputs to write  
// a single line to the stdout stream.  
  
#include <stdio.h>  
  
int main( void )  
{  
   fputs( "Hello world from fputs.\n", stdout );  
}  
```  
  
  **Hello World de fputs.**   
## Équivalent .NET Framework  
 [System::IO::StreamWriter::Write](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.write.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fgets, fgetws](../../c-runtime-library/reference/fgets-fgetws.md)   
 [gets, \_getws](../../c-runtime-library/gets-getws.md)   
 [puts, \_putws](../../c-runtime-library/reference/puts-putws.md)