---
title: fgetc, fgetwc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fgetwc
- fgetc
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
- _fgettc
- fgetwc
- fgetc
dev_langs:
- C++
helpviewer_keywords:
- fgettc function
- characters, reading
- _fgettc function
- fgetc function
- streams, reading characters from
- reading characters from streams
- fgetwc function
ms.assetid: 13348b7b-dc86-421c-9d6c-611ca79c8338
caps.latest.revision: 18
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 5a0a697a4ba7cfea7c24809796179861fccc2f68
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="fgetc-fgetwc"></a>fgetc, fgetwc
Lisent un caractère d’un flux.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int fgetc(   
   FILE *stream   
);  
wint_t fgetwc(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `stream`  
 Pointeur vers la structure `FILE` .  
  
## <a name="return-value"></a>Valeur de retour  
 `fgetc` retourne le caractère lu en tant que `int` ou retourne `EOF` pour indiquer une erreur ou la fin du fichier. `fgetwc` retourne, en tant que [wint_t](../../c-runtime-library/standard-types.md), le caractère large qui correspond au caractère lu ou retourne `WEOF` pour indiquer une erreur ou la fin du fichier. Pour les deux fonctions, utilisez `feof` ou `ferror` pour faire la distinction entre une erreur et une condition de fin de fichier. Si une erreur de lecture se produit, l’indicateur d’erreur pour le flux est défini. Si `stream` a la valeur `NULL`, `fgetc` et `fgetwc` appellent le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions attribuent à `errno` la valeur `EINVAL` et retournent `EOF`.  
  
## <a name="remarks"></a>Notes  
 Chacune de ces fonctions lit un caractère à partir de la position actuelle du fichier associé à `stream`. Ensuite, la fonction incrémente le pointeur de fichier associé (si défini) pour pointer vers le caractère suivant. Si le flux est à la fin du fichier, l’indicateur de fin de fichier pour le flux est défini.  
  
 `fgetc` est équivalente à `getc`, mais est implémentée uniquement comme une fonction, plutôt que comme une fonction et une macro.  
  
 `fgetwc` est la version à caractères larges de `fgetc` ; elle lit `c` comme un caractère multioctet ou large selon que `stream` est ouvert en mode texte ou binaire.  
  
 Les versions avec le suffixe `_nolock` sont identiques, à ceci près qu’elles ne sont pas protégées contre les interférences par d’autres threads.  
  
 Pour plus d’informations sur le traitement des caractères larges et des caractères multioctets en modes texte et binaire, consultez [E/S de flux Unicode en modes texte et binaire](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_fgettc`|`fgetc`|`fgetc`|`fgetwc`|  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`fgetc`|\<stdio.h>|  
|`fgetwc`|\<stdio.h> ou \<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
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
  
## <a name="input-crtfgetctxt"></a>Entrée : crt_fgetc.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>Sortie  
  
```  
Line one.  
Line two.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fputc, fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)
