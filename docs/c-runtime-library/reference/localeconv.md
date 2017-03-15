---
title: "localeconv | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "localeconv"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "localeconv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lconv (type)"
  - "localeconv (fonction)"
  - "paramètres régionaux, obtenir des informations sur"
ms.assetid: 7ecdb1f2-88f5-4037-a0e7-c754ab003660
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# localeconv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient des informations détaillées sur les paramètres régionaux.  
  
## Syntaxe  
  
```  
  
struct lconv *localeconv( void );  
```  
  
## Valeur de retour  
 `localeconv` retourne un pointeur vers un objet rempli de type [lconv de structure](../../c-runtime-library/standard-types.md).  Les valeurs contenues dans l'objet peuvent être remplacées par les appels suivants à `localeconv` et ne modifient pas directement l'objet.  Des appels à [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) avec des valeurs `category` de `LC_ALL`, `LC_MONETARY`, ou `LC_NUMERIC` remplacent le contenu de la structure.  
  
## Notes  
 La fonction `localeconv` obtient des informations détaillées à propos de la mise en forme numérique pour les paramètres régionaux actuels.  Ces informations sont stockées dans une structure de type **lconv**.  La structure de **lconv**, définie dans LOCALE.H, contient les membres suivants :  
  
 `char *decimal_point, wchar_t *_W_decimal_point`  
 Caractère à virgule décimale pour les quantités non monétaires.  
  
 `char *thousands_sep, wchar_t *_W_thousands_sep`  
 Caractère qui sépare des groupes de chiffres à gauche de la virgule décimale pour les quantités non monétaires.  
  
 `char *grouping`  
 Taille de chaque groupe de chiffres en quantités non monétaires.  
  
 `char *int_curr_symbol, wchar_t *_W_int_curr_symbol`  
 Symbole monétaire international pour les paramètres régionaux actuels.  Les trois premiers caractères spécifient le symbole monétaire international alphabétique conformément au *ISO 4217 codes pour la représentation de la devise et les fonds* standard.  Le quatrième caractère \(précédant immédiatement le caractère Null\) sépare le symbole monétaire international de la valeur monétaire.  
  
 `char *currency_symbol, wchar_t *_W_currency_symbol`  
 Symbole monétaire local pour les paramètres régionaux actuels.  
  
 `char *mon_decimal_point, wchar_t *_W_mon_decimal_point`  
 Caractère à virgule décimale pour les quantités monétaires.  
  
 `char *mon_thousands_sep, wchar_t *_W_mon_thousands_sep`  
 Séparateur pour les groupes de chiffres à gauche de la virgule dans une valeur monétaire.  
  
 `char *mon_grouping`  
 Taille de chaque groupe de chiffres en quantités monétaires.  
  
 `char *positive_sign, wchar_t *_W_positive_sign`  
 Chaîne indiquant le signe des montants monétaires non négatifs.  
  
 `char *negative_sign, wchar_t *_W_negative_sign`  
 Chaîne indiquant le signe des montants monétaires négatifs.  
  
 `char int_frac_digits`  
 Nombre de chiffres à droite de la virgule décimale dans une valeur monétaire internationalement mise en forme.  
  
 `char frac_digits`  
 Nombre de chiffres à droite de la virgule décimale dans une valeur monétaire mise en forme.  
  
 `char p_cs_precedes`  
 Attribuez la valeur 1 si le symbole monétaire précède la valeur monétaire mise en forme non négative.  Attribuez la valeur 0 si le symbole suit la valeur.  
  
 `char p_sep_by_space`  
 Attribuez la valeur 1 si le symbole monétaire est séparé par un espace de la valeur monétaire mise en forme non négative.  Attribuez la valeur 0 s'il n'y a pas d'espace de séparation.  
  
 `char n_cs_precedes`  
 Attribuez la valeur 1 si le symbole monétaire précède la valeur monétaire mise en forme négative.  Attribuez la valeur 0 si le symbole suit la valeur.  
  
 `char n_sep_by_space`  
 Attribuez la valeur 1 si le symbole monétaire est séparé par un espace de la valeur monétaire mise en forme négative.  Attribuez la valeur 0 s'il n'y a pas d'espace de séparation.  
  
 `char p_sign_posn`  
 La position du signe positif des montants monétaires mis en forme non négatifs.  
  
 `char n_sign_posn`  
 La position du signe positif des montants monétaires mis en forme négatifs.  
  
 Les membres de la structure qui ont des versions `char` `*` et `wchar_t *` sont des pointeurs vers des chaînes.  N'importe lequel de ceux\-ci qui égale `""` \(ou `L""` pour `wchar_t *`\) est de longueur nulle ou non pris en charge dans les paramètres régionaux actuels.  Notez que `decimal_point` et `_W_decimal_point` sont toujours pris en charge et de longueur différente de zéro.  
  
 Les membres `char` de la structure sont des petits nombres non négatifs, et non des caractères.  N'importe lequel de ceux\-ci qui égale **CHAR\_MAX** n'est pas pris en charge dans les paramètres régionaux actuels.  
  
 Les éléments de **regroupement** et de **mon\_grouping** sont interprétés en fonction des règles suivantes.  
  
 **CHAR\_MAX**  
 N'exécutez pas d'agrégation supplémentaire.  
  
 0  
 Utilisez l'élément précédent pour chacun des chiffres restants.  
  
 *n*  
 Nombre de chiffres qui composent le groupe actuel.  L'élément suivant est examiné pour déterminer la taille du groupe suivant de données avant le groupe actuel.  
  
 Les valeurs de **int\_curr\_symbol** sont interprétées en fonction des règles suivantes :  
  
-   Les trois premiers caractères spécifient le symbole monétaire international alphabétique conformément au *ISO 4217 codes pour la représentation de la devise et les fonds* standard.  
  
-   Le quatrième caractère \(précédant immédiatement le caractère Null\) sépare le symbole monétaire international de la valeur monétaire.  
  
 Les valeurs de **p\_cs\_precedes** et **n\_cs\_precedes** sont interprétées en fonction des règles suivantes \(la règle de **n\_cs\_precedes** est entre parenthèses\) :  
  
 0  
 Le symbole monétaire suit la valeur pour des valeurs monétaires mises en forme non négatives \(négatives\)  
  
 1  
 Le symbole monétaire précède la valeur pour des valeurs monétaires mises en forme non négatives \(négatives\)  
  
 Les valeurs de **p\_sep\_by\_space** et **n\_sep\_by\_space** sont interprétées en fonction des règles suivantes \(la règle de **n\_sep\_by\_space** est entre parenthèses\) :  
  
 0  
 Le symbole monétaire est séparé de la valeur par un espace pour une valeur monétaire mise en forme non négative \(négative\).  
  
 1  
 Il n'y a pas d'espace de séparation entre le symbole monétaire et la valeur monétaire mise en forme non négative \(négative\).  
  
 Les valeurs de **p\_sign\_posn** et **n\_sign\_posn** sont interprétées en fonction des règles suivantes :  
  
 0  
 Des parenthèses entourent la valeur et le symbole monétaires.  
  
 1  
 La chaîne de signe précède la quantité et le symbole monétaires.  
  
 2  
 La chaîne de signe suit la quantité et le symbole monétaires.  
  
 3  
 La chaîne de signe précède immédiatement le symbole monétaire.  
  
 4  
 La chaîne de signe suit immédiatement le symbole monétaire.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`localeconv`|\<locale.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Voir aussi  
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [setlocale](../../preprocessor/setlocale.md)   
 [strcoll, fonctions](../../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)