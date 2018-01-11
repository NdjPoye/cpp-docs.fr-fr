---
title: localeconv | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: localeconv
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
apitype: DLLExport
f1_keywords: localeconv
dev_langs: C++
helpviewer_keywords:
- lconv type
- localeconv function
- locales, getting information on
ms.assetid: 7ecdb1f2-88f5-4037-a0e7-c754ab003660
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2cbd897b353f8a915fb4a29d61d0954b9b5a7f53
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="localeconv"></a>localeconv
Obtient des informations détaillées sur les paramètres régionaux.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
struct lconv *localeconv( void );  
```  
  
## <a name="return-value"></a>Valeur de retour  
 `localeconv` retourne un pointeur désignant un objet rempli de type [struct lconv](../../c-runtime-library/standard-types.md). Les valeurs contenues dans l’objet sont copiées depuis les paramètres régionaux dans le stockage local des threads et peut être remplacées par les appels suivants à `localeconv`. Modifications apportées aux valeurs dans cet objet ne modifiez pas les paramètres régionaux. Les appels à [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) avec les valeurs `category` de `LC_ALL`, `LC_MONETARY` ou `LC_NUMERIC` remplacent le contenu de la structure.  
  
## <a name="remarks"></a>Notes  
 La fonction `localeconv` obtient des informations détaillées sur la mise en forme numérique pour les paramètres régionaux actuels. Ces informations sont stockées dans une structure de type `lconv`. Le `lconv` structure, définie dans les paramètres régionaux. H, contient les membres suivants :  
  
 `char *decimal_point, wchar_t *_W_decimal_point`  
 Caractère de virgule décimale pour les quantités non monétaires.  
  
 `char *thousands_sep, wchar_t *_W_thousands_sep`  
 Caractère qui sépare les groupes de chiffres à gauche de la virgule décimale pour les quantités non monétaires.  
  
 `char *grouping`  
 Pointeur vers un `char`-taille d’entier qui contient la taille de chaque groupe de chiffres dans les quantités non monétaires.  
  
 `char *int_curr_symbol, wchar_t *_W_int_curr_symbol`  
 Symbole monétaire international pour les paramètres régionaux actuels. Les trois premiers caractères spécifient le symbole monétaire international alphabétique tel que le définit la *norme ISO 4217 sur les codes de représentation des monnaies et des fonds*. Le quatrième caractère (situé juste avant le caractère Null) sépare le symbole monétaire international de la quantité monétaire.  
  
 `char *currency_symbol, wchar_t *_W_currency_symbol`  
 Symbole monétaire local pour les paramètres régionaux actuels.  
  
 `char *mon_decimal_point, wchar_t *_W_mon_decimal_point`  
 Caractère de virgule décimale pour les quantités monétaires.  
  
 `char *mon_thousands_sep, wchar_t *_W_mon_thousands_sep`  
 Séparateur de groupes de chiffres à gauche du séparateur décimal dans les quantités monétaires.  
  
 `char *mon_grouping`  
 Pointeur vers un `char`-taille d’entier qui contient la taille de chaque groupe de chiffres dans les quantités monétaires.  
  
 `char *positive_sign, wchar_t *_W_positive_sign`  
 Chaîne indiquant le signe des quantités monétaires non négatives.  
  
 `char *negative_sign, wchar_t *_W_negative_sign`  
 Chaîne indiquant le signe des quantités monétaires négatives.  
  
 `char int_frac_digits`  
 Nombre de chiffres à droite du séparateur décimal dans les quantités monétaires à la mise en forme internationale.  
  
 `char frac_digits`  
 Nombre de chiffres à droite du séparateur décimal dans les quantités monétaires mises en forme.  
  
 `char p_cs_precedes`  
 Défini sur 1 si le symbole monétaire précède la valeur pour une quantité monétaire mise en forme non négative. Défini sur 0 si le symbole suit la valeur.  
  
 `char p_sep_by_space`  
 Défini sur 1 si le symbole monétaire est séparé par un espace de la valeur dans le cas d’une quantité monétaire mise en forme non négative. Défini sur 0 s’il n’y a aucun espace de séparation.  
  
 `char n_cs_precedes`  
 Défini sur 1 si le symbole monétaire précède la valeur dans le cas d’une quantité monétaire mise en forme négative. Défini sur 0 si le symbole suit la valeur.  
  
 `char n_sep_by_space`  
 Défini sur 1 si le symbole monétaire est séparé par un espace de la valeur dans le cas d’une quantité monétaire mise en forme négative. Défini sur 0 s’il n’y a aucun espace de séparation.  
  
 `char p_sign_posn`  
 Position du signe positif dans les quantités monétaires mises en forme non négatives.  
  
 `char n_sign_posn`  
 Position du signe positif dans les quantités monétaires mises en forme négatives.  
  
Sauf les membres spécifiés, de la `lconv` structure qui ont `char *` et `wchar_t *` versions sont des pointeurs vers des chaînes. Si l’un d’eux est égal à `""` (ou à `L""` pour `wchar_t *`), il est de longueur nulle ou n’est pas pris en charge dans les paramètres régionaux actuels. Notez que `decimal_point` et `_W_decimal_point` sont toujours pris en charge et de longueur non nulle.  
  
Les membres `char` de la structure sont des nombres petits non négatifs, et non des caractères. Une de ces égal à `CHAR_MAX` n’est pas pris en charge dans les paramètres régionaux actuels.  
  
Les valeurs de `grouping` et `mon_grouping` sont interprétés en fonction des règles suivantes :  
  
- `CHAR_MAX`-Ne pas exécuter n’importe quel regroupement.  
  
- 0 - utilisez l’élément précédent pour chacun des autres chiffres.  
  
- *n*-Nombre de chiffres qui composent le groupe actuel. L’élément suivant est examiné pour déterminer la taille du groupe de chiffres suivant situé avant le groupe actuel.  
  
Les valeurs de `int_curr_symbol` sont interprétés en fonction des règles suivantes :  
  
-   Les trois premiers caractères spécifient le symbole monétaire international alphabétique tel que le définit la *norme ISO 4217 sur les codes de représentation des monnaies et des fonds*.  
  
-   Le quatrième caractère (situé juste avant le caractère Null) sépare le symbole monétaire international de la quantité monétaire.  
  
Les valeurs de `p_cs_precedes` et `n_cs_precedes` sont interprétés en fonction des règles suivantes (la `n_cs_precedes` règle figure entre parenthèses) :  
  
- 0 - symbole monétaire suit la valeur pour une valeur non négative (négatif) au format monétaire.  
  
- 1 - symbole précède la valeur pour une valeur non négative (négatif) au format monétaire.  
  
Les valeurs de `p_sep_by_space` et `n_sep_by_space` sont interprétés en fonction des règles suivantes (la `n_sep_by_space` règle figure entre parenthèses) :  
  
- 0 - symbole monétaire est séparée de la valeur par un espace de valeur non négative (négatif) au format monétaire.  
  
- 1 - il n’existe pas d’espace de séparation entre symbole monétaire et la valeur de la valeur non négative (négatif) au format monétaire.  
  
Les valeurs de `p_sign_posn` et `n_sign_posn` sont interprétés en fonction des règles suivantes :  
  
- 0 - parenthèses entourent symbole quantité et de devise.  
  
- 1 - chaîne de connexion précède le symbole de quantité et de devise.  
  
- 2 - chaîne de connexion suit le symbole de quantité et de devise.  
  
- 3 - chaîne de connexion précède immédiatement le symbole monétaire.  
  
- 4 - signe de chaîne symbole suit immédiatement.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`localeconv`|\<locale.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [setlocale](../../preprocessor/setlocale.md)   
 [strcoll, fonctions](../../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)