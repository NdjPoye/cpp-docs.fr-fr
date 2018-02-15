---
title: asctime_s, _wasctime_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _wasctime_s
- asctime_s
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
- asctime_s
- _wasctime_s
- _tasctime_s
dev_langs:
- C++
helpviewer_keywords:
- tasctime_s function
- _tasctime_s function
- time structure conversion
- wasctime_s function
- time, converting
- _wasctime_s function
- asctime_s function
ms.assetid: 17ad9b2b-a459-465d-976a-42822897688a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6914dd9c305a1313cde43e69f012786462f1d4a6
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="asctimes-wasctimes"></a>asctime_s, _wasctime_s
Convertissent une structure de temps `tm` en une chaîne de caractères. Ces fonctions sont des versions de [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md) assortie des améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t asctime_s(   
   char* buffer,  
   size_t numberOfElements,  
   const struct tm *_tm   
);  
errno_t _wasctime_s(   
   wchar_t* buffer,  
   size_t numberOfElements  
   const struct tm *_tm   
);  
template <size_t size>  
errno_t asctime_s(   
   char (&buffer)[size],  
   const struct tm *_tm   
); // C++ only  
template <size_t size>  
errno_t _wasctime_s(   
   wchar_t (&buffer)[size],  
   const struct tm *_tm   
); // C++ only  
```  
  
#### <a name="parameters"></a>Paramètres  
 `buffer`  
 [out] Pointeur désignant une mémoire tampon pour stocker le résultat de chaîne de caractères. Ce pointeur est supposé désigner un emplacement de mémoire valide dont la taille est spécifiée par `numberOfElements`.  
  
 `numberOfElements`  
 [in] Taille de la mémoire tampon utilisée pour stocker le résultat.  
  
 `_tm`  
 [in] Structure date/heure. Cette fonction suppose un pointeur désignant un objet `struct tm` valide.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro si l’opération réussit. En cas d’échec, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, la valeur de retour est un code d’erreur. Les codes d’erreur sont définis dans ERRNO.H. Pour plus d’informations, consultez [Constantes errno](../../c-runtime-library/errno-constants.md). Les codes d’erreur retournés pour chaque condition d’erreur sont répertoriés dans le tableau suivant.  
  
### <a name="error-conditions"></a>Conditions d’erreur  
  
|`buffer`|`numberOfElements`|`tm`|Retourner|Valeur dans `buffer`|  
|--------------|------------------------|----------|------------|-----------------------|  
|`NULL`|Any|Any|`EINVAL`|Non modifiée|  
|Pas `NULL` (pointe vers une mémoire valide)|0|Any|`EINVAL`|Non modifiée|  
|Pas `NULL`|0 < taille < 26|Any|`EINVAL`|Chaîne vide|  
|Pas `NULL`|>= 26|`NULL`|`EINVAL`|Chaîne vide|  
|Pas `NULL`|>= 26|Structure de temps non valide ou hors de la plage de valeurs pour les composants de temps|`EINVAL`|Chaîne vide|  
  
> [!NOTE]
>  Les conditions d’erreur pour `wasctime_s` sont similaires à `asctime_s`, à la différence que la limite de taille est mesurée en mots.  
  
## <a name="remarks"></a>Notes  
 La fonction `asctime` convertit une valeur de temps stockée en tant que structure en une chaîne de caractères. La valeur `_tm` est généralement obtenue à partir d’un appel à `gmtime` ou `localtime`. Les deux fonctions peuvent être utilisées pour renseigner une structure `tm`, comme défini dans TIME.H.  
  
|Membre de timeptr|Value|  
|--------------------|-----------|  
|`tm_hour`|Heures écoulées depuis minuit (0-23)|  
|`tm_isdst`|Positif si l’heure d’été est en vigueur ; 0 si l’heure d’été n’est pas appliquée ; négatif si l’état de l’heure d’été est inconnu. La bibliothèque runtime C suppose que les règles de calcul de l’heure d’été sont celles des États-Unis.|  
|`tm_mday`|Jour du mois (1 à 31)|  
|`tm_min`|Minutes après l’heure (0 à 59)|  
|`tm_mon`|Mois (de 0 à 11 ; Janvier = 0)|  
|`tm_sec`|Secondes après la minute (0 à 59)|  
|`tm_wday`|Jour de la semaine (0-6 ; Dimanche = 0)|  
|`tm_yday`|Jour de l’année (0-365 ; Le 1er janvier = 0)|  
|`tm_year`|Année (année en cours moins 1900)|  
  
 La chaîne de caractères convertie est également ajustée en fonction des paramètres de fuseau horaire local. Consultez les fonctions [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md), [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) et [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md) pour plus d’informations sur la configuration de l’heure locale, et la fonction [_tzset](../../c-runtime-library/reference/tzset.md) pour plus d’informations sur la définition des variables globales et d’environnement des fuseaux horaires.  
  
 Le résultat de chaîne généré par `asctime_s` contient exactement 26 caractères et présente la forme `Wed Jan 02 02:03:55 1980\n\0`. Une horloge de 24 heures est utilisée. Tous les champs ont une largeur constante. Le caractère de saut de ligne et le caractère null occupent les deux dernières positions de la chaîne. La valeur passée comme deuxième paramètre doit être au moins de cette taille. Sinon, le code d’erreur `EINVAL` est retourné.  
  
 `_wasctime_s` est une version à caractères larges de `asctime_s`. Sinon, `_wasctime_s` et `asctime_s` se comportent de la même façon.  
  
### <a name="generic-text-routine-mapping"></a>Mappage de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tasctime_s`|`asctime_s`|`asctime_s`|`_wasctime_s`|  
  
 En C++, l’utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire automatiquement la longueur de la mémoire tampon, ce qui évite d’avoir à spécifier un argument de taille. Pour plus d'informations, consultez [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`asctime_s`|\<time.h>|  
|`_wasctime_s`|\<time.h> ou \<wchar.h>|  
  
## <a name="security"></a>Sécurité  
 Si le pointeur de la mémoire tampon n’est pas `NULL` et que le pointeur ne désigne pas une mémoire tampon valide, la fonction remplace d’office ce qui se trouve à l’emplacement. Cela peut également entraîner une violation d’accès.  
  
 Un [dépassement de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795) peut se produire si l’argument de la taille passé est supérieur à la taille réelle de la mémoire tampon.  
  
## <a name="example"></a>Exemple  
 Ce programme place l’heure système dans l’entier long `aclock`, la traduit en structure `newtime`, puis la convertit sous forme de chaîne de sortie, à l’aide de la fonction `asctime_s`.  
  
```  
// crt_asctime_s.c  
#include <time.h>  
#include <stdio.h>  
  
struct tm newtime;  
__time32_t aclock;  
  
int main( void )  
{  
   char buffer[32];  
   errno_t errNum;  
   _time32( &aclock );   // Get time in seconds.  
   _localtime32_s( &newtime, &aclock );   // Convert time to struct tm form.  
  
   // Print local time as a string.  
  
   errNum = asctime_s(buffer, 32, &newtime);  
   if (errNum)  
   {  
       printf("Error code: %d", (int)errNum);  
       return 1;  
   }  
   printf( "Current date and time: %s", buffer );  
   return 0;  
}  
```  
  
```Output  
Current date and time: Wed May 14 15:30:17 2003  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)