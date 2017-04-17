---
title: set_unexpected (CRT) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- set_unexpected
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
- set_unexpected
dev_langs:
- C++
helpviewer_keywords:
- set_unexpected function
- unexpected function
- exception handling, termination
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
caps.latest.revision: 11
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
ms.openlocfilehash: 97be545243fb4ef60bff8b8244ca9fd943b25cd6
ms.lasthandoff: 02/24/2017

---
# <a name="setunexpected-crt"></a>set_unexpected (CRT)
Installe votre propre fonction d’arrêt qui doit être appelée par `unexpected`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
unexpected_function set_unexpected(  
   unexpected_function unexpFunction   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `unexpFunction`  
 Pointeur désignant une fonction que vous écrivez pour remplacer la fonction `unexpected`.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur désignant la précédente fonction d’arrêt inscrite par `_set_unexpected`, si bien que la fonction précédente peut être restaurée ultérieurement. Si aucune fonction précédente n’a été définie, la valeur de retour peut être utilisée pour restaurer le comportement par défaut ; cette valeur peut être NULL.  
  
## <a name="remarks"></a>Notes  
 La fonction `set_unexpected` installe `unexpFunction` comme fonction appelée par `unexpected`. `unexpected` n’est pas utilisé dans l’implémentation de gestion des exceptions C++ actuelle. Le type `unexpected_function` est défini dans EH.H comme pointeur vers une fonction inattendue défini par l’utilisateur, `unexpFunction` qui retourne `void`. Votre fonction `unexpFunction` personnalisée ne doit pas retourner de valeur à son appelant.  
  
```  
typedef void ( *unexpected_function )( );  
```  
  
 Par défaut, `unexpected` appelle `terminate`. Vous pouvez modifier ce comportement par défaut en écrivant votre propre fonction d’arrêt et en appelant `set_unexpected` avec le nom de votre fonction comme argument. `unexpected` appelle la dernière fonction donnée comme argument à `set_unexpected`.  
  
 Contrairement à la fonction d’arrêt personnalisée dont l’installation résulte d’un appel à `set_terminate`, une exception peut être levée à partir de `unexpFunction`.  
  
 Dans un environnement multithread, les fonctions inattendues sont gérées séparément pour chaque thread. Chaque nouveau thread doit installer sa propre fonction inattendue. Par conséquent, chaque thread est responsable de sa propre gestion inattendue.  
  
 Dans l’implémentation Microsoft actuelle de gestion des exceptions C++, `unexpected` appelle par défaut la fonction `terminate`, qui n’est jamais appelée par la bibliothèque runtime de gestion des exceptions. Il n’y a aucun avantage particulier à appeler `unexpected` plutôt que `terminate`.  
  
 Il existe un seul gestionnaire `set_unexpected` pour l’ensemble des DLL ou EXE liés de manière dynamique ; même si vous appelez `set_unexpected`, votre gestionnaire peut être remplacé par un autre ou vous pouvez remplacer un gestionnaire défini par une autre DLL ou un autre EXE.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`set_unexpected`|\<eh.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de gestion des exceptions](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [_get_unexpected](../../c-runtime-library/reference/get-unexpected.md)   
 [set_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)