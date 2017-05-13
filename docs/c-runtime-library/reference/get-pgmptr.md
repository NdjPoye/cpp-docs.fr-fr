---
title: _get_pgmptr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_pgmptr
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
- get_pgmptr
- _get_pgmptr
dev_langs:
- C++
helpviewer_keywords:
- get_pgmptr function
- _get_pgmptr function
- pgmptr global variable
- _pgmptr global variable
ms.assetid: 29f16a9f-a685-4721-add3-7fad4f67eece
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: bb04c82492a241c8a1089e2414358a11b54fff70
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="getpgmptr"></a>_get_pgmptr
Obtient la valeur actuelle de la variable globale `_pgmptr`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t _get_pgmptr(   
   char **pValue   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [out] `pValue`  
 Pointeur vers une chaîne à remplir avec la valeur actuelle de la variable `_pgmptr`.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne zéro si l'opération a réussi et un code d'erreur en cas d'échec. Si `pValue` a la valeur `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, cette fonction affecte la valeur `errno` à `EINVAL` et retourne `EINVAL`.  
  
## <a name="remarks"></a>Remarques  
 Le `_pgmptr` (variable globale) contient le chemin d’accès complet au fichier exécutable associé au processus. Pour plus d’informations, consultez [_pgmptr, _wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_get_pgmptr`|\<stdlib.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="see-also"></a>Voir aussi  
 [_get_wpgmptr](../../c-runtime-library/reference/get-wpgmptr.md)
