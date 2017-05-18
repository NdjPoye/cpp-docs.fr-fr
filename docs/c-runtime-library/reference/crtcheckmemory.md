---
title: _CrtCheckMemory | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtCheckMemory
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
- CrtCheckMemory
- _CrtCheckMemory
dev_langs:
- C++
helpviewer_keywords:
- _CrtCheckMemory function
- CrtCheckMemory function
ms.assetid: 457cc72e-60fd-4177-ab5c-6ae26a420765
caps.latest.revision: 12
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
ms.openlocfilehash: 82b64afbdd80e9b1433f8f9873b4e295fc2e20c1
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="crtcheckmemory"></a>_CrtCheckMemory
Confirme l’intégrité des blocs de mémoire alloués dans le tas de débogage (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
int _CrtCheckMemory( void );  
```  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, `_CrtCheckMemory` retourne TRUE ; sinon, la fonction retourne FALSE.  
  
## <a name="remarks"></a>Notes  
 La fonction `_CrtCheckMemory` valide la mémoire allouée par le gestionnaire de tas de débogage en vérifiant le tas de base sous-jacent et en inspectant chaque bloc de mémoire. Si une incohérence de mémoire ou une erreur est rencontrée dans le tas de base sous-jacent, les informations d’en-tête de débogage ou les mémoires tampons de remplacement, `_CrtCheckMemory` génère un rapport de débogage avec les informations décrivant la condition d’erreur. Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, les appels à `_CrtCheckMemory` sont supprimés pendant le prétraitement.  
  
 Le comportement de `_CrtCheckMemory` peut être contrôlé en définissant les champs de bits de l’indicateur [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) à l’aide de la fonction [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md). Si le champ de bits **_CRTDBG_CHECK_ALWAYS_DF** est activé (ON), `_CrtCheckMemory` est appelé chaque fois qu’une opération d’allocation de mémoire est demandée. Bien que cette méthode ralentisse l’exécution, il est utile d’intercepter rapidement les erreurs. Si le champ de bits **_CRTDBG_ALLOC_MEM_DF** est désactivé (OFF), `_CrtCheckMemory` ne vérifie pas le tas et retourne immédiatement **TRUE**.  
  
 Comme cette fonction retourne **TRUE** ou **FALSE**, elle peut être passée à l’une des macros [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) pour créer un mécanisme de gestion des erreurs de débogage simple. L’exemple suivant provoque un échec d’assertion si l’altération est détectée dans le tas :  
  
```  
_ASSERTE( _CrtCheckMemory( ) );  
```  
  
 Pour plus d’informations sur la façon dont `_CrtCheckMemory` peut être utilisé avec d’autres fonctions de débogage, consultez [Fonctions de création de rapports sur l’état du tas](/visualstudio/debugger/crt-debug-heap-details). Pour obtenir une vue d’ensemble de la gestion de la mémoire et du tas de débogage, consultez [Détails du tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_CrtCheckMemory`|\<crtdbg.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
 Pour obtenir un exemple d’utilisation de `_CrtCheckMemory`, consultez [crt_dbg1](http://msdn.microsoft.com/en-us/17b4b20c-e849-48f5-8eb5-dca6509cbaf9).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)   
 [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)
