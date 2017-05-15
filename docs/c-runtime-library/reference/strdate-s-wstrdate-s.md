---
title: _strdate_s, _wstrdate_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _strdate_s
- _wstrdate_s
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _strdate_s
- wstrdate_s
- _wstrdate_s
- strdate_s
- _tstrdate_s
dev_langs:
- C++
helpviewer_keywords:
- dates, copying
- tstrdate_s function
- wstrdate_s function
- _tstrdate_s function
- strdate_s function
- copying dates
- _strdate_s function
- _wstrdate_s function
ms.assetid: d41d8ea9-e5ce-40d4-864e-1ac29b455991
caps.latest.revision: 24
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
ms.openlocfilehash: 5b1701f41b2f66ccbc2601763c09a4db0523c2ed
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="strdates-wstrdates"></a>_strdate_s, _wstrdate_s
Copient la date système actuelle dans une mémoire tampon. Ces versions de [_strdate, _wstrdate](../../c-runtime-library/reference/strdate-wstrdate.md) intègrent les améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t _strdate_s(  
   char *buffer,  
   size_t numberOfElements  
);  
errno_t _wstrdate_s(  
   wchar_t *buffer,  
   size_t numberOfElements  
);  
template <size_t size>  
errno_t _strdate_s(  
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
errno_t _wstrdate_s(  
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Paramètres  
 [out] `buffer`  
 Pointeur désignant une mémoire tampon qui sera remplie avec la chaîne de date mise en forme.  
  
 [in] `numberOfElements`  
 Taille de la mémoire tampon.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro si l’opération réussit. En cas d’échec, la valeur de retour est un code d’erreur. Les codes d’erreur sont définis dans ERRNO.H. Consultez le tableau ci-dessous pour en savoir plus sur les erreurs générées exactement par cette fonction. Pour plus d’informations sur les codes d’erreur, consultez [errno](../../c-runtime-library/errno-constants.md).  
  
## <a name="error-conditions"></a>Conditions d’erreur  
  
|`buffer`|`numberOfElements`|Retourner|Contenu de `buffer`|  
|--------------|------------------------|------------|--------------------------|  
|`NULL`|(indifférent)|`EINVAL`|Non modifié|  
|Non `NULL` (pointant vers la mémoire tampon valide)|0|`EINVAL`|Non modifié|  
|Non `NULL` (pointant vers la mémoire tampon valide)|0 < `numberOfElements` < 9|`EINVAL`|Chaîne vide|  
|Non `NULL` (pointant vers la mémoire tampon valide)|`numberOfElements` >= 9|0|Date actuelle au format spécifié dans la section Notes|  
  
## <a name="security-issues"></a>Problèmes de sécurité  
 La transmission d’une valeur non `NULL` non valide pour la mémoire tampon entraîne une violation d’accès si le paramètre `numberOfElements` a une valeur supérieure à 9.  
  
 La transmission d’une valeur de taille supérieure à la taille réelle de `buffer` entraîne un dépassement de la mémoire tampon.  
  
## <a name="remarks"></a>Notes  
 Ces fonctions offrent des versions plus sécurisées de `_strdate` et `_wstrdate`. La fonction `_strdate_s` copie la date système actuelle dans la mémoire tampon désignée par `buffer`, dans le format `mm`/`dd`/`yy`, les deux chiffres représentés par `mm` correspondant au mois, ceux de `dd` au jour, et ceux de `yy` à l’année. Par exemple, la chaîne `12/05/99` représente le 5 décembre 1999. La chaîne doit comporter au moins 9 caractères.  
  
 `_wstrdate_s` est une version à caractères larges de `_strdate_s` ; l'argument et la valeur de retour de `_wstrdate_s` sont des chaînes à caractères larges. Ces fonctions se comportent sinon de façon identique.  
  
 Si `buffer` est un pointeur `NULL` ou si `numberOfElements` a une valeur inférieure à 9 caractères, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, ces fonctions retournent -1 et affectent à `errno` la valeur `EINVAL` si la mémoire tampon a la valeur `NULL` ou si `numberOfElements` a une valeur inférieure ou égale à 0, ou elles affectent à `errno` la valeur `ERANGE` si `numberOfElements` a une valeur inférieure à 9.  
  
 En C++, l’utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement (ce qui évite d’avoir à spécifier un argument taille) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalentes plus récentes et sécurisées. Pour plus d’informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mapping"></a>Mappage de routines de texte générique :  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tstrdate_s`|`_strdate_s`|`_strdate_s`|`_wstrdate_s`|  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_strdate`|\<time.h>|  
|`_wstrdate`|\<time.h> ou \<wchar.h>|  
|`_strdate_s`|\<time.h>|  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple relatif à [time](../../c-runtime-library/reference/time-time32-time64.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [mktime, _mktime32, _mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)
