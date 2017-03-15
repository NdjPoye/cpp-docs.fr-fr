---
title: _putw | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _putw
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
- _putw
- putw
dev_langs:
- C++
helpviewer_keywords:
- integers, writing to streams
- putw function
- streams, writing integers to
- _putw function
ms.assetid: 83d63644-249d-4a39-87e5-3b7aa313968d
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: ae689f0f299f307bdda9771d4929623e04a7196f
ms.lasthandoff: 02/24/2017

---
# <a name="putw"></a>_putw
Écrit un entier dans un flux.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      int _putw(  
   int binint,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 *binint*  
 Entier binaire à sortir.  
  
 `stream`  
 Pointeur désignant la structure **FILE**.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne la valeur écrite. La valeur de retour `EOF` peut indiquer une erreur. Sachant que `EOF` est aussi une valeur entière légitime, utilisez `ferror` pour vérifier une erreur. Si `stream` est un pointeur Null, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, cette fonction affecte la valeur `errno` à `EINVAL` et retourne `EOF`.  
  
 Pour obtenir des informations sur ces codes d’erreur et les autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 La fonction `_putw` écrit une valeur binaire de type `int` à la position actuelle de *stream.* `_putw` n’affecte pas l’alignement des éléments du flux alignés ni ne présume aucun alignement spécial. `_putw` vise principalement à assurer la compatibilité avec les bibliothèques précédentes. Des problèmes de portabilité peuvent se présenter avec `_putw`, car la taille d’un `int` et l’ordre des octets au sein d’un `int` diffèrent d’un système à l’autre.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_putw`|\<stdio.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_putw.c  
/* This program uses _putw to write a  
 * word to a stream, then performs an error check.  
 */  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   FILE *stream;  
   unsigned u;  
   if( fopen_s( &stream, "data.out", "wb" ) )  
      exit( 1 );  
   for( u = 0; u < 10; u++ )  
   {  
      _putw( u + 0x2132, stream );   /* Write word to stream. */  
      if( ferror( stream ) )         /* Make error check. */  
      {  
         printf( "_putw failed" );  
         clearerr_s( stream );  
         exit( 1 );  
      }  
   }  
   printf( "Wrote ten words\n" );  
   fclose( stream );  
}  
```  
  
## <a name="output"></a>Sortie  
  
```  
Wrote ten words  
```  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [_getw](../../c-runtime-library/reference/getw.md)
