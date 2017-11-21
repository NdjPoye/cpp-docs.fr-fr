---
title: _get_doserrno | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _get_doserrno
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
- _get_doserrno
- get_doserrno
dev_langs: C++
helpviewer_keywords:
- get_doserrno function
- _get_doserrno function
ms.assetid: 7fec7be3-6e39-4181-846b-8ef24489361c
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 67f546afa3059508787c7d3a5295d2b85651f125
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="getdoserrno"></a>_get_doserrno
Obtient la valeur d'erreur retournée par le système d'exploitation avant qu'elle ne soit traduite en valeur `errno`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t _get_doserrno(   
   int * pValue   
);   
```  
  
#### <a name="parameters"></a>Paramètres  
 [out] `pValue`  
 Pointeur vers un entier à remplir avec la valeur actuelle de la macro globale `_doserrno`.  
  
## <a name="return-value"></a>Valeur de retour  
 Si `_get_doserrno` réussit, retourne zéro ; en cas d'échec, retourne un code d'erreur. Si `pValue` a la valeur `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, cette fonction affecte la valeur `errno` à `EINVAL` et retourne `EINVAL`.  
  
## <a name="remarks"></a>Notes  
 La macro globale `_doserrno` prend la valeur zéro pendant l'initialisation CRT, avant le début de l'exécution du processus. Elle prend la valeur d'erreur du système d'exploitation retournée par tout appel de fonction au niveau système qui retourne une erreur de système d'exploitation, et elle n'est jamais réinitialisée à zéro pendant l'exécution. Quand vous écrivez du code pour vérifier la valeur d’erreur retournée par une fonction, effacez toujours `_doserrno` en utilisant [_set_doserrno](../../c-runtime-library/reference/set-doserrno.md) avant l’appel de fonction. Comme un autre appel de fonction peut remplacer `_doserrno`, vérifiez la valeur en utilisant `_get_doserrno` immédiatement après l'appel de fonction.  
  
 Nous conseillons [_get_errno](../../c-runtime-library/reference/get-errno.md) au lieu de `_get_doserrno` pour les codes d’erreurs portables.  
  
 Les valeurs possibles de `_doserrno` sont définies dans \<errno.h>.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|En-tête facultatif|  
|-------------|---------------------|---------------------|  
|`_get_doserrno`|\<stdlib.h>, \<cstdlib> (C++)|\<errno.h>, \<cerrno> (C++)|  
  
 `_get_doserrno` est une extension Microsoft. Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [_set_doserrno](../../c-runtime-library/reference/set-doserrno.md)   
 [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)