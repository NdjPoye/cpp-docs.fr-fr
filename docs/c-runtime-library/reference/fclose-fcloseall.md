---
title: fclose, _fcloseall | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fclose
- _fcloseall
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
- fclose
- _fcloseall
dev_langs:
- C++
helpviewer_keywords:
- fclose function
- streams, closing
- _fcloseall function
ms.assetid: c3c6ea72-92c6-450a-a33e-3e568d2784a4
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 46b9086e4c75a699acec47e3b6b68ba7bcc231cf
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="fclose-fcloseall"></a>fclose, _fcloseall
Ferme un flux (`fclose`) ou ferme tous les flux ouverts (`_fcloseall`).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int fclose(   
   FILE *stream   
);  
int _fcloseall( void );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `stream`  
 Pointeur vers la structure `FILE` .  
  
## <a name="return-value"></a>Valeur de retour  
 `fclose` retourne 0 si le flux est fermé correctement. `_fcloseall` retourne le nombre total de flux fermés. Ces deux fonctions retournent `EOF` pour indiquer une erreur.  
  
## <a name="remarks"></a>Notes  
 La fonction `fclose` ferme `stream`. Si `stream` a la valeur `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à continuer, `fclose` définit `errno` sur `EINVAL` et retourne `EOF`. Nous vous recommandons de toujours vérifier le pointeur `stream` avant d’appeler cette fonction.  
  
 Consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour plus d’informations sur ces éléments et autres codes d’erreur.  
  
 La fonction `_fcloseall` ferme tous les flux à l’exception de `stdin`, `stdout`, `stderr` (et, dans MS-DOS, `_stdaux` et `_stdprn`). En outre, elle ferme et supprime tous les fichiers temporaires créés par `tmpfile`. Dans les deux fonctions, toutes les mémoires tampons associées au flux sont vidées avant la fermeture. Les mémoires tampons allouées par le système sont libérées quand le flux est fermé. Les mémoires tampons assignées par l’utilisateur avec `setbuf` et `setvbuf` ne sont pas automatiquement libérées.  
  
 **Remarque :** Quand ces fonctions sont utilisées pour fermer un flux, le descripteur de fichier sous-jacent et le handle de fichier de système d’exploitation (ou socket) sont fermés, ainsi que le flux. Ainsi, si le fichier a été ouvert à l’origine en tant que handle ou descripteur de fichier et qu’il est fermé avec `fclose`, n’appelez pas également `_close` pour fermer le descripteur de fichier, ou la fonction Win32 `CloseHandle` pour fermer le handle de fichier.  
  
 `fclose` et `_fcloseall` incluent du code qui protège contre les interférences avec d’autres threads. Pour une version sans verrouillage d’un `fclose`, consultez `_fclose_nolock`.  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`fclose`|\<stdio.h>|  
|`_fcloseall`|\<stdio.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple relatif à [fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_fdopen, _wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, _wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)
