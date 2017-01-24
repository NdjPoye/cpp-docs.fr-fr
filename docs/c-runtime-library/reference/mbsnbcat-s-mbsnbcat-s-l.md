---
title: "_mbsnbcat_s, _mbsnbcat_s_l | Microsoft Docs"
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
  - "_mbsnbcat_s_l"
  - "_mbsnbcat_s"
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
  - "_mbsnbcat_s"
  - "mbsnbcat_s"
  - "_mbsnbcat_s_l"
  - "mbsnbcat_s_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsnbcat_s (fonction)"
  - "_mbsnbcat_s_l (fonction)"
  - "_tcsncat (fonction)"
  - "_tcsncat_s_l (fonction)"
  - "mbsnbcat_s (fonction)"
  - "mbsnbcat_s_l (fonction)"
  - "tcsncat (fonction)"
  - "tcsncat_s_l (fonction)"
ms.assetid: 2c9e9be7-d979-4a54-8ada-23428b6648a9
caps.latest.revision: 28
caps.handback.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mbsnbcat_s, _mbsnbcat_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ajoute à une chaîne de caractères multioctets, au plus, les `n` premiers octets d'une autre chaîne de caractères multioctets.  Il s'agit de versions de [\_mbsnbcat, \_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md) qui intègrent des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Pour plus d'informations, voir [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
errno_t _mbsnbcat_s(  
   unsigned char *dest,  
   size_t sizeInBytes,  
   const unsigned char *src,  
   size_t count   
);  
errno_t _mbsnbcat_s_l(  
   unsigned char *dest,  
   size_t sizeInBytes,  
   const unsigned char *src,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t _mbsnbcat_s(  
   unsigned char (&dest)[size],  
   const unsigned char *src,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _mbsnbcat_s_l(  
   unsigned char (&dest)[size],  
   const unsigned char *src,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### Paramètres  
 `dest`  
 Chaîne de destination à caractères multioctets se terminant par un caractère null.  
  
 `sizeInBytes`  
 Taille de la mémoire tampon `dest` en octets.  
  
 `src`  
 Chaîne source à caractères multioctets se terminant par un caractère null.  
  
 `Count`  
 Nombre d'octets de `src` à ajouter à `dest`.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Zéro en cas de réussite ; code d'erreur dans un autre cas.  
  
### Conditions d'erreur  
  
|`Dest`|`sizeInBytes`|`src`|Valeur de retour|  
|------------|-------------------|-----------|----------------------|  
|`NULL`|tous|tous|`EINVAL`|  
|Tous|\<\= 0|tous|`EINVAL`|  
|Tous|tous|`NULL`|`EINVAL`|  
  
 Si l'une des conditions d'erreur se produit, la fonction génère une erreur de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'erreur est gérée, la fonction retourne `EINVAL` et attribue à `errno` la valeur `EINVAL`.  
  
## Notes  
 La fonction `_mbsnbcat_s` ajoute à `dest`, au plus, les `count` premiers octets de `src`.  Si l'octet qui précède immédiatement le caractère null dans `dest` est un octet de tête, il est remplacé par l'octet initial de `src`.  Dans le cas contraire, l'octet initial de `src` remplace le caractère null de fin de `dest`.  Si un octet null apparaît dans `src` avant l'ajout de `count` octets, `_mbsnbcat_s` ajoute tous les octets de `src`, jusqu'au caractère null.  Si la valeur `count` est supérieure à la longueur de `src`, la longueur de `src` est utilisée à la place de `count`.  La chaîne obtenue se termine par un caractère null.  Si la copie se produit entre des chaînes qui se chevauchent, le comportement est indéfini.  
  
 La valeur de la sortie est affectée par la valeur du paramètre de la catégorie `LC_CTYPE` des paramètres régionaux ; consultez [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md), pour plus d'informations.  Les versions de ces fonctions sont identiques, sauf que celles qui n'ont pas le suffixe `_l` utilisent les paramètres régionaux actuels et celles qui ont le suffixe `_l` utilisent à la place les paramètres régionaux qui ont été passés.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 En C\+\+, l'utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement, ce qui évite ainsi d'avoir à spécifier un argument de taille, et elles peuvent utiliser automatiquement leurs fonctions plus récentes et plus sécurisées en remplacement des fonctions plus anciennes, moins sécurisées.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
 Les versions debug de ces fonctions remplissent d'abord la mémoire tampon avec 0xFD.  Pour désactiver ce comportement, utilisez [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tcsncat`|[strncnt](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|`_mbsnbcat_s`|[wcsncat](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|  
|`_tcsncat_s_l`|`_strncat_s_l`|`_mbsnbcat_s_l`|`_wcsncat_s_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_mbsnbcat_s`|\<mbstring.h\>|  
|`_mbsnbcat_s_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcmp, \_mbsnbcmp\_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [\_strncnt, \_wcsncnt, \_mbsnbcnt, \_mbsnbcnt\_l, \_mbsnccnt, \_mbsnccnt\_l](../../c-runtime-library/reference/strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)   
 [\_mbsnbcpy, \_mbsnbcpy\_l](../../c-runtime-library/reference/mbsnbcpy-mbsnbcpy-l.md)   
 [\_mbsnbcpy\_s, \_mbsnbcpy\_s\_l](../../c-runtime-library/reference/mbsnbcpy-s-mbsnbcpy-s-l.md)   
 [\_mbsnbset, \_mbsnbset\_l](../../c-runtime-library/reference/mbsnbset-mbsnbset-l.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncat\_s, \_strncat\_s\_l, wcsncat\_s, \_wcsncat\_s\_l, \_mbsncat\_s, \_mbsncat\_s\_l](../../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)