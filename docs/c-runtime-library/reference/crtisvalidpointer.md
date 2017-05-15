---
title: _CrtIsValidPointer | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtIsValidPointer
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
- CrtlsValidPointer
- _CrtIsValidPointer
dev_langs:
- C++
helpviewer_keywords:
- CrtIsValidPointer function
- _CrtIsValidPointer function
ms.assetid: 91c35590-ea5e-450f-a15d-ad8d62ade1fa
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 021277c17252d18ee0127d710b3a64b3d25fd6d9
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="crtisvalidpointer"></a>_CrtIsValidPointer
Vérifie qu'un pointeur n'a pas la valeur null. Dans les versions de la bibliothèque Runtime C antérieures à Visual Studio 2010, vérifie qu'une plage mémoire spécifiée est valide pour la lecture et l'écriture (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _CrtIsValidPointer(   
   const void *address,  
   unsigned int size,  
   int access   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 adresse  
 Pointe vers le début de la plage mémoire dont la validité doit être testée.  
  
 `size`  
 Taille de la plage mémoire spécifiée (en octets).  
  
 access  
 Accessibilité en lecture/écriture à déterminer pour la plage mémoire.  
  
## <a name="return-value"></a>Valeur de retour  
 `_CrtIsValidPointer` retourne TRUE si le pointeur spécifié n'a pas la valeur null. Dans les versions de bibliothèque CRT antérieures à Visual Studio 2010, retourne TRUE si la plage mémoire spécifiée est valide pour la ou les opérations spécifiées. Dans le cas contraire, la fonction retourne FALSE.  
  
## <a name="remarks"></a>Notes  
 À partir de la bibliothèque CRT de Visual Studio 2010, les paramètres de taille et d'accès sont ignorés et `_CrtIsValidPointer` vérifie uniquement que l'adresse spécifiée n'a pas la valeur null. Ce test étant facile à effectuer par soi-même, nous vous déconseillons d'utiliser cette fonction. Dans les versions antérieures à Visual Studio 2010, la fonction vérifie que la plage mémoire débutant à `address` et s'étendant pour des octets `size` est valide pour la ou les opérations d'accessibilité spécifiées. Quand `access` a la valeur TRUE, la plage mémoire est vérifiée pour la lecture et l'écriture. Quand `access` a la valeur FALSE, la plage mémoire n'est validée que pour la lecture. Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, les appels à `_CrtIsValidPointer` sont supprimés durant le prétraitement.  
  
 Comme cette fonction retourne TRUE ou FALSE, elle peut être passée à l’une des macros [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) pour créer un mécanisme de gestion des erreurs de débogage simple. L'exemple suivant provoque un échec d'assertion si la plage mémoire n'est pas valide pour les opérations à la fois de lecture et d'écriture :  
  
```  
_ASSERTE( _CrtIsValidPointer( address, size, TRUE ) );  
```  
  
 Pour plus d’informations sur la façon dont `_CrtIsValidPointer` peut être utilisé avec d’autres macros et fonctions de débogage, consultez [Macros pour la création de rapports](/visualstudio/debugger/macros-for-reporting). Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version de débogage du tas de base, consultez [Détails du tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_CrtIsValidPointer`|\<crtdbg.h>|  
  
 `_CrtIsValidPointer` est une extension Microsoft. Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliothèques  
 Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
 Voir l’exemple pour la rubrique [_CrtIsValidHeapPointer](../../c-runtime-library/reference/crtisvalidheappointer.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)
