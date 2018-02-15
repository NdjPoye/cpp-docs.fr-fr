---
title: _fgetchar, _fgetwchar | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _fgetchar
- _fgetwchar
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
- fgetwchar
- _fgettchar
- _fgetchar
- _fgetwchar
- fgettchar
dev_langs:
- C++
helpviewer_keywords:
- fgetwchar function
- _fgetchar function
- fgettchar function
- _fgetwchar function
- _fgettchar function
- standard input, reading from
- fgetchar function
ms.assetid: 8bce874c-701a-41a3-b1b2-feff266fb5b9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0eabf9bd54764aaa37bd860eb5bdb7d1ac5232ab
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="fgetchar-fgetwchar"></a>_fgetchar, _fgetwchar
Lit un caractère dans `stdin`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _fgetchar( void );  
wint_t _fgetwchar( void );  
```  
  
## <a name="return-value"></a>Valeur de retour  
 `_fgetchar` retourne le caractère lu en tant que `int` ou retourne `EOF` pour indiquer une erreur ou la fin du fichier. **_**`fgetwchar` retourne, en tant que [wint_t](../../c-runtime-library/standard-types.md), le caractère large qui correspond au caractère lu ou retourne `WEOF` pour indiquer une erreur ou la fin du fichier. Pour les deux fonctions, utilisez `feof` ou `ferror` pour faire la distinction entre une erreur et une condition de fin de fichier.  
  
## <a name="remarks"></a>Notes  
 Ces fonctions lisent un caractère dans `stdin`. Ensuite, la fonction incrémente le pointeur de fichier associé (si défini) pour désigner le caractère suivant. Si le flux est à la fin du fichier, l’indicateur de fin de fichier pour le flux est défini.  
  
 `_fgetchar` équivaut à `fgetc( stdin )`. Elle est également équivalente à `getchar`, mais est implémentée uniquement comme une fonction, plutôt que comme une fonction et une macro. `_fgetwchar` est la version à caractères larges de `_fgetchar`.  
  
 Ces fonctions ne sont pas compatibles avec la norme ANSI.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine Tchar.h|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_fgettchar`|`_fgetchar`|`_fgetchar`|`_fgetwchar`|  
  
## <a name="requirements"></a>Configuration requise  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`_fgetchar`|\<stdio.h>|  
|`_fgetwchar`|\<stdio.h> ou \<wchar.h>|  
  
 La console n’est pas pris en charge dans les applications de plateforme Windows universelle (UWP). Les descripteurs de flux standard qui sont associés à la console :`stdin`, `stdout`, et `stderr`, doivent être redirigés avant que les fonctions d’exécution C peuvent les utiliser dans [ ! Applications INCLUDEUWP. Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
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
  
```Output  
  
      Line one.  
Line two.Line one.  
Line two.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fputc, fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)