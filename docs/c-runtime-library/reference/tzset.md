---
title: _tzset | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 15464ac8be075d44a9a42223964239538508a683
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="tzset"></a>_tzset

Définit des variables d’environnement de date/heure.

> [!IMPORTANT]
> Cette API ne peut pas être utilisée dans les applications qui s’exécutent dans le Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge dans les applications de la plateforme Windows universelle](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntaxe

```C
void _tzset( void );
```

## <a name="remarks"></a>Notes

Le **_tzset** fonction utilise le paramètre actuel de la variable d’environnement **TZ** pour affecter des valeurs à trois variables globales : **_daylight**, **_timezone** , et **_tzname**. Ces variables sont utilisées par le [_ftime](ftime-ftime32-ftime64.md) et [localtime](localtime-localtime32-localtime64.md) fonctions pour apporter des corrections à partir du temps universel coordonné (UTC) en heure locale et par le [temps](time-time32-time64.md) fonction calculer l’heure UTC à partir de l’heure système. Utilisez la syntaxe suivante pour définir le **TZ** variable d’environnement :

> **définir TZ =**_tzn_ \[ **+** &#124; **-**]*hh* \[ **:**_mm_\[**:**_ss_]] [*dzn*]

|Paramètre|Description|
|-|-|
*tzn*|Nom du fuseau horaire en trois lettres, comme PST. Vous devez spécifier le décalage correct de l’heure locale à l’heure UTC.
*hh*|Différence en heures entre l’heure UTC et l’heure locale. Signe (+) facultatif pour les valeurs positives.
*mm*|Minutes. Séparé de *hh* par un signe deux-points (**:**).
*ss*|Secondes. Séparé de *mm* par un signe deux-points (**:**).
*dzn*|Fuseau horaire de l’heure d’été en trois lettres, comme PDT. Si l’heure d’été n’est jamais en vigueur dans la localité, définissez **TZ** sans valeur pour *dzn*. La bibliothèque runtime C suppose que les règles de calcul de l’heure d’été sont celles des États-Unis.

> [!NOTE]
> Soyez attentif au calcul du signe de la différence d’heure. Comme la différence d’heure est le décalage de l’heure locale avec l’heure UTC (plutôt que l’inverse), son signe peut être l’opposé de ce que vous attendez de façon intuitive. Pour les fuseaux horaires en avance sur l’heure UTC, la différence de temps est négative ; pour ceux qui sont en retard sur l’heure UTC, la différence est positive.

Par exemple, pour définir le **TZ** variable d’environnement pour qu’il corresponde au fuseau horaire actuel en Allemagne, entrez les informations suivantes sur la ligne de commande :

> **définir TZ = TPS-1GDT**

Cette commande utilise GST pour indiquer l’heure standard allemande, suppose que l’heure UTC est en retard d’une heure sur l’Allemagne (ou autrement dit, que l’Allemagne est en avance d’une heure sur l’heure UTC) et suppose qu’Allemagne observe l’heure d’été.

Si le **TZ** valeur n’est pas définie, **_tzset** tente d’utiliser les informations de fuseau horaire spécifiées par le système d’exploitation. Dans le système d’exploitation Windows, ces informations sont spécifiées dans l’application Date et heure du Panneau de configuration. Si **_tzset** ne peut pas obtenir cette information, elle utilise PST8PDT par défaut, ce qui signifie le fuseau horaire Pacifique.

Selon le **TZ** valeur variable d’environnement, les valeurs suivantes sont affectées aux variables globales **_daylight**, **_timezone**, et **_tzname** lorsque **_tzset** est appelée :

|Variable globale|Description|Valeur par défaut|
|---------------------|-----------------|-------------------|
|**_daylight**|Une valeur différente de zéro si le fuseau horaire de l’heure d’été est spécifié dans **TZ** configuration ; sinon, 0.|1|
|**_timezone**|Différence en secondes entre l’heure locale et l’heure UTC.|28 800 (28 800 secondes est égal à 8 heures)|
|**_tzname**[0]|Valeur de chaîne de nom du fuseau horaire à partir de **TZ** variable d’environnement ; vide si **TZ** n’a pas été définie.|PST|
|**_tzname**[1]|Valeur de chaîne de la zone de l’heure d’été ; vide si le fuseau horaire de l’enregistrement de l’heure d’été est omis de **TZ** variable d’environnement.|PDT|

Les valeurs par défaut indiqués dans le tableau précédent pour **_daylight** et **_tzname** tableau correspondent à « PST8PDT ». Si le fuseau horaire DST est omis à partir de la **TZ** variable d’environnement, la valeur de **_daylight** est égal à 0 et la [_ftime](ftime-ftime32-ftime64.md), [gmtime](gmtime-gmtime32-gmtime64.md)et [localtime](localtime-localtime32-localtime64.md) fonctions retournent 0 pour les indicateurs DST.

## <a name="requirements"></a>Spécifications

|Routine|En-tête requis|
|-------------|---------------------|
|**_tzset**|\<time.h>|

Le **_tzset** fonction est spécifique à Microsoft. Pour plus d'informations, voir [Compatibilité](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Exemple

```C
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

## <a name="see-also"></a>Voir aussi

[Gestion du temps](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](utime-utime32-utime64-wutime-wutime32-wutime64.md)<br/>
