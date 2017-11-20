---
title: strerror_s, _strerror_s, _wcserror_s, __wcserror_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __wcserror_s
- _strerror_s
- _wcserror_s
- strerror_s
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
- wcserror_s
- __wcserror_s
- _tcserror_s
- _wcserror_s
- tcserror_s
- strerror_s
- _strerror_s
dev_langs: C++
helpviewer_keywords:
- __wcserror_s function
- error messages, printing
- tcserror_s function
- printing error messages
- strerror_s function
- _wcserror_s function
- _tcserror_s function
- _strerror_s function
- wcserror_s function
- error messages, getting
ms.assetid: 9e5b15a0-efe1-4586-b7e3-e1d7c31a03d6
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d14c4fd98a9191e8a92d3f24dc24c19de2433e15
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="strerrors-strerrors-wcserrors-wcserrors"></a>strerror_s, _strerror_s, _wcserror_s, __wcserror_s
Obtiennent un message d’erreur système (`strerror_s`, `_wcserror_s`) ou impriment un message d’erreur fourni par l’utilisateur (`_strerror_s`, `__wcserror_s`). Ces versions de [strerror, _strerror, _wcserror, \__wcserror](../../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md) intègrent les améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t strerror_s(  
   char *buffer,  
   size_t numberOfElements,  
   int errnum   
);  
errno_t _strerror_s(  
   char *buffer,  
   size_t numberOfElements,  
   const char *strErrMsg   
);  
errno_t _wcserror_s(  
   wchar_t *buffer,  
   size_t numberOfElements,  
   int errnum   
);  
errno_t __wcserror_s(  
   wchar_t *buffer,  
   size_t numberOfElements,  
   const wchar_t *strErrMsg   
);  
template <size_t size>  
errno_t strerror_s(  
   char (&buffer)[size],  
   int errnum   
); // C++ only  
template <size_t size>  
errno_t _strerror_s(  
   char (&buffer)[size],  
   const char *strErrMsg   
); // C++ only  
template <size_t size>  
errno_t _wcserror_s(  
   wchar_t (&buffer)[size],  
   int errnum   
); // C++ only  
template <size_t size>  
errno_t __wcserror_s(  
   wchar_t (&buffer)[size],  
   const wchar_t *strErrMsg   
); // C++ only  
```  
  
#### <a name="parameters"></a>Paramètres  
 `buffer`  
 Mémoire tampon devant contenir la chaîne d’erreur.  
  
 `numberOfElements`  
 Taille de la mémoire tampon.  
  
 `errnum`  
 Numéro d'erreur.  
  
 `strErrMsg`  
 Message fourni par l'utilisateur.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro si l'opération a réussi, un code d'erreur en cas d'échec.  
  
### <a name="error-condtions"></a>Conditions d’erreur  
  
|`buffer`|`numberOfElements`|`strErrMsg`|Contenu de `buffer`|  
|--------------|------------------------|-----------------|--------------------------|  
|`NULL`|any|any|N/A|  
|any|0|any|non modifié|  
  
## <a name="remarks"></a>Notes  
 La fonction `strerror_s` mappe `errnum` à une chaîne de message d’erreur, retournant la chaîne contenue dans `buffer`. `_strerror_s` ne prend pas le numéro d’erreur ; elle utilise la valeur actuelle de `errno` pour déterminer le message approprié. Ni `strerror_s` ni `_strerror_s` n’imprime réellement le message : pour cela, vous devez appeler une fonction de sortie telle que [fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md) :  
  
```  
if (( _access( "datafile",2 )) == -1 )  
{  
   _strerror_s(buffer, 80);  
   fprintf( stderr, buffer );  
}  
```  
  
 Si `strErrMsg` a la valeur `NULL`, `_strerror_s` retourne une chaîne de `buffer` contenant le message d’erreur système pour le dernière appel de bibliothèque qui a généré l’erreur. La chaîne de message d'erreur se termine par le caractère de saut de ligne ('\n'). Si `strErrMsg` n’a pas la valeur `NULL`, `_strerror_s` retourne une chaîne de `buffer` contenant (dans l’ordre) votre message de type chaîne, deux-points, un espace, le message d’erreur système pour le dernier appel de bibliothèque ayant généré une erreur, puis un caractère de saut de ligne. La longueur maximale de votre message de type chaîne est de 94 caractères.  
  
 Ces fonctions tronquent le message d’erreur si sa longueur dépasse `numberOfElements` -1. La chaîne obtenue dans `buffer` se termine toujours par un caractère null.  
  
 Le numéro d’erreur effectif pour `_strerror_s` est stocké dans la variable [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Les messages d’erreur système sont accessibles via la variable [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md), qui est un tableau de messages classés par numéro d’erreur. `_strerror_s` accède au message d’erreur approprié en utilisant la valeur `errno` comme index de la variable `_sys_errlist`. La valeur de la variable [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) est définie comme étant le nombre maximal d’éléments contenus dans le tableau `_sys_errlist`. Pour générer des résultats précis, appelez `_strerror_s` de suite après le retour avec erreur d'une routine de bibliothèque. Sinon, les appels suivants à `strerror_s` ou `_strerror_s` peuvent remplacer la valeur `errno`.  
  
 `_wcserror_s` et `__wcserror_s` sont, respectivement, des versions à caractères larges de `strerror_s` et `_strerror_s`.  
  
 Ces fonctions valident leurs paramètres. Si la mémoire tampon a la valeur `NULL` ou si le paramètre de taille est égal à 0, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à continuer, les fonctions retournent `EINVAL` et définissent `errno` sur `EINVAL`.  
  
 `_strerror_s`, `_wcserror_s`, et `__wcserror_s` ne font pas partie de la définition ANSI mais sont plutôt des extensions de Microsoft. Ne les utilisez pas si vous avez besoin d’une portabilité ; pour bénéficier d’une compatibilité ANSI, utilisez plutôt `strerror_s`.  
  
 En C++, l’utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire automatiquement la longueur de la mémoire tampon, ce qui évite d’avoir à spécifier un argument de taille. Pour plus d’informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
 Les versions debug de ces fonctions remplissent d'abord la mémoire tampon avec 0xFD. Pour désactiver ce comportement, utilisez [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcserror_s`|`strerror_s`|`strerror_s`|`_wcserror_s`|  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`strerror_s`, `_strerror_s`|\<string.h>|  
|`_wcserror_s`, `__wcserror_s`|\<string.h> ou \<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple relatif à [perror](../../c-runtime-library/reference/perror-wperror.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, _wperror](../../c-runtime-library/reference/perror-wperror.md)