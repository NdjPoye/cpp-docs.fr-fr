---
title: mbstowcs_s, _mbstowcs_s_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbstowcs_s_l
- mbstowcs_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbstowcs_s_l
- mbstowcs_s
dev_langs: C++
helpviewer_keywords:
- _mbstowcs_s_l function
- mbstowcs_s function
- mbstowcs_s_l function
ms.assetid: 2fbda953-6918-498f-b440-3e7b21ed65a4
caps.latest.revision: "31"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 822a7058afd6588be6f953c5c2b89d41ec02c87f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="mbstowcss-mbstowcssl"></a>mbstowcs_s, _mbstowcs_s_l
Convertit une séquence de caractères multioctets en séquence correspondante de caractères larges. Versions de [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md) intégrant les améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
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
  
#### <a name="parameters"></a>Paramètres  
 [out] `pReturnValue`  
 Nombre de caractères convertis.  
  
 [out] `wcstr`  
 Adresse de la mémoire tampon pour la chaîne de caractères larges convertie résultante.  
  
 [in] `sizeInWords`  
 Taille, en mots, de la mémoire tampon `wcstr`.  
  
 [in]`mbstr`  
 Adresse d’une séquence de caractères multioctets se terminant par un caractère Null.  
  
 [in] `count`  
 Nombre maximal de caractères larges à stocker dans la mémoire tampon `wcstr`, à l’exclusion du caractère Null de fin, ou [_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 [in] `locale`  
 Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro si l'opération a réussi, un code d'erreur en cas d'échec.  
  
|Condition d'erreur|Valeur de retour et `errno`|  
|---------------------|------------------------------|  
|`wcstr` a la valeur `NULL` et `sizeInWords` > 0|`EINVAL`|  
|`mbstr` a la valeur `NULL`.|`EINVAL`|  
|La mémoire tampon de destination est trop petite pour contenir la chaîne convertie (à moins que `count` ait la valeur `_TRUNCATE` ; consultez les notes ci-dessous)|`ERANGE`|  
|`wcstr` n’a pas la valeur `NULL` et `sizeInWords` == 0|`EINVAL`|  
  
 Si l’une de ces conditions se produit, l’exception de paramètre non valide est appelée, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à continuer, la fonction retourne un code d'erreur et définit `errno`, comme indiqué dans le tableau.  
  
## <a name="remarks"></a>Notes  
 La fonction `mbstowcs_s` convertit une chaîne de caractères multioctets désignés par `mbstr` en caractères larges stockés dans la mémoire tampon désignée par `wcstr`. La conversion se poursuit pour chaque caractère jusqu'à ce qu'une des conditions suivantes soit remplie :  
  
-   Un caractère multioctet de null est rencontré.  
  
-   Un caractère multioctet non valide est rencontré.  
  
-   Le nombre caractères larges stockés dans la mémoire tampon de `wcstr` est égal à `count`.  
  
 La chaîne de destination est toujours terminée par null (même en cas d'erreur).  
  
 Si `count` correspond à la valeur spéciale [_TRUNCATE](../../c-runtime-library/truncate.md), `mbstowcs_s` convertit la plus grande partie possible de la chaîne en fonction de la capacité de la mémoire tampon de destination, tout en laissant de l’espace pour une marque de fin Null.  
  
 Si la fonction `mbstowcs_s` convertit correctement la chaîne source, elle place la taille en caractères larges de la chaîne convertie, y compris la marque de fin Null, dans `*pReturnValue` (à condition que `pReturnValue` n’ait pas la valeur `NULL`). Cela se produit même si l'argument `wcstr` a la valeur `NULL`, et permet de déterminer la taille de mémoire tampon requise. Notez que si `wcstr` a la valeur `NULL`, `count` est ignoré et `sizeInWords` doit avoir la valeur 0.  
  
 Si la fonction `mbstowcs_s` rencontre un caractère multioctet non valide, elle affecte la valeur 0 à `*pReturnValue`, définit la mémoire tampon de destination sur une chaîne vide, affecte à `errno` la valeur `EILSEQ` et retourne `EILSEQ`.  
  
 Si les séquences pointées par `mbstr` et `wcstr` se chevauchent, le comportement de `mbstowcs_s` n'est pas défini.  
  
> [!IMPORTANT]
>  Vérifiez que `wcstr` et `mbstr` ne se chevauchent pas, et que `count` reflète correctement le nombre de caractères multioctets à convertir.  
  
 La fonction `mbstowcs_s` utilise les paramètres régionaux actifs pour tout comportement dépendant des paramètres régionaux ; la fonction `_mbstowcs_s_l` est identique sauf qu’elle utilise à la place les paramètres régionaux transmis. Pour plus d’informations, consultez [Locale](../../c-runtime-library/locale.md).  
  
 En C++, l’utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement (ce qui évite d’avoir à spécifier un argument taille) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalentes plus récentes et sécurisées. Pour plus d'informations, consultez [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`mbstowcs_s`|\<stdlib.h>|  
|`_mbstowcs_s_l`|\<stdlib.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)