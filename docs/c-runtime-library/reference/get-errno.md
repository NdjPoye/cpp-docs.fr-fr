---
title: _get_errno | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_errno
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_errno
dev_langs:
- C++
helpviewer_keywords:
- get_errno function
- errno global variable
- _get_errno function
ms.assetid: b3fd5ebc-f41b-4314-a2f4-2f2d79d6e740
caps.latest.revision: 19
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
ms.openlocfilehash: c88a88d5307c83dad50e465b130b253ac21b37f7
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="geterrno"></a>_get_errno
Obtient la valeur actuelle de la variable globale errno.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t _get_errno(   
   int * pValue   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [out] `pValue`  
 Pointeur désignant un entier à remplir avec la valeur actuelle de la variable `errno`.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne zéro si l'opération a réussi et un code d'erreur en cas d'échec. Si `pValue` a la valeur `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, cette fonction affecte la valeur `errno` à `EINVAL` et retourne `EINVAL`.  
  
## <a name="remarks"></a>Notes  
 Les valeurs possibles de `errno` sont définies dans Errno.h. Consultez également [errno, constantes](../../c-runtime-library/errno-constants.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_get_errno.c  
#include <stdio.h>  
#include <fcntl.h>  
#include <sys/stat.h>  
#include <share.h>  
#include <errno.h>  
  
int main()  
{  
   errno_t err;  
   int pfh;  
   _sopen_s( &pfh, "nonexistent.file", _O_WRONLY, _SH_DENYNO, _S_IWRITE );  
   _get_errno( &err );  
   printf( "errno = %d\n", err );  
   printf( "fyi, ENOENT = %d\n", ENOENT );  
}  
```  
  
```Output  
errno = 2  
fyi, ENOENT = 2  
```  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|En-tête facultatif|  
|-------------|---------------------|---------------------|  
|`_get_errno`|\<stdlib.h>|\<errno.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="see-also"></a>Voir aussi  
 [_set_errno](../../c-runtime-library/reference/set-errno.md)   
 [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)
