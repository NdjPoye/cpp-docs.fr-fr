---
title: _futime, _futime32, _futime64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _futime64
- _futime32
- _futime
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- futime
- _futime
- futime64
- _futime64
dev_langs:
- C++
helpviewer_keywords:
- _futime function
- futime32 function
- futime64 function
- file modification time [C++]
- _futime64 function
- futime function
- _futime32 function
ms.assetid: b942ce8f-5cc7-4fa8-ab47-de5965eded53
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 03eda993cbc087d5dc39f2c9d0f985ac5db48099
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="futime-futime32-futime64"></a>_futime, _futime32, _futime64
Définit l’heure de modification d’un fichier ouvert.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _futime(   
   int fd,  
   struct _utimbuf *filetime   
);  
int _futime32(   
   int fd,  
   struct __utimbuf32 *filetime   
);  
int _futime64(   
   int fd,  
   struct __utimbuf64 *filetime   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `fd`  
 Descripteur du fichier ouvert.  
  
 `filetime`  
 Pointeur désignant la structure qui contient la nouvelle date de modification.  
  
## <a name="return-value"></a>Valeur de retour  
 Retournent 0 en cas de réussite. Si une erreur se produit, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, la fonction retourne -1 et `errno` a la valeur `EBADF`, qui indique un descripteur de fichier non valide, ou `EINVAL`, qui indique un paramètre non valide.  
  
## <a name="remarks"></a>Remarques  
 Le `_futime` routine définit la date de modification et le temps d’accès sur le fichier ouvert associé `fd`. `_futime` est identique à [_utime](../../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md), à ceci près que son argument est le descripteur d’un fichier ouvert, et non le nom d’un fichier ou un chemin de fichier. La structure `_utimbuf` contient des champs pour les nouvelles date de modification et heure d’accès. Les deux champs doivent contenir des valeurs valides. `_utimbuf32` et `_utimbuf64` sont identiques à `_utimbuf`, sauf pour l’utilisation des types d’heure 32 bits et 64 bits, respectivement. `_futime` et `_utimbuf` utilisent un type d’heure 64 bits, tandis que `_futime` a le même comportement que `_futime64`. Si vous devez forcer l’ancien comportement, définissez `_USE_32BIT_TIME_T`. Grâce à cette opération, `_futime` a un comportement identique à `_futime32` et la structure `_utimbuf` utilise le type d’heure 32 bits, devenant ainsi équivalente à `__utimbuf32`.  
  
 `_futime64`, qui utilise la structure `__utimbuf64`, peut lire et modifier les dates de fichier jusqu’au 31 décembre 3000 à 23:59:59, heure UTC, alors qu’un appel à `_futime32` échoue si la date du fichier est postérieure au 18 janvier 2038 à 23:59:59, heure UTC. Le 1er janvier 1970 à minuit est la limite inférieure de la plage de dates pour ces fonctions.  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|En-tête facultatif|  
|--------------|---------------------|---------------------|  
|`_futime`|\<sys/utime.h>|\<errno.h>|  
|`_futime32`|\<sys/utime.h>|\<errno.h>|  
|`_futime64`|\<sys/utime.h>|\<errno.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_futime.c  
// This program uses _futime to set the  
// file-modification time to the current time.  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <fcntl.h>  
#include <io.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <sys/utime.h>  
#include <share.h>  
  
int main( void )  
{  
   int hFile;  
  
   // Show file time before and after.   
   system( "dir crt_futime.c_input" );  
  
   _sopen_s( &hFile, "crt_futime.c_input", _O_RDWR, _SH_DENYNO, 0 );  
  
   if( _futime( hFile, NULL ) == -1 )  
      perror( "_futime failed\n" );  
   else  
      printf( "File time modified\n" );  
  
   _close (hFile);  
  
   system( "dir crt_futime.c_input" );  
}  
```  
  
## <a name="input-crtfutimecinput"></a>Entrée : crt_futime.c_input  
  
```  
Arbitrary file contents.  
```  
  
### <a name="sample-output"></a>Résultat de l'exemple  
  
```  
Volume in drive Z has no label.  
 Volume Serial Number is 5C68-57C1  
  
 Directory of Z:\crt  
  
03/25/2004  10:40 AM                24 crt_futime.c_input  
               1 File(s)             24 bytes  
               0 Dir(s)  24,268,476,416 bytes free  
 Volume in drive Z has no label.  
 Volume Serial Number is 5C68-57C1  
  
 Directory of Z:\crt  
  
03/25/2004  10:41 AM                24 crt_futime.c_input  
               1 File(s)             24 bytes  
               0 Dir(s)  24,268,476,416 bytes free  
File time modified  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)
