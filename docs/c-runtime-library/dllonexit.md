---
title: __dllonexit | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __dllonexit
apilocation:
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcr120_clr0400.dll
apitype: DLLExport
f1_keywords:
- __dllonexit
dev_langs:
- C++
helpviewer_keywords:
- __dllonexit
ms.assetid: 708f2ceb-f95c-46b0-a58d-d68b3fa36f12
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9e59acec12c90d101ef385c379c092c7034f1ed0
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="dllonexit"></a>__dllonexit
Enregistre une routine à appeler au moment de la sortie.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
_onexit_t __dllonexit(   _onexit_t func,  
   _PVFV **  pbegin,   
   _PVFV **  pend   
   )  
```  
  
#### <a name="parameters"></a>Paramètres  
 `func`  
 Pointeur vers une fonction à exécuter à la sortie.  
  
 `pbegin`  
 Pointeur vers une variable qui pointe vers le début d’une liste de fonctions à exécuter au moment du détachement.  
  
 `pend`  
 Pointeur vers une variable qui pointe vers la fin d’une liste de fonctions à exécuter au moment du détachement.  
  
## <a name="return-value"></a>Valeur de retour  
 Si l’opération réussit, pointeur vers la fonction de l’utilisateur. Dans le cas contraire, pointeur NULL.  
  
## <a name="remarks"></a>Notes  
 La fonction `__dllonexit` est analogue à la fonction [_onexit](../c-runtime-library/reference/onexit-onexit-m.md) sauf que les variables globales utilisées par cette fonction ne sont pas visibles pour cette routine. Au lieu de variables globales, cette fonction utilise les paramètres `pbegin` et `pend`.  
  
 Les fonctions `_onexit` et `atexit` dans une DLL liée à MSVCRT.LIB doivent conserver leur propre liste atexit/_onexit. Cette routine est le processus de travail appelé par de telles DLL.  
  
 Le type `_PVFV` est défini en tant que `typedef void (__cdecl *_PVFV)(void)`.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|Fichier obligatoire|  
|-------------|-------------------|  
|__dllonexit|onexit.c|  
  
## <a name="see-also"></a>Voir aussi  
 [_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)
