---
title: "_fgetchar, _fgetwchar | Microsoft Docs"
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
  - "_fgetchar"
  - "_fgetwchar"
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
  - "fgetwchar"
  - "_fgettchar"
  - "_fgetchar"
  - "_fgetwchar"
  - "fgettchar"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fgetchar (fonction)"
  - "_fgettchar (fonction)"
  - "_fgetwchar (fonction)"
  - "fgetchar (fonction)"
  - "fgettchar (fonction)"
  - "fgetwchar (fonction)"
  - "entrée standard, lire dans"
ms.assetid: 8bce874c-701a-41a3-b1b2-feff266fb5b9
caps.latest.revision: 16
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fgetchar, _fgetwchar
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lit un caractère dans `stdin`.  
  
## Syntaxe  
  
```  
int _fgetchar( void );  
wint_t _fgetwchar( void );  
```  
  
## Valeur de retour  
 `_fgetchar` retourne le caractère lu comme un `int` ou retourne`EOF` pour indiquer une erreur ou une fin de fichier.  **\_**`fgetwchar` retourne, en tant que [wint\_t](../../c-runtime-library/standard-types.md), le caractère élargi correspondant au caractère lu ou retourne `WEOF` pour indiquer une erreur ou fin de fichier.  Pour les deux fonctions, utilisez `feof` ou `ferror` pour différencier une erreur et une fin de fichier.  
  
## Notes  
 Ces fonctions lisent un caractère unique de `stdin`.  Cette fonction incrémente ensuite le pointeur de fichier associé \(si défini\) pour pointer au caractère suivant.  Si le flux est à la fin du fichier, l'indicateur de fin du flux est défini.  
  
 `_fgetchar` équivaut à `fgetc( stdin )`.  Elle est aussi équivalente à `getchar`, mais implémenté uniquement comme une fonction plutôt que comme une fonction et une macro.  `_fgetwchar` est la version à caractère élargi de `_fgetchar`.  
  
 Ces fonctions ne sont pas compatibles avec la norme ANSI.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_fgettchar`|`_fgetchar`|`_fgetchar`|`_fgetwchar`|  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`_fgetchar`|\<stdio.h\>|  
|`_fgetwchar`|\<stdio.h\> ou \<wchar.h\>|  
  
 La console n'est pas prise en charge dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Les handles de flux standard associés à la console, `stdin`, `stdout` et `stderr` doivent être redirigés pour que les fonctions runtime C puissent les utiliser dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_fgetchar.c  
// This program uses _fgetchar to read the first  
// 80 input characters (or until the end of input)  
// and place them into a string named buffer.  
//  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char buffer[81];  
   int  i, ch;  
  
   // Read in first 80 characters and place them in "buffer":  
   ch = _fgetchar();  
   for( i=0; (i < 80 ) && ( feof( stdin ) == 0 ); i++ )  
   {  
      buffer[i] = (char)ch;  
      ch = _fgetchar();  
   }  
  
   // Add null to end string   
   buffer[i] = '\0';  
   printf( "%s\n", buffer );  
}  
```  
  
  **`Ligne une. Ligne deux.`Ligne une.**  
**Ligne deux.**   
## Équivalent .NET Framework  
  
-   [System::IO::StreamReader::Read](https://msdn.microsoft.com/en-us/library/system.io.streamreader.read.aspx).  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fputc, fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)