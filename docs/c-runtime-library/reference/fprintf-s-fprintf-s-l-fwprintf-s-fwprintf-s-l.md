---
title: fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fprintf_s_l
- fwprintf_s
- fprintf_s
- _fwprintf_s_l
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _ftprintf_s
- fprintf_s
- fwprintf_s
dev_langs:
- C++
helpviewer_keywords:
- ftprintf_s_l function
- ftprintf_s function
- _fprintf_s_l function
- _ftprintf_s function
- _ftprintf_s_l function
- fwprintf_s_l function
- fwprintf_s function
- fprintf_s_l function
- fprintf_s function
- _fwprintf_s_l function
- print formatted data to streams
ms.assetid: 16067c3c-69ce-472a-8272-9aadf1f5beed
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: d6fc4a71132483e4eb8646fe5394994a0af7fbd6
ms.lasthandoff: 02/24/2017

---
# <a name="fprintfs-fprintfsl-fwprintfs-fwprintfsl"></a>fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l
Envoient les données mises en forme vers un flux. Ces versions de [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md) intègrent les améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
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
  
#### <a name="parameters"></a>Paramètres  
 `stream`  
 Pointeur vers la structure `FILE` .  
  
 `format`  
 Chaîne de contrôle de format.  
  
 `argument`  
 Arguments facultatifs.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 `fprintf_s` retourne le nombre d’octets écrits. `fwprintf_s` retourne le nombre de caractères larges écrits. Chacune de ces fonctions retourne une valeur négative à la place en cas d’erreur de sortie.  
  
## <a name="remarks"></a>Notes  
 `fprintf_s` met en forme et envoie une série de caractères et de valeurs vers la sortie `stream`*.* Chaque fonction `argument` (le cas échéant) est convertie et sortie selon la spécification de format correspondante dans `format`*.* Pour `fprintf_s`, l’argument `format` a les mêmes syntaxe et utilisation que dans `printf_s`.  
  
 `fwprintf_s` est une version à caractères larges de `fprintf_s` ; dans `fwprintf_s`, `format` est une chaîne à caractères larges. Ces fonctions se comportent de la même façon si le flux est ouvert en mode ANSI. `fprintf_s` ne prend actuellement pas en charge la sortie vers un flux UNICODE.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux actuels.  
  
> [!IMPORTANT]
>  Assurez-vous que `format` n'est pas une chaîne définie par l'utilisateur.  
  
 Comme les versions non sécurisées (voir [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)), ces fonctions valident leurs paramètres et appellent le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md), si `stream` ou `format` est un pointeur null. Ces fonctions diffèrent des versions non sécurisées en ce sens que la chaîne de format elle-même est également validée. S’il existe des spécificateurs de mise en forme inconnus ou incorrects, ces fonctions génèrent l’exception de paramètre non valide. Dans tous les cas, si l’exécution est autorisée à se poursuivre, les fonctions retournent -1 et définissent `errno` avec la valeur `EINVAL`. Consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour plus d’informations sur ces éléments et autres codes d’erreur.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ftprintf_s`|`fprintf_s`|`fprintf_s`|`fwprintf_s`|  
|`_ftprintf_s_l`|`_fprintf_s_l`|`_fprintf_s_l`|`_fwprintf_s_l`|  
  
 Pour plus d’informations, consultez [Spécifications de format](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`fprintf_s`, `_fprintf_s_l`|\<stdio.h>|  
|`fwprintf_s`, `_fwprintf_s_l`|\<stdio.h> ou \<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
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
  
```Output  
this is a string  
10  
1.500000  
```  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 [System::IO::StreamWriter::Write](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.write.aspx)  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [fscanf, _fscanf_l, fwscanf, _fwscanf_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)
