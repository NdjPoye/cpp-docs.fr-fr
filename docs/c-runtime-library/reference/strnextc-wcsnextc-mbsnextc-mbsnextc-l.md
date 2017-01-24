---
title: "_strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_strnextc"
  - "_mbsnextc_l"
  - "_mbsnextc"
  - "_wcsnextc"
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
  - "strnextc"
  - "tcsnextc"
  - "_mbsnextc_l"
  - "_mbsnextc"
  - "mbsnextc_l"
  - "ftcsnextc"
  - "mbsnextc"
  - "_tcsnextc"
  - "_wcsnextc"
  - "_ftcsnextc"
  - "_strnextc"
  - "wcsnextc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsnextc (fonction)"
  - "_mbsnextc_l (fonction)"
  - "_strnextc (fonction)"
  - "_tcsnextc (fonction)"
  - "_wcsnextc (fonction)"
  - "mbsnextc (fonction)"
  - "mbsnextc_l (fonction)"
  - "strnextc (fonction)"
  - "tcsnextc (fonction)"
  - "wcsnextc (fonction)"
ms.assetid: e3086173-9eb5-4540-a23a-5d866bd05340
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Recherche le caractère suivant dans une chaîne.  
  
> [!IMPORTANT]
>  `_mbsnextc` et `_mbsnextc_l` ne peuvent pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
unsigned int _strnextc(  
   const char *str  
);  
unsigned int _wscnextc(  
   const wchar_t *str  
);   
unsigned int _mbsnextc(  
   const unsigned char *str   
);  
unsigned int _mbsnextc_l(  
   const unsigned char *str,  
   _locale_t locale  
);  
  
```  
  
#### Paramètres  
 `str`  
 Chaîne source.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne la valeur entière du caractère suivant dans `str`*.*  
  
## Notes  
 La fonction `_mbsnextc` retourne la valeur entière du caractère multi\-octets suivant dans `str`, sans déplacer le pointeur de chaîne.  `_mbsnextc` identifie des séquences de caractères multi\-octets selon la [page de codes multi\-octets](../../c-runtime-library/code-pages.md) en cours d'utilisation.  
  
 Si `str` est `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `errno` is affecté à la valeur `EINVAL` et la fonction retourne 0.  
  
 **Note de sécurité** Cette API entraîne un risque potentiel provoqué par un problème de dépassement de mémoire tampon.  Les dépassements de mémoire tampon sont une méthode fréquente d'attaque du système, ce qui provoque une élévation des privilèges injustifiée.  Pour plus d'informations, consultez [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tcsnextc`|`_strnextc`|`_mbsnextc`|`_wcsnextc`|  
  
 `_strnextc` et `_wcsnextc` sont des versions de `_mbsnextc` traitant des chaînes de caractères sur un seul octet et à caractères élargis respectivement.  `_wcsnextc` retourne la valeur entière du caractère élargi suivant dans `string`; `_strnextc` retourne la valeur entière du caractère codé sur un octet suivant dans `string`.  `_strnextc` et `_wcsnextc` sont fournis uniquement pour ce mappage et ne doivent pas être utilisés sinon.  Pour plus d'informations, consultez [Utilisation des mappages de texte générique](../../c-runtime-library/using-generic-text-mappings.md) et [Mappages de texte générique](../../c-runtime-library/generic-text-mappings.md).  
  
 `_mbsnextc_l`  est identique sauf qu'il utilise à la place les paramètres régionaux qui sont passés.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_mbsnextc`|\<mbstring.h\>|  
|`_mbsnextc_l`|\<mbstring.h\>|  
|`_strnextc`|\<tchar.h\>|  
|`_wcsnextc`|\<tchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_strdec, \_wcsdec, \_mbsdec, \_mbsdec\_l](../../c-runtime-library/reference/strdec-wcsdec-mbsdec-mbsdec-l.md)   
 [\_strinc, \_wcsinc, \_mbsinc, \_mbsinc\_l](../../c-runtime-library/reference/strinc-wcsinc-mbsinc-mbsinc-l.md)   
 [\_strninc, \_wcsninc, \_mbsninc, \_mbsninc\_l](../../c-runtime-library/reference/strninc-wcsninc-mbsninc-mbsninc-l.md)