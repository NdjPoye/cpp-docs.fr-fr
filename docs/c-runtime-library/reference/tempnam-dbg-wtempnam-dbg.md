---
title: _tempnam_dbg, _wtempnam_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wtempnam_dbg
- _tempnam_dbg
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
apitype: DLLExport
f1_keywords:
- wtempnam_dbg
- tempnam_dbg
- _tempnam_dbg
- _wtempnam_dbg
dev_langs:
- C++
helpviewer_keywords:
- file names [C++], creating temporary
- tempnam_dbg function
- temporary files, creating
- file names [C++], temporary
- wtempnam_dbg function
- _tempnam_dbg function
- _wtempnam_dbg function
ms.assetid: e3760bb4-bb01-4808-b689-2c45af56a170
caps.latest.revision: 13
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 260c5ae7348516683d8e749a2dcb6cdac6ea0943
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="tempnamdbg-wtempnamdbg"></a>_tempnam_dbg, _wtempnam_dbg
Versions des fonctions [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) qui utilisent la version debug de `malloc, _malloc_dbg`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
char *_tempnam_dbg(  
   const char *dir,  
   const char *prefix,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
wchar_t *_wtempnam_dbg(  
   const wchar_t *dir,  
   const wchar_t *prefix,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `dir`  
 Chemin d’accès utilisé dans le nom de fichier en l’absence de variable d’environnement TMP ou si TMP n’est pas un répertoire valide.  
  
 `prefix`  
 Chaîne qui sera ajoutée aux noms retournés par `_tempnam`.  
  
 `blockType`  
 Type de bloc de mémoire demandé : `_CLIENT_BLOCK` ou `_NORMAL_BLOCK`.  
  
 `filename`  
 Pointeur vers le nom du fichier source qui a demandé l'opération d'allocation ou `NULL`.  
  
 `linenumber`  
 Numéro de ligne dans le fichier source où l'opération d'allocation a été demandée ou `NULL`.  
  
## <a name="return-value"></a>Valeur de retour  
 Chaque fonction retourne un pointeur vers le nom généré ou `NULL` en cas de défaillance. Une défaillance peut se produire si un nom de répertoire non valide a été spécifié dans la variable d'environnement TMP et dans le paramètre `dir`.  
  
> [!NOTE]
>  `free` (ou `free_dbg`) doit être appelé pour les pointeurs alloués par `_tempnam_dbg` et `_wtempnam_dbg`.  
  
## <a name="remarks"></a>Remarques  
 Le `_tempnam_dbg` et `_wtempnam_dbg` fonctions sont identiques aux `_tempnam` et `_wtempnam` , sauf que, lorsque `_DEBUG` est défini, ces fonctions utilisent la version debug de `malloc` et `_malloc_dbg`, allocation de mémoire si `NULL` est passée comme premier paramètre. Pour plus d’informations, consultez [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 Dans la plupart des cas, vous n'avez pas besoin d'appeler ces fonctions de manière explicite. À la place, vous pouvez définir l'indicateur `_CRTDBG_MAP_ALLOC`. Quand `_CRTDBG_MAP_ALLOC` est défini, les appels à `_tempnam` et `_wtempnam` sont remappés à `_tempnam_dbg` et `_wtempnam_dbg`, respectivement, avec `blockType` défini sur `_NORMAL_BLOCK`. Ainsi, vous n'avez pas besoin d'appeler ces fonctions de manière explicite sauf si vous souhaitez marquer les blocs du tas comme `_CLIENT_BLOCK`. Pour plus d’informations, consultez [Types de bloc sur le tas de débogage](/visualstudio/debugger/crt-debug-heap-details).  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ttempnam_dbg`|`_tempnam_dbg`|`_tempnam_dbg`|`_wtempnam_dbg`|  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_tempnam_dbg`, `_wtempnam_dbg`|\<crtdbg.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="see-also"></a>Voir aussi  
 [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [Versions Debug des fonctions d'allocation du tas](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)
