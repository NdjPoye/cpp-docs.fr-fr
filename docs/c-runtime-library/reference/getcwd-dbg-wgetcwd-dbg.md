---
title: _getcwd_dbg, _wgetcwd_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wgetcwd_dbg
- _getcwd_dbg
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getcwd_dbg
- _wgetcwd_dbg
- getcwd_dbg
- wgetcwd_dbg
dev_langs:
- C++
helpviewer_keywords:
- wgetcwd_dbg function
- working directory
- _getcwd_dbg function
- getcwd_dbg function
- current working directory
- _wgetcwd_dbg function
- directories [C++], current working
ms.assetid: 8d5d151f-d844-4aa6-a28c-1c11a22dc00d
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 2218210801bff38094d06d96736a7f05f7be29cf
ms.lasthandoff: 02/24/2017

---
# <a name="getcwddbg-wgetcwddbg"></a>_getcwd_dbg, _wgetcwd_dbg
Versions de débogage des fonctions [_getcwd, _wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md) (disponibles uniquement durant le débogage).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
char *_getcwd_dbg(   
   char *buffer,  
   int maxlen,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
wchar_t *_wgetcwd_dbg(   
   wchar_t *buffer,  
   int maxlen,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `buffer`  
 Emplacement de stockage pour le chemin.  
  
 `maxlen`  
 Longueur maximale du chemin d'accès en caractères : `char` pour `_getcwd_dbg` et `wchar_t` pour `_wgetcwd_dbg`.  
  
 `blockType`  
 Type demandé du bloc de mémoire : `_CLIENT_BLOCK` ou `_NORMAL_BLOCK`.  
  
 `filename`  
 Pointeur vers le nom du fichier source qui a demandé l'opération d'allocation ou `NULL`.  
  
 `linenumber`  
 Numéro de ligne dans le fichier source où l'opération d'allocation a été demandée ou `NULL`.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur vers `buffer`. Une valeur de retour `NULL` indique une erreur et `errno` prend la valeur `ENOMEM`, ce qui indique que la mémoire est insuffisante pour allouer `maxlen` octets (quand un argument `NULL` est donné comme `buffer`), ou la valeur `ERANGE`, ce qui indique que le chemin d’accès fait plus de `maxlen` caractères.  
  
 Pour plus d’informations, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 Les fonctions `_getcwd_dbg` et `_wgetcwd_dbg` sont identiques à `_getcwd` et `_wgetcwd` sauf que, quand _`DEBUG` est défini, ces fonctions utilisent la version de débogage de `malloc` et `_malloc_dbg` pour allouer la mémoire si la valeur `NULL` est passée comme premier paramètre. Pour plus d’informations, consultez [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 Dans la plupart des cas, vous n'avez pas besoin d'appeler ces fonctions de manière explicite. À la place, vous pouvez définir l'indicateur `_CRTDBG_MAP_ALLOC`. Quand `_CRTDBG_MAP_ALLOC` est défini, les appels à `_getcwd` et `_wgetcwd` sont remappés à `_getcwd_dbg` et `_wgetcwd_dbg`, respectivement, avec `blockType` défini sur `_NORMAL_BLOCK`. Ainsi, vous n'avez pas besoin d'appeler ces fonctions de manière explicite sauf si vous souhaitez marquer les blocs du tas comme `_CLIENT_BLOCK`. Pour plus d’informations, consultez [Types de bloc sur le tas de débogage](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine Tchar.h|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tgetcwd_dbg`|`_getcwd_dbg`|`_getcwd_dbg`|`_wgetcwd_dbg`|  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_getcwd_dbg`|\<crtdbg.h>|  
|`_wgetcwd_dbg`|\<crtdbg.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 <xref:System.Environment.CurrentDirectory%2A>  
  
## <a name="see-also"></a>Voir aussi  
 [_getcwd, _wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [Contrôle de répertoire](../../c-runtime-library/directory-control.md)   
 [Versions Debug des fonctions d’allocation du tas](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)
