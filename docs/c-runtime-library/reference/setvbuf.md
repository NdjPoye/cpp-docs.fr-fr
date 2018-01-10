---
title: setvbuf | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: setvbuf
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
f1_keywords: setvbuf
dev_langs: C++
helpviewer_keywords:
- controlling stream buffering
- stream buffering
- setvbuf function
ms.assetid: 6aa5aa37-3408-4fa0-992f-87f9f9c4baea
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0855982627c60c51ec5753031ae932ffd430f024
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="setvbuf"></a>setvbuf
Contrôle la mise en mémoire tampon du flux et la taille de la mémoire tampon.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int setvbuf(  
   FILE *stream,  
   char *buffer,  
   int mode,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `stream`  
 Pointeur vers la structure `FILE` .  
  
 `buffer`  
 Mémoire tampon allouée par l’utilisateur.  
  
 `mode`  
 Mode de mise en mémoire tampon.  
  
 `size`  
 Taille de la mémoire tampon en octets. Plage autorisée : 2 <= `size` <= INT_MAX (2147483647). En interne, la valeur fournie pour `size` est arrondie vers le bas au multiple de 2 le plus proche.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne 0 en cas de réussite.  
  
 Si `stream` a la valeur `NULL` ou si `mode` ou `size` ne se trouve pas dans une plage valide, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, cette fonction retourne -1 et affecte à `errno` la valeur `EINVAL`.  
  
 Pour plus d’informations sur ces codes d’erreur et les autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 La fonction `setvbuf` permet au programme de contrôler la mise en mémoire tampon et la taille de la mémoire tampon pour `stream`. `stream` doit faire référence à un fichier ouvert qui n’a pas subi d’opération d’E/S depuis son ouverture. Le tableau désigné par `buffer` est utilisé en tant que mémoire tampon, sauf s’il a la valeur `NULL`, auquel cas `setvbuf` utilise une mémoire tampon allouée automatiquement de longueur `size`/2 * 2 octets.  
  
 Le mode doit être `_IOFBF`, `_IOLBF` ou `_IONBF`. Si `mode` a la valeur `_IOFBF` ou `_IOLBF`, `size` est utilisé comme taille de la mémoire tampon. Si `mode` a la valeur `_IONBF`, le flux n’est pas mis en mémoire tampon et `size` et `buffer` sont ignorés. Les valeurs de `mode` et leur signification sont les suivantes :  
  
 `_IOFBF`  
 Mise en mémoire tampon complète. Autrement dit, `buffer` est utilisé comme mémoire tampon et `size` comme taille de la mémoire tampon. Si `buffer` a la valeur `NULL`, une mémoire tampon allouée automatiquement d’une longueur de `size` octets est utilisée.  
  
 `_IOLBF`  
 Pour certains systèmes, ce mode assure une mise en mémoire tampon de ligne. Cependant, pour Win32, son comportement est identique à `_IOFBF` (mise en mémoire tampon complète).  
  
 `_IONBF`  
 Aucune mémoire tampon n’est utilisée, quel que soit le paramétrage de `buffer` ou `size`.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`setvbuf`|\<stdio.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_setvbuf.c  
// This program opens two streams: stream1  
// and stream2. It then uses setvbuf to give stream1 a  
// user-defined buffer of 1024 bytes and stream2 no buffer.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   char buf[1024];  
   FILE *stream1, *stream2;  
  
   if( fopen_s( &stream1, "data1", "a" ) == 0 &&  
       fopen_s( &stream2, "data2", "w" ) == 0 )  
   {  
      if( setvbuf( stream1, buf, _IOFBF, sizeof( buf ) ) != 0 )  
         printf( "Incorrect type or size of buffer for stream1\n" );  
      else  
         printf( "'stream1' now has a buffer of 1024 bytes\n" );  
      if( setvbuf( stream2, NULL, _IONBF, 0 ) != 0 )  
         printf( "Incorrect type or size of buffer for stream2\n" );  
      else  
         printf( "'stream2' now has no buffer\n" );  
      _fcloseall();  
   }  
}  
```  
  
```Output  
'stream1' now has a buffer of 1024 bytes  
'stream2' now has no buffer  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [setbuf](../../c-runtime-library/reference/setbuf.md)