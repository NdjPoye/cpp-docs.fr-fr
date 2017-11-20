---
title: setbuf | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: setbuf
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
f1_keywords: setbuf
dev_langs: C++
helpviewer_keywords:
- setbuf function
- stream buffering
ms.assetid: 13beda22-7b56-455d-8a6c-f2eb636885b9
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a57e815376414724b2c92977c52a309f86c63b50
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="setbuf"></a>setbuf
Contrôle la mise en mémoire tampon de flux. Cette fonction est dépréciée. Utilisez à la place [setvbuf](../../c-runtime-library/reference/setvbuf.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void setbuf(  
   FILE *stream,  
   char *buffer   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `stream`  
 Pointeur vers la structure `FILE` .  
  
 `buffer`  
 Mémoire tampon allouée par l’utilisateur.  
  
## <a name="remarks"></a>Notes  
 La fonction `setbuf` contrôle la mise en mémoire pour `stream`. L’argument `stream` doit faire référence à un fichier ouvert qui n’a pas été lu ou écrit. Si l’argument `buffer` a la valeur `NULL`, le flux n’est pas mis en mémoire tampon. Sinon, la mémoire tampon doit pointer vers un tableau de caractères de longueur `BUFSIZ`, `BUFSIZ` correspondant à la taille de la mémoire tampon telle que définie dans STDIO.H. La mémoire tampon spécifiée par l’utilisateur est utilisée pour la mise en mémoire tampon des E/S à la place de la mémoire tampon par défaut allouée par le système. Par défaut, le flux `stderr` n’est pas mis en mémoire tampon, mais vous pouvez utiliser `setbuf` pour assigner des mémoires tampon à `stderr`.  
  
 La fonction `setbuf` a été remplacée par [setvbuf](../../c-runtime-library/reference/setvbuf.md), qui est la routine par défaut pour le nouveau code. `setbuf` est conservée pour assurer la compatibilité avec le code existant.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`setbuf`|\<stdio.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_setbuf.c  
// compile with: /W3  
// This program first opens files named DATA1 and  
// DATA2. Then it uses setbuf to give DATA1 a user-assigned  
// buffer and to change DATA2 so that it has no buffer.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char buf[BUFSIZ];  
   FILE *stream1, *stream2;  
  
   fopen_s( &stream1, "data1", "a" );  
   fopen_s( &stream2, "data2", "w" );  
  
   if( (stream1 != NULL) && (stream2 != NULL) )  
   {  
      // "stream1" uses user-assigned buffer:  
      setbuf( stream1, buf ); // C4996  
      // Note: setbuf is deprecated; consider using setvbuf instead  
      printf( "stream1 set to user-defined buffer at: %Fp\n", buf );  
  
      // "stream2" is unbuffered  
      setbuf( stream2, NULL ); // C4996  
      printf( "stream2 buffering disabled\n" );  
      _fcloseall();  
   }  
}  
```  
  
```Output  
stream1 set to user-defined buffer at: 0012FCDC  
stream2 buffering disabled  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)