---
title: _CrtMemCheckpoint | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtMemCheckpoint
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
- CrtMemCheckpoint
- _CrtMemCheckpoint
- crtdbg/_CrtMemCheckpoint
dev_langs:
- C++
helpviewer_keywords:
- CrtMemCheckpoint function
- _CrtMemCheckpoint function
ms.assetid: f1bacbaa-5a0c-498a-ac7a-b6131d83dfbc
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 5f9b0615a51318ea0e783a90d7a450b6e11372d2
ms.lasthandoff: 02/24/2017

---
# <a name="crtmemcheckpoint"></a>_CrtMemCheckpoint
Obtient l'état actuel du tas de débogage et le stocke dans une structure `_CrtMemState` fournie par l'application (version debug uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void _CrtMemCheckpoint(  
   _CrtMemState *state   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `state`  
 Pointeur vers la structure `_CrtMemState` à remplir avec le point de contrôle de mémoire.  
  
## <a name="remarks"></a>Notes  
 La fonction `_CrtMemCheckpoint` crée un instantané de l'état actuel du tas de débogage à tout moment donné. Cet instantané peut être utilisé par d’autres fonctions d’état du tas, comme [_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md), pour aider à détecter les fuites de mémoire et d’autres problèmes. Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, les appels à `_CrtMemState` sont supprimés durant le prétraitement.  
  
 L'application doit passer un pointeur vers une instance précédemment allouée de la structure `_CrtMemState` , définie dans Crtdbg.h, dans le paramètre `state` . Si `_CrtMemCheckpoint` rencontre une erreur pendant la création du point de contrôle, la fonction génère un rapport de débogage `_CRT_WARN` qui décrit le problème.  
  
 Pour plus d’informations sur les fonctions d’état du tas et sur la structure `_CrtMemState`, consultez [Fonctions de création de rapports sur l’état du tas](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version Debug du tas de base, consultez [Détails du tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
 Si `state` a la valeur `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, [errno, _doserrno, _sys_errlist, et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ont la valeur `EINVAL` et la fonction retourne le contrôle.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_CrtMemCheckpoint`|\<crtdbg.h>, \<errno.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
 **Bibliothèques :** uniquement les versions Debug de la bibliothèque UCRT.  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md)
