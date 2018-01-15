---
title: _CrtSetAllocHook | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtSetAllocHook
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
- _CrtSetAllocHook
- CrtSetAllocHook
dev_langs: C++
helpviewer_keywords:
- _CrtSetAllocHook function
- CrtSetAllocHook function
ms.assetid: 405df37b-2fd1-42c8-83bc-90887f17f29d
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ac777b2e2a7ca791821be52b68f136998c33d243
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="crtsetallochook"></a>_CrtSetAllocHook
Installe une fonction d’allocation définie par le client en la raccordant au processus d’allocation de mémoire de débogage du runtime C (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
_CRT_ALLOC_HOOK _CrtSetAllocHook(  
   _CRT_ALLOC_HOOK allocHook   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `allocHook`  
 Nouvelle fonction d’allocation définie par le client à raccorder au processus d’allocation de mémoire de débogage du runtime C  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne la fonction de raccordement d’allocation définie, ou `NULL` si `allocHook` est `NULL`.  
  
## <a name="remarks"></a>Notes  
 `_CrtSetAllocHook` permet à une application de raccorder sa propre fonction d’allocation au processus d’allocation de mémoire de bibliothèque de débogage du runtime C. Ainsi, chaque appel à une fonction d’allocation de débogage pour allouer, réallouer ou libérer un bloc de mémoire déclenche un appel à la fonction de raccordement de l’application. `_CrtSetAllocHook` fournit à une application une méthode simple pour tester comment l’application gère les situations de mémoire insuffisante, la possibilité d’examiner les modèles d’allocation et la possibilité de consigner les informations d’allocation pour une analyse ultérieure. Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, les appels à `_CrtSetAllocHook` sont supprimés durant le prétraitement.  
  
 La fonction `_CrtSetAllocHook` installe la nouvelle fonction d’allocation définie par le client spécifiée dans `allocHook` et retourne la fonction de raccordement définie. L’exemple suivant montre comment un raccordement d’allocation défini par le client doit être prototypé :  
  
```  
int YourAllocHook( int allocType, void *userData, size_t size, int   
blockType, long requestNumber, const unsigned char *filename, int   
lineNumber);  
```  
  
 L’argument `allocType` spécifie le type de l’opération d’allocation `(_HOOK_ALLOC`, `_HOOK_REALLOC` et `_HOOK_FREE`) qui a déclenché l’appel à la fonction de raccordement de l’allocation. Quand le type d’allocation de déclenchement est `_HOOK_FREE`, `userData` est un pointeur désignant la section de données utilisateur du bloc de mémoire sur le point d’être libéré. Toutefois, quand le type d’allocation de déclenchement est `_HOOK_ALLOC` ou `_HOOK_REALLOC`, `userData` est `NULL`, car le bloc de mémoire n’a pas encore été alloué.  
  
 `size` spécifie la taille du bloc de mémoire en octets, `blockType` indique le type du bloc de mémoire, `requestNumber` est le numéro d’ordre d’allocation d’objet du bloc de mémoire et, le cas échéant, `filename` et `lineNumber` spécifient le nom du fichier source et le numéro de ligne où l’opération d’allocation de déclenchement a été lancée.  
  
 Une fois que la fonction de raccordement a terminé le traitement, elle doit retourner une valeur booléenne, qui indique la marche à suivre au processus d’allocation du runtime C principal. Quand la fonction de raccordement souhaite que le processus d’allocation principal se poursuive comme si elle n’avait jamais été appelée, elle doit retourner `TRUE`. Ainsi, l’opération d’allocation de déclenchement d’origine est exécutée. À l’aide de cette implémentation, la fonction de raccordement peut rassembler et enregistrer les informations d’allocation pour une analyse ultérieure, sans interférer avec l’opération d’allocation actuelle ou l’état du tas de débogage.  
  
 Quand la fonction de raccordement souhaite que le processus d’allocation principal se poursuive comme si l’opération d’allocation de déclenchement avait été appelée et avait échoué, elle doit retourner `FALSE`. À l’aide de cette implémentation, la fonction de raccordement peut simuler un large éventail de conditions de mémoire et d’états de tas de débogage pour tester comment l’application gère chaque situation.  
  
 Pour désactiver la fonction de raccordement, transmettez `NULL` à `_CrtSetAllocHook`.  
  
 Pour plus d’informations sur la façon dont `_CrtSetAllocHook` peut être utilisé avec d’autres fonctions de gestion de mémoire ou sur la façon d’écrire vos propres fonctions de raccordement définies par le client, consultez [Écriture de fonctions de raccordement de débogage](/visualstudio/debugger/debug-hook-function-writing).  
  
> [!NOTE]
>  `_CrtSetAllocHook` n’est pas pris en charge sous `/clr:pure`. Les options de compilateur **/clr:pure** et **/clr:safe** sont dépréciées dans Visual Studio 2015.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_CrtSetAllocHook`|\<crtdbg.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
 Pour obtenir un exemple d’utilisation de `_CrtSetAllocHook`, consultez [crt_dbg2](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [_CrtGetAllocHook](../../c-runtime-library/reference/crtgetallochook.md)