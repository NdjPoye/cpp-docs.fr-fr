---
title: feof | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- feof
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
- feof
dev_langs:
- C++
helpviewer_keywords:
- end of file, testing for
- feof function
ms.assetid: 09081eee-7c4b-4189-861f-2fad95d3ec6d
caps.latest.revision: 15
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
ms.openlocfilehash: 345ebdff9733ac25bd3a42dc5a5465d501e1f28f
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="feof"></a>feof
Teste la fin de fichier sur un flux.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int feof(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `stream`  
 Pointeur vers la structure `FILE` .  
  
## <a name="return-value"></a>Valeur de retour  
 La fonction `feof` retourne une valeur différente de zéro si une opération de lecture a tenté de lire au-delà de la fin du fichier ; sinon, elle retourne 0. Si le pointeur de flux est `NULL`, la fonction appelle le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, `errno` a la valeur `EINVAL`, et `feof` retourne 0.  
  
 Consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour plus d’informations sur ces éléments et autres codes d’erreur.  
  
## <a name="remarks"></a>Notes  
 La routine `feof` (implémentée à la fois en tant que fonction et que macro) détermine si la fin de `stream` a été passée. Quand la fin du fichier est passée, les opérations de lecture retournent un indicateur de fin de fichier jusqu’à ce que le flux soit fermé ou que `rewind`, `fsetpos`, `fseek` ou `clearerr` soit appelé sur lui.  
  
 Par exemple, si un fichier contient 10 octets et que vous lisez 10 octets du fichier, `feof` retourne 0 car, même si le pointeur de fichier est à la fin du fichier, vous n’avez pas essayé de lire au-delà de la fin. C’est seulement si vous tentez de lire un 11e octet que `feof` retourne une valeur différente de zéro.  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`feof`|\<stdio.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_feof.c  
// This program uses feof to indicate when  
// it reaches the end of the file CRT_FEOF.TXT. It also  
// checks for errors with ferror.  
//  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int  count, total = 0;  
   char buffer[100];  
   FILE *stream;  
  
   fopen_s( &stream, "crt_feof.txt", "r" );  
   if( stream == NULL )  
      exit( 1 );  
  
   // Cycle until end of file reached:  
   while( !feof( stream ) )  
   {  
      // Attempt to read in 100 bytes:  
      count = fread( buffer, sizeof( char ), 100, stream );  
      if( ferror( stream ) )      {  
         perror( "Read error" );  
         break;  
      }  
  
      // Total up actual bytes read  
      total += count;  
   }  
   printf( "Number of bytes read = %d\n", total );  
   fclose( stream );  
}  
```  
  
## <a name="input-crtfeoftxt"></a>Entrée : crt_feof.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>Sortie  
  
```  
Number of bytes read = 19  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion des erreurs](../../c-runtime-library/error-handling-crt.md)   
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [_eof](../../c-runtime-library/reference/eof.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, _wperror](../../c-runtime-library/reference/perror-wperror.md)
