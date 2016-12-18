---
title: "puts, _putws | Microsoft Docs"
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
  - "_putws"
  - "puts"
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
  - "_putts"
  - "_putws"
  - "puts"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_putts (fonction)"
  - "_putws (fonction)"
  - "puts (fonction)"
  - "putts (fonction)"
  - "putws (fonction)"
  - "sortie standard, écrire dans"
  - "chaînes (C++), écrire"
ms.assetid: 32dada12-ed45-40ac-be06-3feeced9ecd6
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# puts, _putws
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Écrit une chaîne dans **stdout**.  
  
## Syntaxe  
  
```  
  
      int puts(  
   const char *str   
);  
int _putws(  
   const wchar_t *str   
);  
```  
  
#### Paramètres  
 `str`  
 Chaîne de sortie.  
  
## Valeur de retour  
 Retourne une valeur positive en cas de succès.  Si `puts` échoue, il retourne `EOF`; si `_putws` échoue, il retourne **WEOF**.  Si `str` est un pointeur null, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction définit `errno` à la valeur `EINVAL` et retourne `EOF` ou **WEOF**.  
  
 Pour plus d'informations sur ces codes d'erreur et autres, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `puts` écrit `str` dans le flux de sortie standard **stdout**, en remplaçant le caractère null de fin de la chaîne \("\\0 "\) avec un caractère de saut de ligne \("\\n "\) dans le flux de sortie.  
  
 `_putws` est la version à caractères élargis de `puts`; les deux fonctions se comportent de la même manière si le flux est ouvert en mode ANSI.  `puts` ne prend pas en charge actuellement la sortie dans un flux UNICODE.  
  
 Sous Windows 2000 et versions ultérieures, **\_putwch** écrit les caractères Unicode à l'aide des paramètres régionaux de CONSOLE.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_putts`|`puts`|`puts`|`_putws`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`puts`|\<stdio.h\>|  
|`_putws`|\<stdio.h\>|  
  
 La console n'est pas prise en charge dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Les handles de flux standard associés à la console, `stdin`, `stdout` et `stderr` doivent être redirigés pour que les fonctions runtime C puissent les utiliser dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_puts.c  
/* This program uses puts to write a string to stdout.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   puts( "Hello world from puts!" );  
}  
```  
  
## Sortie  
  
```  
Hello world from puts!  
```  
  
## Équivalent .NET Framework  
 [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fputs, fputws](../../c-runtime-library/reference/fputs-fputws.md)   
 [fgets, fgetws](../../c-runtime-library/reference/fgets-fgetws.md)