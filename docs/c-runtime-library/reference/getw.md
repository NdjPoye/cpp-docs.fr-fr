---
title: _getw | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _getw
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
- _getw
dev_langs:
- C++
helpviewer_keywords:
- _getw function
- integers, getting from streams
- getw function
ms.assetid: ef75facc-b84e-470f-9f5f-8746c90822a0
caps.latest.revision: 14
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
ms.openlocfilehash: 0a6b39cc8780af58f0ea5c4023cac7339473bae4
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="getw"></a>_getw
Obtient un entier à partir d’un flux.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _getw(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `stream`  
 Pointeur désignant la structure `FILE`.  
  
## <a name="return-value"></a>Valeur de retour  
 `_getw` retourne la valeur entière lue. Une valeur de retour égale à `EOF` indique une erreur ou la fin du fichier. Toutefois, étant donné que la valeur `EOF` est également une valeur d’entier légitime, utilisez `feof` ou `ferror` pour vérifier une condition d’erreur ou de fin de fichier. Si `stream` a la valeur `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, `errno` a la valeur `EINVAL` et la fonction retourne une valeur `EOF`.  
  
## <a name="remarks"></a>Notes  
 La fonction `_getw` lit la valeur binaire suivante de type `int` à partir du fichier associé à `stream` et incrémente le pointeur de fichier associé (le cas échéant) pour qu’il désigne le caractère non lu suivant. `_getw` ne considère pas que les éléments du flux sont alignés de manière spécifique. Des problèmes de portage peuvent se produire avec `_getw`, car la taille du type `int` et l’ordre des octets dans le type `int` diffèrent d’un système à l’autre.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_getw`|\<stdio.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_getw.c  
// This program uses _getw to read a word  
// from a stream, then performs an error check.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   FILE *stream;  
   int i;  
  
   if( fopen_s( &stream, "crt_getw.txt", "rb" ) )  
      printf( "Couldn't open file\n" );  
   else  
   {  
      // Read a word from the stream:  
      i = _getw( stream );  
  
      // If there is an error...  
      if( ferror( stream ) )  
      {  
         printf( "_getw failed\n" );  
         clearerr_s( stream );  
      }  
      else  
         printf( "First data word in file: 0x%.4x\n", i );  
      fclose( stream );  
   }  
}  
```  
  
## <a name="input-crtgetwtxt"></a>Entrée : crt_getw.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>Sortie  
  
```  
First data word in file: 0x656e694c  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [_putw](../../c-runtime-library/reference/putw.md)
