---
title: "_strupr_s, _strupr_s_l, _mbsupr_s, _mbsupr_s_l, _wcsupr_s, _wcsupr_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_strupr_s"
  - "_strupr_s_l"
  - "_mbsupr_s"
  - "_wcsupr_s_l"
  - "_mbsupr_s_l"
  - "_wcsupr_s"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "strupr_s"
  - "mbsupr_s"
  - "wcsupr_s"
  - "_mbsupr_s_l"
  - "mbsupr_s_l"
  - "wcsupr_s_l"
  - "_wcsupr_s"
  - "_tcsupr_s_l"
  - "_mbsupr_s"
  - "_tcsupr_s"
  - "strupr_s_l"
  - "_wcsupr_s_l"
  - "_strupr_s"
  - "_strupr_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsupr_s (fonction)"
  - "_mbsupr_s_l (fonction)"
  - "_strupr_s (fonction)"
  - "_strupr_s_l (fonction)"
  - "_tcsupr_s (fonction)"
  - "_tcsupr_s_l (fonction)"
  - "_wcsupr_s (fonction)"
  - "_wcsupr_s_l (fonction)"
  - "convertir la casse, CRT (fonctions)"
  - "mbsupr_s (fonction)"
  - "mbsupr_s_l (fonction)"
  - "conversion de chaînes (C++), casse"
  - "chaînes (C++), casse"
  - "chaînes (C++), convertir la casse"
  - "strupr_s (fonction)"
  - "strupr_s_l (fonction)"
  - "tcsupr_s (fonction)"
  - "tcsupr_s_l (fonction)"
  - "majuscules, convertir les chaînes en"
  - "wcsupr_s (fonction)"
  - "wcsupr_s_l (fonction)"
ms.assetid: 82d3a273-9f6f-4a26-9560-919d891e4581
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 30
---
# _strupr_s, _strupr_s_l, _mbsupr_s, _mbsupr_s_l, _wcsupr_s, _wcsupr_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit une chaîne en majuscules, avec les paramètres régionaux actuels ou des paramètres régionaux spécifiés qui sont passés.  Ces versions [\_strupr, \_strupr\_l, \_mbsupr, \_mbsupr\_l, \_wcsupr\_l, \_wcsupr](../../c-runtime-library/reference/strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md) présentent des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  `_mbsupr_s` et `_mbsupr_s_l` ne peuvent pas être utilisées dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
errno_t _strupr_s(  
   char *str,  
   size_t numberOfElements  
);  
errno_t _wcsupr_s(  
   wchar_t * str,  
   size_t numberOfElements  
);  
errno_t _strupr_s_l(  
   char * str,  
   size_t numberOfElements,  
   _locale_t locale  
);  
errno_t _wcsupr_s_l(  
   wchar_t * str,  
   size_t numberOfElements,  
   _locale_t locale  
);  
errno_t _mbsupr_s(  
   unsigned char *str,  
   size_t numberOfElements  
);  
errno_t _mbsupr_s_l(  
   unsigned char *str,  
   size_t numberOfElements,  
   _locale_t locale  
);  
template <size_t size>  
errno_t _strupr_s(  
   char (&str)[size]  
); // C++ only  
template <size_t size>  
errno_t _wcsupr_s(  
   wchar_t (&str)[size]  
); // C++ only  
template <size_t size>  
errno_t _strupr_s_l(  
   char (&str)[size],  
   _locale_t locale  
); // C++ only  
template <size_t size>  
errno_t _wcsupr_s_l(  
   wchar_t (&str)[size],  
   _locale_t locale  
); // C++ only  
template <size_t size>  
errno_t _mbsupr_s(  
   unsigned char (&str)[size]  
); // C++ only  
template <size_t size>  
errno_t _mbsupr_s_l(  
   unsigned char (&str)[size],  
   _locale_t locale  
); // C++ only  
```  
  
#### Paramètres  
 `str`  
 Chaîne à mettre en majuscules.  
  
 `numberOfElements`  
 Taille de la mémoire tampon.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Zéro si l'opération a réussi ; code d'erreur non nul en cas d'échec.  
  
 Ces fonctions valident leurs paramètres.  Si `str` est un pointeur `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, les fonctions retournent \-1 `EINVAL` et attribuent à `errno` la valeur `EINVAL`.  Si `numberOfElements` est inférieur à la longueur de la chaîne de caractère, les fonctions retournent également `ERANGE` et attribuent à `errno` la valeur `ERANGE`.  
  
## Notes  
 La fonction `_strupr_s` convertit, sur place, toutes les lettres minuscules dans `str` en majuscules.  `_wcsupr_s` est la version à caractère élargi de `_strupr_s`.  `_mbsupr_s` est la version à caractères multioctet de `_strupr_s`.  
  
 La conversion est déterminée par le paramètre de catégorie `LC_CTYPE` des paramètres régionaux.  Les autres caractères ne sont pas affectés.  Pour plus d'informations sur `LC_CTYPE`, consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux actuels; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux passés.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 En C\+\+, l'utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement \(ce qui évite d'avoir à spécifier un argument taille\) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalentes plus récentes et sécurisées.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
 Les versions debug de ces fonctions remplissent d'abord la mémoire tampon avec 0xFD.  Pour désactiver ce comportement, utilisez [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tcsupr_s`|`_strupr_s`|`_mbsupr_s`|`_wcsupr_s`|  
|`_tcsupr_s_l`|`_strupr_s_l`|`_mbsupr_s_l`|`_wcsupr_s_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_strupr_s`, `_strupr_s_l`|\<string.h\>|  
|`_wcsupr_s`, `_wcsupr_s_l`, `_mbsupr_s`, `_mbsupr_s_l`|\<string.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
 Consultez l'exemple pour [\_strlwr\_s, \_strlwr\_s\_l, \_mbslwr\_s, \_mbslwr\_s\_l, \_wcslwr\_s, \_wcslwr\_s\_l](../../c-runtime-library/reference/strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md).  
  
## Équivalent .NET Framework  
 [System::String::ToUpper](https://msdn.microsoft.com/en-us/library/system.string.toupper.aspx)  
  
## Voir aussi  
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [\_strlwr\_s, \_strlwr\_s\_l, \_mbslwr\_s, \_mbslwr\_s\_l, \_wcslwr\_s, \_wcslwr\_s\_l](../../c-runtime-library/reference/strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md)