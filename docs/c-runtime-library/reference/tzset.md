---
title: _tzset | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _tzset
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
- _tzset
dev_langs:
- C++
helpviewer_keywords:
- _tzset function
- time environment variables
- environment variables, setting time
ms.assetid: 3f6ed537-b414-444d-b272-5dd377481930
caps.latest.revision: 23
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: d52530de55147945f12f664d882ce0cda18f8e17
ms.lasthandoff: 02/24/2017

---
# <a name="tzset"></a>_tzset
Définit des variables d’environnement de date/heure.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s’exécutent dans le Windows Runtime. Pour plus d’informations, consultez                  [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void _tzset( void );  
```  
  
## <a name="remarks"></a>Notes  
 La fonction `_tzset` utilise le paramètre actuel de la variable d’environnement `TZ` pour affecter des valeurs à trois variables globales : `_daylight`, `_timezone`et `_tzname`. Ces variables sont utilisées par les fonctions [_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) et [localtime](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) pour apporter des corrections à l’heure locale à partir du temps universel coordonné (UTC) et par la fonction `time` pour calculer l’heure UTC à partir de l’heure système. Utilisez la syntaxe suivante pour définir la variable d’environnement `TZ` :  
  
 `set` `TZ`=`tzn`[+ &#124; –]`hh`[`:``mm`[`:``ss`] ][`dzn`]  
  
 `tzn`  
 Nom du fuseau horaire en trois lettres, comme PST. Vous devez spécifier le décalage correct de l’heure locale à l’heure UTC.  
  
 `hh`  
 Différence en heures entre l’heure UTC et l’heure locale. Signe (+) facultatif pour les valeurs positives.  
  
 `mm`  
 Minutes. Séparé de `hh` par un signe deux-points (`:`).  
  
 `ss`  
 Secondes. Séparé de `mm` par un signe deux-points (`:`).  
  
 `dzn`  
 Fuseau horaire de l’heure d’été en trois lettres, comme PDT. Si l’heure d’été n’est jamais en vigueur dans la localité, définissez `TZ` sans valeur pour `dzn`. La bibliothèque runtime C suppose que les règles de calcul de l’heure d’été sont celles des États-Unis.  
  
> [!NOTE]
>  Soyez attentif au calcul du signe de la différence d’heure. Comme la différence d’heure est le décalage de l’heure locale avec l’heure UTC (plutôt que l’inverse), son signe peut être l’opposé de ce que vous attendez de façon intuitive. Pour les fuseaux horaires en avance sur l’heure UTC, la différence de temps est négative ; pour ceux qui sont en retard sur l’heure UTC, la différence est positive.  
  
 Par exemple, pour définir la variable d’environnement `TZ` pour correspondre au fuseau horaire actuel en Allemagne, entrez ceci sur la ligne de commande :  
  
```  
set TZ=GST-1GDT  
```  
  
 Cette commande utilise GST pour indiquer l’heure standard allemande, suppose que l’heure UTC est en retard d’une heure sur l’Allemagne (ou autrement dit, que l’Allemagne est en avance d’une heure sur l’heure UTC) et suppose qu’Allemagne observe l’heure d’été.  
  
 Si la valeur de `TZ` n’est pas définie, _`tzset` tente d’utiliser les informations de fuseau horaire spécifiées par le système d’exploitation. Dans le système d’exploitation Windows, ces informations sont spécifiées dans l’application Date et heure du Panneau de configuration. Si `_tzset` ne peut pas obtenir ces informations, elle utilise PST8PDT par défaut, ce qui signifie le fuseau horaire Pacifique.  
  
 Selon la valeur de la variable d’environnement `TZ` , les valeurs suivantes sont affectées aux variables globales `_daylight`, `_timezone`et `_tzname` quand `_tzset` est appelée :  
  
|Variable globale|Description|Valeur par défaut|  
|---------------------|-----------------|-------------------|  
|`_daylight`|Une valeur différente de zéro si le fuseau horaire de l’heure d’été est spécifié dans le paramètre `TZ` ; sinon, 0.|1|  
|`_timezone`|Différence en secondes entre l’heure locale et l’heure UTC.|28 800 (28 800 secondes est égal à 8 heures)|  
|`_tzname`[0]|Valeur de chaîne du nom du fuseau horaire provenant de la variable d’environnement `TZ` ; vide si `TZ` n’a pas été définie.|PST|  
|`_tzname`[1]|Valeur de chaîne du fuseau horaire de l’heure d’été ; vide si le fuseau horaire de l’heure d’été est omis dans la variable d’environnement `TZ` .|PDT|  
  
 Les valeurs par défaut indiquées dans le tableau précédent pour `_daylight` et le tableau `_tzname` correspondent à « PST8PDT ». Si le fuseau horaire DST est omis de la variable d’environnement `TZ` , la valeur de `_daylight` est 0 et les fonctions `_ftime`, `gmtime`et `localtime` retournent 0 pour les indicateurs DST.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_tzset`|\<time.h>|  
  
 Pour plus d’informations, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_tzset.cpp  
// This program uses _tzset to set the global variables  
// named _daylight, _timezone, and _tzname. Since TZ is  
// not being explicitly set, it uses the system time.  
  
#include <time.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
    _tzset();  
    int daylight;  
    _get_daylight( &daylight );  
    printf( "_daylight = %d\n", daylight );  
    long timezone;  
    _get_timezone( &timezone );  
    printf( "_timezone = %ld\n", timezone );  
    size_t s;  
    char tzname[100];  
    _get_tzname( &s, tzname, sizeof(tzname), 0 );  
    printf( "_tzname[0] = %s\n", tzname );  
    exit( 0 );  
}  
```  
  
```Output  
_daylight = 1  
_timezone = 28800  
_tzname[0] = Pacific Standard Time  
```  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](../../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)
