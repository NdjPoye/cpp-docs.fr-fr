---
title: _invalid_parameter, _invalid_parameter_noinfo, _invalid_parameter_noinfo_noreturn, _invoke_watson | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _invalid_parameter
- _invalid_parameter_noinfo
- _invalid_parameter_noinfo_noreturn
- _invoke_watson
apilocation: api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- CORECRT/_invalid_parameter
- _invalid_parameter
- CORECRT/_invalid_parameter_noinfo
- _invalid_parameter_noinfo
- CORECRT/_invalid_parameter_noinfo_noreturn
- _invalid_parameter_noinfo_noreturn
- CORECRT/_invoke_watson
- _invoke_watson
ms.assetid: a4d6f1fd-ce56-4783-8719-927151a7a814
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 49ae87567cd311e271a0ab50d7112a4a8f0c1b4a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="invalidparameter-invalidparameternoinfo-invalidparameternoinfonoreturn-invokewatson"></a>_invalid_parameter, _invalid_parameter_noinfo, _invalid_parameter_noinfo_noreturn, _invoke_watson
Ces fonctions sont utilisées par la bibliothèque Runtime C pour gérer les paramètres non valides transmis aux fonctions de la bibliothèque CRT. Votre code peut également utiliser ces fonctions pour prendre en charge la gestion personnalisable ou par défaut des paramètres non valides.

## <a name="syntax"></a>Syntaxe
```
extern "C" void __cdecl 
_invalid_parameter(
    wchar_t const* const expression,
    wchar_t const* const function_name,
    wchar_t const* const file_name,
    unsigned int   const line_number,
    uintptr_t      const reserved);  

extern "C" void __cdecl 
_invalid_parameter_noinfo(void);  

extern "C" __declspec(noreturn) void __cdecl 
_invalid_parameter_noinfo_noreturn(void);  

extern "C" __declspec(noreturn) void __cdecl 
_invoke_watson(  
    wchar_t const* const expression,
    wchar_t const* const function_name,
    wchar_t const* const file_name,
    unsigned int   const line_number,
    uintptr_t      const reserved);
```

## <a name="return-value"></a>Valeur de retour
Ces fonctions ne retournent pas de valeur. Les fonctions `_invalid_parameter_noinfo_noreturn` et `_invoke_watson` ne retournent pas le contrôle à l’appelant et, dans certains cas, il peut en aller de même pour `_invalid_parameter` et `_invalid_parameter_noinfo`.

## <a name="parameters"></a>Paramètres
`expression`  
Chaîne représentant l’expression de paramètre de code source qui n’est pas valide.

`function_name`  
Nom de la fonction qui a appelé le gestionnaire.

`file_name`  
Fichier de code source dans lequel le gestionnaire a été appelé.

`line_number`  
Numéro de ligne dans le code source où le gestionnaire a été appelé.

`reserved`  
Non utilisé.

## <a name="remarks"></a>Notes
Quand des paramètres non valides sont passés aux fonctions de la bibliothèque runtime C, celles-ci appellent un *gestionnaire de paramètres non valides*, fonction qui peut être spécifiée par le programmeur pour effectuer plusieurs actions. Par exemple, il peut signaler le problème à l’utilisateur, écrire dans un journal, marquer un arrêt dans un débogueur, mettre fin au programme ou ne rien faire du tout. Si aucune fonction n’est spécifiée par le programmeur, un gestionnaire par défaut, `_invoke_watson`, est appelé.

Par défaut, quand un paramètre non valide est identifié dans un code de débogage, les fonctions de la bibliothèque CRT appellent la fonction `_invalid_parameter` à l’aide de paramètres détaillés. Dans un code sans débogage, la fonction `_invalid_parameter_noinfo` est appelée, entraînant l’appel de la fonction `_invalid_parameter` à l’aide de paramètres vides. Si la fonction de bibliothèque CRT sans débogage nécessite l’arrêt du programme, la fonction `_invalid_parameter_noinfo_noreturn` est appelée, entraînant l’appel de la fonction `_invalid_parameter` à l’aide de paramètres vides, suivi d’un appel de la fonction `_invoke_watson` pour forcer l’arrêt du programme.

La fonction `_invalid_parameter` vérifie si un gestionnaire de paramètres non valides défini par l’utilisateur a été défini et, si tel est le cas, elle l’appelle. Par exemple, si un gestionnaire de thread local défini par l’utilisateur a été défini par un appel à [set_thread_local_invalid_parameter_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) dans le thread actuel, il est appelé, puis la fonction retourne le contrôle. Sinon, si un gestionnaire de paramètres non valides global défini par l’utilisateur a été défini par un appel à [set_invalid_parameter_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md), il est appelé, puis la fonction retourne le contrôle. Sinon, le gestionnaire par défaut `_invoke_watson` est appelé. Le comportement par défaut de `_invoke_watson` consiste à arrêter le programme. Les gestionnaires définis par l’utilisateur peuvent arrêter le programme ou retourner le contrôle. Il est recommandé que les gestionnaires définis par l’utilisateur terminent le programme, sauf si la récupération est certaine. 

Quand le gestionnaire par défaut `_invoke_watson` est appelé, si le processeur prend en charge une opération [__fastfail](../../intrinsics/fastfail.md), il est appelé à l’aide d’un paramètre de `FAST_FAIL_INVALID_ARG` et le processus se termine. Sinon, une exception d’échec rapide est déclenchée, qui peut être interceptée par un débogueur attaché. Si le processus est autorisé à se poursuivre, il est arrêtée par un appel à la fonction Windows `TerminateProcess` à l’aide d’un état de code d’exception de `STATUS_INVALID_CRUNTIME_PARAMETER`. 

## <a name="requirements"></a>Spécifications  
|Fonction|En-tête requis|  
|--------------|------------------|  
|`_invalid_parameter`, `_invalid_parameter_noinfo`, `_invalid_parameter_noinfo_noreturn`, `_invoke_watson`|\<corecrt.h>|  
  
 Pour plus d’informations sur la compatibilité, voir consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler](../../c-runtime-library/reference/get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)  
 [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)  
 [Validation de paramètre](../../c-runtime-library/parameter-validation.md)
