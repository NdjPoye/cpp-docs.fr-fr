---
title: "fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l | Microsoft Docs"
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
  - "_fprintf_s_l"
  - "fwprintf_s"
  - "fprintf_s"
  - "_fwprintf_s_l"
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
apitype: "DLLExport"
f1_keywords: 
  - "_ftprintf_s"
  - "fprintf_s"
  - "fwprintf_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fprintf_s_l (fonction)"
  - "_ftprintf_s (fonction)"
  - "_ftprintf_s_l (fonction)"
  - "_fwprintf_s_l (fonction)"
  - "fprintf_s (fonction)"
  - "fprintf_s_l (fonction)"
  - "ftprintf_s (fonction)"
  - "ftprintf_s_l (fonction)"
  - "fwprintf_s (fonction)"
  - "fwprintf_s_l (fonction)"
  - "imprimer des données mises en forme dans les flux"
ms.assetid: 16067c3c-69ce-472a-8272-9aadf1f5beed
caps.latest.revision: 21
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

imprimer des données mises en forme dans les flux  Il s'agit de versions de [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md) avec des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
int fprintf_s(   
   FILE *stream,  
   const char *format [,  
   argument ]...  
);  
int _fprintf_s_l(   
   FILE *stream,  
   const char *format,  
   locale_t locale [,  
   argument ]...  
);  
int fwprintf_s(   
   FILE *stream,  
   const wchar_t *format [,  
   argument ]...  
);  
int _fwprintf_s_l(   
   FILE *stream,  
   const wchar_t *format,  
   locale_t locale [,  
   argument ]…  
);  
```  
  
#### Paramètres  
 `stream`  
 Pointeur vers la structure `FILE`.  
  
 `format`  
 Chaîne de contrôle de format.  
  
 `argument`  
 Arguments facultatifs.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 `fprintf_s`retourne le nombre d'octets écrit.  `fwprintf_s` retourne le nombre de caractères larges entrés.  Chacune de ces fonctions retourne une valeur négative à la place lorsqu'une erreur de sortie se produit.  
  
## Notes  
 La fonction `fprintf_s` met en forme et retourne une série de caractères et de valeurs en sortie `stream` Chaque fonction `argument` \(le cas échéant\) est convertie et sortie selon la spécification de format correspondante dans \<parameterReference\>format\<\/parameterReference\>\<legacyItalic\>.\<\/legacyItalic\> Pour `fprintf_s`, l'argument `format` a la même syntaxe et utilisation que dans `printf_s`.  
  
 `fwprintf_s` est une version à caractères larges de `fprintf_s` ; dans `fwprintf_s`, `format` est une chaîne à caractères larges.  Ces fonctions se comportent de la même façon si le flux est ouvert en mode ANSI.  `fprintf_s` ne prend pas en charge actuellement la sortie dans un flux UNICODE.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux actuels.  
  
> [!IMPORTANT]
>  Assurez\-vous que `format` n'est pas une chaîne définie par l'utilisateur.  
  
 Comme les versions non sécurisées \(consultez [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)\), ces fonctions valident leurs paramètres et appellent le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md), si `stream` ou `format` est un pointeur null.  Ces fonctions diffèrent des versions non sécurisées car la chaîne de format elle\-même est également validée.  S'il existe des spécificateurs de format inconnus ou mal formés, ces fonctions appellent le gestionnaire de paramètre non valide.  Dans tous les cas, si l'exécution est autorisée à se poursuivre, ces fonctions retournent \-1 et définissent `errno` à `EINVAL` .  Consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour plus d'informations sur ces éléments et autres codes d'erreur.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_ftprintf_s`|`fprintf_s`|`fprintf_s`|`fwprintf_s`|  
|`_ftprintf_s_l`|`_fprintf_s_l`|`_fprintf_s_l`|`_fwprintf_s_l`|  
  
 Pour plus d'informations, consultez [Spécifications de format](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`fprintf_s`, `_fprintf_s_l`|\<stdio.h\>|  
|`fwprintf_s`, `_fwprintf_s_l`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_fprintf_s.c  
// This program uses fprintf_s to format various  
// data and print it to the file named FPRINTF_S.OUT. It  
// then displays FPRINTF_S.OUT on the screen using the system  
// function to invoke the operating-system TYPE command.  
  
#include <stdio.h>  
#include <process.h>  
  
FILE *stream;  
  
int main( void )  
{  
   int    i = 10;  
   double fp = 1.5;  
   char   s[] = "this is a string";  
   char   c = '\n';  
  
   fopen_s( &stream, "fprintf_s.out", "w" );  
   fprintf_s( stream, "%s%c", s, c );  
   fprintf_s( stream, "%d\n", i );  
   fprintf_s( stream, "%f\n", fp );  
   fclose( stream );  
   system( "type fprintf_s.out" );  
}  
```  
  
  **Il s'agit d'une chaîne.**  
**10**  
**1.500000**   
## Équivalent .NET Framework  
 [System::IO::StreamWriter::Write](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.write.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [fscanf, \_fscanf\_l, fwscanf, \_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)