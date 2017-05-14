---
title: _CrtGetDumpClient | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtGetDumpClient
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
- CrtGetDumpClient
- _CrtGetDumpClient
dev_langs:
- C++
helpviewer_keywords:
- _CrtGetDumpClient function
- CrtGetDumpClient function
ms.assetid: 9051867f-341b-493b-b53d-45d2b454a3ad
caps.latest.revision: 13
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
ms.openlocfilehash: 941fc0ffdeb691b599ceb8c79d4439da4d36dd7f
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="crtgetdumpclient"></a>_CrtGetDumpClient
Récupère la fonction définie par l’application actuelle pour vider les blocs de mémoire de type `_CLIENT_BLOCK` (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
_CRT_DUMP_CLIENT _CrtGetDumpClient( void );  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne la routine de vidage actuelle.  
  
## <a name="remarks"></a>Notes  
 La fonction `_CrtGetDumpClient` récupère la fonction de raccordement actuelle pour vider les objets stockés dans les blocs de mémoire `_CLIENT_BLOCK` pour le processus de vidage de mémoire de débogage du runtime C.  
  
 Pour plus d’informations sur l’utilisation d’autres fonctions d’exécution compatibles avec le raccordement et sur l’écriture de vos propres fonctions de raccordement définies par le client, consultez [Écriture de fonctions de raccordement de débogage](/visualstudio/debugger/debug-hook-function-writing).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_CrtGetDumpClient`|\<crtdbg.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md)   
 [_CrtSetDumpClient](../../c-runtime-library/reference/crtsetdumpclient.md)
