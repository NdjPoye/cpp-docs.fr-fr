---
title: strftime, wcsftime, _strftime_l, _wcsftime_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- strftime
- _wcsftime_l
- _strftime_l
- wcsftime
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
- _tcsftime
- strftime
- wcsftime
dev_langs: C++
helpviewer_keywords:
- _strftime_l function
- strftime function
- tcsftime function
- _wcsftime_l function
- wcsftime function
- _tcsftime function
- time strings
ms.assetid: 6330ff20-4729-4c4a-82af-932915d893ea
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ec9c46f1a6d52a8769e5db454d44baf9ec9d8a8a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="strftime-wcsftime-strftimel-wcsftimel"></a>strftime, wcsftime, _strftime_l, _wcsftime_l
Mettent en forme une chaîne d’heure.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
size_t strftime(  
   char *strDest,  
   size_t maxsize,  
   const char *format,  
   const struct tm *timeptr   
);  
size_t _strftime_l(  
   char *strDest,  
   size_t maxsize,  
   const char *format,  
   const struct tm *timeptr,  
   _locale_t locale  
);  
size_t wcsftime(  
   wchar_t *strDest,  
   size_t maxsize,  
   const wchar_t *format,  
   const struct tm *timeptr   
);  
size_t _wcsftime_l(  
   wchar_t *strDest,  
   size_t maxsize,  
   const wchar_t *format,  
   const struct tm *timeptr,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `strDest`  
 Chaîne de sortie.  
  
 `maxsize`  
 Taille de la mémoire tampon `strDest`, mesurée en caractères (`char` ou `wchart_t`).  
  
 `format`  
 Chaîne de contrôle de format.  
  
 `timeptr`  
 Structure de données `tm`.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 `strftime` retourne le nombre de caractères placés dans `strDest` et `wcsftime` retourne le nombre correspondant de caractères larges.  
  
 Si le nombre total de caractères, caractère Null de fin inclus, est supérieur à `maxsize`, `strftime` et `wcsftime` retournent 0 et le contenu de `strDest` est indéterminé.  
  
 Le nombre de caractères présents dans `strDest` est égal au nombre de caractères littéraux contenus dans `format` et des caractères éventuellement ajoutés à `format` via des codes de mise en forme. Le caractère Null de fin d’une chaîne n’est pas compté dans la valeur de retour.  
  
## <a name="remarks"></a>Remarques  
 Le `strftime` et `wcsftime` format de fonctions la `tm` temps dans `timeptr` en fonction de l’élément `format` argument et le résultat dans la mémoire tampon de magasin `strDest`. Tout au plus, des caractères `maxsize` sont placés dans la chaîne. Pour obtenir une description des champs de la structure `timeptr`, consultez [asctime](../../c-runtime-library/reference/asctime-wasctime.md). `wcsftime` est l’équivalent en caractères larges de `strftime` ; son argument de pointeur de chaîne pointe vers une chaîne de caractères larges. Ces fonctions se comportent sinon de façon identique.  
  
> [!NOTE]
>  Dans les versions antérieures à Visual C++ 2005, la documentation décrivait le paramètre `format` de `wcsftime` comme ayant le type de données `const wchar_t *`. Or, l’implémentation effective du type de données `format` était `const char *`. L’implémentation de la `format` type de données a été mis à jour pour refléter la documentation précédente et actuelle, autrement dit, `const wchar_t *`.  
  
 Cette fonction valide ses paramètres. Si `strDest`, `format`, ou `timeptr` est un pointeur null, ou si le `tm` structure de données traité par `timeptr` n’est pas valide (par exemple, s’il contient des valeurs hors limites pour la date ou heure), ou si le `format` chaîne contient un code de mise en forme non valide, le Gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, la fonction retourne 0 et affecte à `errno` la valeur `EINVAL`.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsftime`|`strftime`|`strftime`|`wcsftime`|  
  
 L’argument `format` se compose d’un ou plusieurs codes ; comme dans `printf`, les codes de mise en forme sont précédés d’un signe de pourcentage (`%`). Les caractères qui ne commencent pas par `%` sont copiées telles quelles à `strDest`. La catégorie `LC_TIME` des paramètres régionaux actifs affecte la mise en forme de sortie de `strftime`. (Pour plus d’informations sur `LC_TIME`, consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).) Les fonctions sans suffixe `_l` utilisent les paramètres régionaux actuellement définis. Les versions de ces fonctions avec suffixe `_l` sont identiques, sauf qu’elles prennent les paramètres régionaux comme paramètre et les utilisent à la place des paramètres régionaux actuellement définis. Pour plus d’informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Les codes de mise en forme de `strftime` sont répertoriés ci-dessous :  
  
 `%a`  
 Nom de jour de la semaine abrégé  
  
 `%A`  
 Nom de jour de la semaine complet  
  
 `%b`  
 Nom de mois abrégé  
  
 `%B`  
 Nom de mois complet  
  
 `%c`  
 Représentation de la date et de l’heure correspondant aux paramètres régionaux  
  
 `%d`  
 Jour du mois sous forme décimale (01 à 31)  
  
 `%H`  
 Heure au format 24 heures (00 - 23)  
  
 `%I`  
 Heure au format de 12 heures (01 à 12)  
  
 `%j`  
 Jour de l’année sous forme décimale (001-366)  
  
 `%m`  
 Mois sous forme décimale (01 à 12)  
  
 `%M`  
 Minute sous forme de nombre décimal (00 - 59)  
  
 `%p`  
 Indicateur A.M./P.M. des paramètre régionaux actifs pour l’heure au format 12 heures  
  
 `%S`  
 Seconde sous forme de nombre décimal (00 - 59)  
  
 `%U`  
 Semaine de l’année sous la forme d’un nombre décimal, dimanche étant le premier jour de la semaine (00 - 53)  
  
 `%w`  
 Jour de la semaine sous forme décimale (0 - 6 ; Dimanche est 0)  
  
 `%W`  
 Semaine sous forme de nombre décimal, lundi étant le premier jour de la semaine (00 - 53)  
  
 `%x`  
 Représentation de la date en fonction des paramètres régionaux actifs  
  
 `%X`  
 Représentation de l’heure en fonction des paramètres régionaux actifs  
  
 `%y`  
 Année sans siècle, sous forme de nombre décimal (00 - 99)  
  
 `%Y`  
 Année avec le siècle, sous forme de nombre décimal  
  
 `%z, %Z`  
 Nom du fuseau horaire complet ou abrégé, selon les paramètres de Registre ; absence de caractères si le fuseau horaire est inconnu  
  
 `%%`  
 Signe de pourcentage  
  
 Comme dans la fonction `printf`, l’indicateur `#` peut servir de préfixe à n’importe quel code de mise en forme. Dans ce cas, la signification du code de format change comme suit.  
  
|Code du format|Signification|  
|-----------------|-------------|  
|`%#a, %#A, %#b, %#B, %#p, %#X, %#z, %#Z, %#%`|L’indicateur `#` est ignoré.|  
|`%#c`|Représentation longue de la date et de l’heure correspondant aux paramètres régionaux actifs. Par exemple : « Mardi 14 mars 1995, 12:41:29 ».|  
|`%#x`|Représentation longue de la date correspondant aux paramètres régionaux actifs. Par exemple : « Mardi 14 mars 1995 ».|  
|`%#d, %#H, %#I, %#j, %#m, %#M, %#S, %#U, %#w, %#W, %#y, %#Y`|Supprime les zéros non significatifs éventuels.|  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`strftime`|\<time.h>|  
|`wcsftime`|\<time.h> ou \<wchar.h>|  
|`_strftime_l`|\<time.h>|  
|`_wcsftime_l`|\<time.h> ou \<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple relatif à [time](../../c-runtime-library/reference/time-time32-time64.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcoll, fonctions](../../c-runtime-library/strcoll-functions.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)