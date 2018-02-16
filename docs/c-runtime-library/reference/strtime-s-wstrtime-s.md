---
title: _strtime_s, _wstrtime_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _wstrtime_s
- _strtime_s
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
- _wstrtime_s
- strtime_s
- wstrtime_s
- _strtime_s
dev_langs:
- C++
helpviewer_keywords:
- wstrtime_s function
- copying time to buffers
- strtime_s function
- _wstrtime_s function
- time, copying
- _strtime_s function
ms.assetid: 42acf013-c334-485d-b610-84c0af8a46ec
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c93a98d7be13b19357b1308183519650411ec775
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="strtimes-wstrtimes"></a>_strtime_s, _wstrtime_s
Copient l’heure actuelle dans une mémoire tampon. Ces versions de [_strtime, _wstrtime](../../c-runtime-library/reference/strtime-wstrtime.md) intègrent les améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t _strtime_s(  
   char *buffer,  
   size_t numberOfElements  
);  
errno_t _wstrtime_s(  
   wchar_t *buffer,  
   size_t numberOfElements  
);  
template <size_t size>  
errno_t _strtime_s(  
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
errno_t _wstrtime_s(  
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Paramètres  
 [out] `buffer`  
 Mémoire tampon, d’une longueur d’au moins 10 octets, dans laquelle l’heure doit être écrite.  
  
 [in] `numberOfElements`  
 Taille de la mémoire tampon.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro si l’opération aboutit.  
  
 Si une condition d’erreur se présente, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). En cas d’échec, la valeur de retour est un code d’erreur. Les codes d’erreur sont définis dans ERRNO.H. Consultez le tableau suivant pour en savoir plus sur les erreurs générées exactement par cette fonction. Pour plus d’informations sur les codes d’erreur, consultez [errno, constantes](../../c-runtime-library/errno-constants.md).  
  
### <a name="error-conditions"></a>Conditions d’erreur  
  
|`buffer`|`numberOfElements`|Retourner|Contenu de `buffer`|  
|--------------|------------------------|------------|--------------------------|  
|`NULL`|(indifférent)|`EINVAL`|Non modifié|  
|Non `NULL` (pointant vers la mémoire tampon valide)|0|`EINVAL`|Non modifiée|  
|Non `NULL` (pointant vers la mémoire tampon valide)|0 < taille < 9|`EINVAL`|Chaîne vide|  
|Non `NULL` (pointant vers la mémoire tampon valide)|Taille > 9|0|Heure actuelle au format spécifié dans la section Notes|  
  
## <a name="security-issues"></a>Problèmes de sécurité  
 La transmission d’une valeur non NULL non valide pour la mémoire tampon entraîne une violation d’accès si le paramètre `numberOfElements` a une valeur supérieure à 9.  
  
 La transmission d’une valeur pour `numberOfElements` qui est supérieure à la taille réelle de la mémoire tampon occasionne un dépassement de la mémoire tampon.  
  
## <a name="remarks"></a>Notes  
 Ces fonctions offrent des versions plus sécurisées de `_strtime` et `_wstrtime`. Le `_strtime_s` fonction copie l’heure locale actuelle dans la mémoire tampon pointée par `timestr`. L’heure se présente sous la forme `hh:mm:ss`. `hh` correspond à deux chiffres qui représentent l’heure au format 24 heures, `mm` correspond à deux chiffres qui représentent les minutes, et `ss` correspond à deux chiffres qui représentent les secondes. Par exemple, la chaîne `18:23:44` représente 18 heures passé de 23 minutes et 44 secondes. La mémoire tampon doit avoir une longueur au moins égale à 9 octets. La taille réelle est spécifiée par le deuxième paramètre.  
  
 `_wstrtime` est une version à caractères larges de `_strtime` ; l'argument et la valeur de retour de `_wstrtime` sont des chaînes à caractères larges. Ces fonctions se comportent sinon de façon identique.  
  
 En C++, l’utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement (ce qui évite d’avoir à spécifier un argument taille) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalentes plus récentes et sécurisées. Pour plus d'informations, consultez [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mapping"></a>Mappage de routines de texte générique :  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tstrtime_s`|`_strtime_s`|`_strtime_s`|`_wstrtime_s`|  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_strtime_s`|\<time.h>|  
|`_wstrtime_s`|\<time.h> ou \<wchar.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// strtime_s.c  
  
#include <time.h>  
#include <stdio.h>  
  
int main()  
{  
    char tmpbuf[9];  
    errno_t err;  
  
    // Set time zone from TZ environment variable. If TZ is not set,  
    // the operating system is queried to obtain the default value   
    // for the variable.   
    //  
    _tzset();  
  
    // Display operating system-style date and time.   
    err = _strtime_s( tmpbuf, 9 );  
    if (err)  
    {  
       printf("_strdate_s failed due to an invalid argument.");  
      exit(1);  
    }  
    printf( "OS time:\t\t\t\t%s\n", tmpbuf );  
    err = _strdate_s( tmpbuf, 9 );  
    if (err)  
    {  
       printf("_strdate_s failed due to an invalid argument.");  
       exit(1);  
    }  
    printf( "OS date:\t\t\t\t%s\n", tmpbuf );  
  
}  
```  
  
```Output  
OS time:            14:37:49  
OS date:            04/25/03  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [mktime, _mktime32, _mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)