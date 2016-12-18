---
title: "mbstowcs_s, _mbstowcs_s_l | Microsoft Docs"
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
  - "_mbstowcs_s_l"
  - "mbstowcs_s"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_mbstowcs_s_l"
  - "mbstowcs_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbstowcs_s_l (fonction)"
  - "mbstowcs_s (fonction)"
  - "mbstowcs_s_l (fonction)"
ms.assetid: 2fbda953-6918-498f-b440-3e7b21ed65a4
caps.latest.revision: 31
caps.handback.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# mbstowcs_s, _mbstowcs_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit une séquence de caractères multioctets en une séquence correspondante de caractères larges.  Versions de [mbstowcs, \_mbstowcs\_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md) avec des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
errno_t mbstowcs_s(  
   size_t *pReturnValue,  
   wchar_t *wcstr,  
   size_t sizeInWords,  
   const char *mbstr,  
   size_t count   
);  
errno_t _mbstowcs_s_l(  
   size_t *pReturnValue,  
   wchar_t *wcstr,  
   size_t sizeInWords,  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t mbstowcs_s(  
   size_t *pReturnValue,  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _mbstowcs_s_l(  
   size_t *pReturnValue,  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### Paramètres  
 \[out\] `pReturnValue`  
 Nombre de caractères convertis.  
  
 \[out\] `wcstr`  
 Adresse de la mémoire tampon du résultat de la conversion de la chaîne de caractères larges.  
  
 \[in\] `sizeInWords`  
 La taille de la mémoire tampon `wcstr` en mots.  
  
 \[in\]`mbstr`  
 L'adresse d'une séquence de caractères multioctets terminés par null.  
  
 \[in\] `count`  
 Le nombre maximal de caractères larges à stocker dans la mémoire tampon `wcstr`, à l'exclusion du null de fin, ou [\_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 \[in\] `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Zéro si l'opération a réussi, code d'erreur en cas de échec.  
  
|Condition d'erreur|Valeur de retour et`errno`|  
|------------------------|--------------------------------|  
|`wcstr` est `NULL` et `sizeInWords` \> 0|`EINVAL`|  
|`mbstr` est `NULL`|`EINVAL`|  
|La mémoire tampon de destination est trop petite pour contenir la chaîne convertie \(à moins que `count` est `_TRUNCATE`; consultez les notes ci\-dessous\)|`ERANGE`|  
|`wcstr` n'est  `NULL` et `sizeInWords` \=\= 0|`EINVAL`|  
  
 Si l'une de ces conditions d'erreur se produit, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à continuer, la fonction retourne un code d'erreur et définit `errno` comme indiqué dans la table.  
  
## Notes  
 La fonction `mbstowcs_s` convertit une chaîne de caractères multioctets pointés par `mbstr` vers des caractères stockés dans la mémoire tampon désignés par `wcstr`.  La conversion se poursuit pour chaque caractère tant qu'une des conditions suivantes est remplie :  
  
-   Un caractère NULL multioctets est produit  
  
-   Un caractères multioctets invalide est produit  
  
-   Le nombre de caractères larges stockés dans la mémoire tampon `wcstr` est égale à `count`.  
  
 La chaîne de destination est toujours terminée par null \(même en cas d'erreur\).  
  
 Si `count` est la valeur spéciale [\_TRUNCATE](../../c-runtime-library/truncate.md), alors `mbstowcs_s` convertit autant de la chaîne que ce qui s'insérera dans la mémoire tampon de destination, tout en laissant toujours de l'espace pour une marque de fin null.  
  
 Si `mbstowcs_s` convertit correctement la chaîne source, elle définit la taille en caractères larges de la chaîne convertie, notamment la marque de fin null, dans `*``pReturnValue` \( dans la cas où `pReturnValue` n'est pas `NULL`\).  Cela se produit même si l'argument `wcstr` est `NULL` et permet de déterminer la taille de mémoire tampon requise.  Notez que si `wcstr` est `NULL`, `count` est ignoré, et `sizeInWords` doit être 0.  
  
 Si  `mbstowcs_s` rencontre un caractères multioctets inalide, il renvoie 0 dans `*``pReturnValue`, associe la mémoire tampon de destination à une chaîne vide, définit `errno` à `EILSEQ`, et retourne `EILSEQ`.  
  
 Si les séquences désignées par `mbstr` et `wcstr` se chevauchent, le comportement de`mbstowcs_s` n'est pas défini.  
  
> [!IMPORTANT]
>  Vérifiez que `wcstr` et `mbstr` ne se chevauchent pas, et que `count` reflète fidèlement le nombre de caractères multioctets à convertir.  
  
 `mbstowcs_s` utilise les paramètres régionaux actuels pour tout comportement dépend des paramètres régionaux ; `_mbstowcs_s_l` est identique à la différence qu'il utilise les paramètres régionaux transmis à la place.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 En C\+\+, l'utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement \(ce qui évite d'avoir à spécifier un argument taille\) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalentes plus récentes et sécurisées.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`mbstowcs_s`|\<stdlib.h\>|  
|`_mbstowcs_s_l`|\<stdlib.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbtowc, \_mbtowc\_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs, \_wcstombs\_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)