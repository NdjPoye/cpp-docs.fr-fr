---
title: _strtime, _wstrtime | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wstrtime
- _strtime
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
- _wstrtime
- _strtime
- wstrtime
- strtime
- _tstrtime
dev_langs: C++
helpviewer_keywords:
- strtime function
- _strtime function
- _wstrtime function
- copying time to buffers
- wstrtime function
- tstrtime function
- _tstrtime function
- time, copying
ms.assetid: 9e538161-cf49-44ec-bca5-c0ab0b9e4ca3
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 112e5b6c29f73cb162a1d417fb23842fafc80ff9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="strtime-wstrtime"></a>_strtime, _wstrtime
Copient l’heure dans une mémoire tampon. Il existe des versions plus sécurisées de ces fonctions. Consultez [_strtime_s, _wstrtime_s](../../c-runtime-library/reference/strtime-s-wstrtime-s.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
char *_strtime(  
   char *timestr   
);  
wchar_t *_wstrtime(  
   wchar_t *timestr   
);  
template <size_t size>  
char *_strtime(  
   char (&timestr)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_wstrtime(  
   wchar_t (&timestr)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Paramètres  
 `timestr`  
 Chaîne d’heure.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur désignant la chaîne de caractères `timestr` obtenue.  
  
## <a name="remarks"></a>Notes  
 Le `_strtime` fonction copie l’heure locale actuelle dans la mémoire tampon pointée par `timestr`. L’heure se présente sous la forme `hh:mm:ss`. `hh` correspond à deux chiffres qui représentent l’heure au format 24 heures, `mm` correspond à deux chiffres qui représentent les minutes, et `ss` correspond à deux chiffres qui représentent les secondes. Par exemple, la chaîne `18:23:44` représente 18 heures passé de 23 minutes et 44 secondes. La mémoire tampon doit avoir une longueur au moins égale à 9 octets.  
  
 `_wstrtime` est une version à caractères larges de `_strtime` ; l'argument et la valeur de retour de `_wstrtime` sont des chaînes à caractères larges. Sinon, ces fonctions se comportent de la même manière. Si `timestr` est un pointeur `NULL` ou si le format de `timestr` est incorrect, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exception est autorisée à se poursuivre, ces fonctions retournent une valeur NULL et affectent à `errno` la valeur `EINVAL` si `timestr` avait la valeur NULL, ou affectent à `errno` la valeur `ERANGE` si le format de `timestr` était incorrect.  
  
 En C++, ces fonctions ont des surcharges de modèle qui appellent les équivalents plus récents et sécurisés de ces fonctions. Pour plus d'informations, consultez [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tstrtime`|`_strtime`|`_strtime`|`_wstrtime`|  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_strtime`|\<time.h>|  
|`_wstrtime`|\<time.h> ou \<wchar.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_strtime.c  
// compile with: /W3  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char tbuffer [9];  
   _strtime( tbuffer ); // C4996  
   // Note: _strtime is deprecated; consider using _strtime_s instead  
   printf( "The current time is %s \n", tbuffer );  
}  
```  
  
```Output  
The current time is 14:21:44  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [mktime, _mktime32, _mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)