---
title: ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ctime64
- _wctime32
- ctime
- _wctime64
- _ctime32
- _wctime
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
- _wctime64
- _ctime32
- _tctime
- _wctime
- _wctime32
- _tctime64
- _ctime64
- ctime
dev_langs:
- C++
helpviewer_keywords:
- tctime64 function
- _ctime32 function
- ctime32 function
- _wctime function
- wctime64 function
- _tctime64 function
- _tctime32 function
- _ctime64 function
- _wctime64 function
- ctime function
- wctime32 function
- ctime64 function
- _wctime32 function
- _tctime function
- tctime32 function
- tctime function
- wctime function
- time, converting
ms.assetid: 2423de37-a35c-4f0a-a378-3116bc120a9d
caps.latest.revision: 25
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: f3d756cec6d9482cfabcbc2a336cbf5d6381a97a
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="ctime-ctime32-ctime64-wctime-wctime32-wctime64"></a>ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64
Convertissent une valeur de temps en une chaîne et ajustent les paramètres de fuseau horaire local. Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
char *ctime(   
   const time_t *timer   
);  
char *_ctime32(   
   const __time32_t *timer )  
;  
char *_ctime64(   
   const __time64_t *timer )  
;  
wchar_t *_wctime(   
   const time_t *timer   
);  
wchar_t *_wctime32(   
   const __time32_t *timer  
);  
wchar_t *_wctime64(   
   const __time64_t *timer   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `timer`  
 Pointeur désignant la valeur de temps stockée.  
  
## <a name="return-value"></a>Valeur de retour  
 Pointeur désignant le résultat de chaîne de caractères. `NULL` est retourné si :  
  
-   `time` représente une date antérieure au 1er janvier 1970 à minuit, UTC ;  
  
-   si vous utilisez `_ctime32` ou `_wctime32` et que `time` représente une date postérieure au 18 janvier 2038 à 23:59:59, heure UTC ;  
  
-   si vous utilisez `_ctime64` ou `_wctime64` et que `time` représente une date postérieure au 31 décembre 3000 à 23:59:59, heure UTC.  
  
 `ctime` est une fonction inline qui prend la valeur `_ctime64`, tandis que `time_t` équivaut à `__time64_t`. Si vous devez forcer le compilateur à interpréter `time_t` comme l’ancien `time_t` 32 bits, vous pouvez définir `_USE_32BIT_TIME_T`. Ainsi, `ctime` prend la valeur `_ctime32`. Cela n’est pas recommandé, car votre application peut échouer après le 18 janvier 2038 et cela n’est pas autorisé sur les plateformes 64 bits.  
  
## <a name="remarks"></a>Notes  
 La fonction `ctime` convertit une valeur de temps stockée en tant que valeur [time_t](../../c-runtime-library/standard-types.md) en une chaîne de caractères. La valeur `timer` est généralement obtenue à partir d’un appel à [time](../../c-runtime-library/reference/time-time32-time64.md), qui retourne le nombre de secondes écoulées depuis minuit (00:00:00), le 1er janvier 1970, temps universel coordonné (UTC). La chaîne de valeur de retour contient exactement 26 caractères et présente la forme suivante :  
  
```  
Wed Jan 02 02:03:55 1980\n\0  
```  
  
 Une horloge de 24 heures est utilisée. Tous les champs ont une largeur constante. Le caractère de saut de ligne (« \n ») et le caractère null (« \0 ») occupent les deux dernières positions de la chaîne.  
  
 La chaîne de caractères convertie est également ajustée en fonction des paramètres de fuseau horaire local. Consultez les fonctions `time`, [_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) et [localtime](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) pour plus d’informations sur la configuration de l’heure locale, et la fonction [_tzset](../../c-runtime-library/reference/tzset.md) pour plus de détails sur la définition des variables globales et d’environnement des fuseaux horaires.  
  
 Un appel à `ctime` modifie la mémoire tampon unique allouée de manière statique qu’utilisent les fonctions `gmtime` et `localtime`. Chaque appel à une de ces routines détruit le résultat de l’appel précédent. `ctime` partage une mémoire tampon statique avec la fonction `asctime`. Ainsi, un appel à `ctime` détruit les résultats d’un appel précédent à `asctime`, `localtime` ou `gmtime`.  
  
 `_wctime` et `_wctime64` sont la version à caractères larges de `ctime` et `_ctime64` ; ils retournent un pointeur désignant une chaîne à caractères larges. Sinon, `_ctime64`, `_wctime` et `_wctime64` se comportent de la même façon que `ctime`.  
  
 Ces fonctions valident leurs paramètres. Si `timer` est un pointeur null ou que la valeur d’horloge est négative, ces fonctions appellent le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à continuer, les fonctions retournent `NULL` et définissent `errno` sur `EINVAL`.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tctime`|`ctime`|`ctime`|`_wctime`|  
|`_tctime32`|`_ctime32`|`_ctime32`|`_wctime32`|  
|`_tctime64`|`_ctime64`|`_ctime64`|`_wctime64`|  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`ctime`|\<time.h>|  
|`_ctime32`|\<time.h>|  
|`_ctime64`|\<time.h>|  
|`_wctime`|\<time.h> ou \<wchar.h>|  
|`_wctime32`|\<time.h> ou \<wchar.h>|  
|`_wctime64`|\<time.h> ou \<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_ctime64.c  
// compile with: /W3  
/* This program gets the current  
 * time in _time64_t form, then uses ctime to  
 * display the time in string form.  
 */  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   __time64_t ltime;  
  
   _time64( &ltime );  
   printf( "The time is %s\n", _ctime64( &ltime ) ); // C4996  
   // Note: _ctime64 is deprecated; consider using _ctime64_s  
}  
```  
  
```Output  
The time is Wed Feb 13 16:04:43 2002  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)
