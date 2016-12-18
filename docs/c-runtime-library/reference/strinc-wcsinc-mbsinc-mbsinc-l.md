---
title: "_strinc, _wcsinc, _mbsinc, _mbsinc_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsinc"
  - "_wcsinc"
  - "_mbsinc_l"
  - "_strinc"
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
apitype: "DLLExport"
f1_keywords: 
  - "mbsinc_l"
  - "_strinc"
  - "strinc"
  - "_mbsinc"
  - "_wcsinc"
  - "wcsinc"
  - "mbsinc"
  - "_mbsinc_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsinc (fonction)"
  - "_mbsinc_l (fonction)"
  - "_strinc (fonction)"
  - "_tcsinc (fonction)"
  - "_wcsinc (fonction)"
  - "mbsinc (fonction)"
  - "mbsinc_l (fonction)"
  - "strinc (fonction)"
  - "tcsinc (fonction)"
  - "wcsinc (fonction)"
ms.assetid: 54685943-8e2c-45e9-a559-2d94930dc6b4
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strinc, _wcsinc, _mbsinc, _mbsinc_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Avance un pointeur de chaîne d'un caractère.  
  
> [!IMPORTANT]
>  Les fonctions `_mbsinc` et `_mbsinc_l` ne peuvent pas être utilisées dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Pour plus d'informations, voir [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
char *_strinc(    const char *current,    _locale_t locale ); wchar_t *_wcsinc(    const wchar_t *current,    _locale_t locale ); unsigned char *_mbsinc(    const unsigned char *current  ); unsigned char *_mbsinc_l(    const unsigned char *current,    _locale_t locale );   
```  
  
#### Paramètres  
 `current`  
 Pointeur de caractère.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Chacune de ces routines retourne un pointeur vers le caractère qui suit immédiatement `current`.  
  
## Notes  
 La fonction `_mbsinc` retourne un pointeur vers le premier octet du caractère multioctets qui suit immédiatement `current`.  `_mbsinc` reconnaît les séquences de caractères multioctets en fonction de la [page de code multioctets](../../c-runtime-library/code-pages.md) en cours d'utilisation ; `_mbsinc_l` est identique, à ceci près qu'elle utilise les paramètres régionaux qui lui sont passés.  Pour plus d'informations, voir [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 La fonction de texte générique `_tcsinc`, définie dans Tchar.h, est mappée à `_mbsinc` si `_MBCS` a été défini, ou à `_wcsinc` si `_UNICODE` a été défini.  Sinon, `_tcsinc` est mappée à `_strinc`.  `_strinc` et `_wcsinc` sont des versions à caractères codés sur un octet et à caractères larges de `_mbsinc`.  `_strinc` et `_wcsinc` sont fournies uniquement pour ce mappage et ne doivent sinon pas être utilisées.  Pour plus d’informations, voir [Utilisation des mappages de texte générique](../../c-runtime-library/using-generic-text-mappings.md) et [Mappages de texte générique](../../c-runtime-library/generic-text-mappings.md).  
  
 Si `current` a la valeur `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction retourne `EINVAL` et affecte à `errno` la valeur `EINVAL`.  
  
> [!IMPORTANT]
>  Ces fonctions peuvent être vulnérables aux menaces de dépassement de mémoire tampon.  Les dépassements de mémoire tampon peuvent être utilisés pour les attaques du système, car ils peuvent provoquer une élévation des privilèges injustifiée.  Pour plus d'informations, voir [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_mbsinc`|\<mbstring.h\>|  
|`_mbsinc_l`|\<mbstring.h\>|  
|`_strinc`|\<tchar.h\>|  
|`_wcsinc`|\<tchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, voir [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [\_strdec, \_wcsdec, \_mbsdec, \_mbsdec\_l](../../c-runtime-library/reference/strdec-wcsdec-mbsdec-mbsdec-l.md)   
 [\_strnextc, \_wcsnextc, \_mbsnextc, \_mbsnextc\_l](../../c-runtime-library/reference/strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)   
 [\_strninc, \_wcsninc, \_mbsninc, \_mbsninc\_l](../../c-runtime-library/reference/strninc-wcsninc-mbsninc-mbsninc-l.md)