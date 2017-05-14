---
title: fputc, fputwc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fputc
- fputwc
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fputc
- fputwc
- _fputtc
dev_langs:
- C++
helpviewer_keywords:
- streams, writing characters to
- fputtc function
- _fputtc function
- fputwc function
- fputc function
ms.assetid: 5a0a593d-43f4-4fa2-a401-ec4e23de4d2f
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 7eb1bb55bd153f4ef5387b616b72f611e3a50a9f
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="fputc-fputwc"></a>fputc, fputwc
Écrit un caractère dans un flux.  
  
## <a name="syntax"></a>Syntaxe  
  
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
  
#### <a name="parameters"></a>Paramètres  
 `c`  
 Caractère à écrire.  
  
 `stream`  
 Pointeur vers la structure `FILE` .  
  
## <a name="return-value"></a>Valeur de retour  
 Chacune de ces fonctions retourne le caractère écrit. Pour `fputc`, une valeur de retour égale à `EOF` indique une erreur. Pour `fputwc`, une valeur de retour égale à `WEOF` indique une erreur. Si `stream` a la valeur `NULL`, ces fonctions appellent le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à continuer, elles retournent `EOF` et définissent `errno` sur `EINVAL`.  
  
 Consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour plus d’informations sur ces éléments et autres codes d’erreur.  
  
## <a name="remarks"></a>Notes  
 Chacune de ces fonctions écrit le caractère unique `c` dans un fichier à la position indiquée par l’indicateur de position de fichier associé (si défini) et avance l’indicateur comme il convient. Dans le cas de `fputc` et `fputwc`, le fichier est associé `stream`. Si le fichier ne peut pas prendre en charge les demandes de positionnement ou a été ouvert en mode ajout, le caractère est ajouté à la fin du flux.  
  
 Les deux fonctions se comportent de la même façon si le flux est ouvert en mode ANSI. `fputc` ne prend actuellement pas en charge la sortie vers un flux UNICODE.  
  
 Les versions avec le suffixe `_nolock` sont identiques, à ceci près qu’elles ne sont pas protégées contre les interférences par d’autres threads. Pour plus d’informations, consultez [_fputc_nolock, _fputwc_nolock](../../c-runtime-library/reference/fputc-nolock-fputwc-nolock.md).  
  
 Voici une série de notes spécifiques aux routines.  
  
|Routine|Notes|  
|-------------|-------------|  
|`fputc`|Équivalente à `putc`, mais implémentée uniquement comme une fonction, plutôt que comme une fonction et une macro.|  
|`fputwc`|Version à caractères larges de `fputc`. Écrit `c` comme un caractère multioctet ou large selon que `stream` est ouvert en mode texte ou binaire.|  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_fputtc`|`fputc`|`fputc`|`fputwc`|  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`fputc`|\<stdio.h>|  
|`fputwc`|\<stdio.h> ou \<wchar.h>|  
  
 La console n'est pas prise en charge dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] . Les handles de flux standard associés à la console (`stdin`, `stdout` et `stderr`) doivent être redirigés pour que les fonctions Runtime C puissent les utiliser dans les applications du [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]. Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
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
  
```Output  
This is a test of fputc!!  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fgetc, fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)
