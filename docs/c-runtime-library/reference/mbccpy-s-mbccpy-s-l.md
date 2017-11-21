---
title: _mbccpy_s, _mbccpy_s_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbccpy_s
- _mbccpy_s_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbccpy_s_l
- mbccpy_s_l
- mbccpy_s
- _mbccpy_s
dev_langs: C++
helpviewer_keywords:
- tccpy_s_l function
- _tccpy_s function
- _mbccpy_s function
- mbccpy_s function
- tccpy_s function
- mbccpy_s_l function
- _tccpy_s_l function
- _mbccpy_s_l function
ms.assetid: b6e965fa-53c1-4ec3-85ef-a1c4b4f2b2da
caps.latest.revision: "30"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 04c9091214928ecf7122868992974a0b0af9d3c6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="mbccpys-mbccpysl"></a>_mbccpy_s, _mbccpy_s_l
Copier un caractère multioctet d’une chaîne vers une autre chaîne. Ces versions de [_mbccpy, _mbccpy_l](../../c-runtime-library/reference/mbccpy-mbccpy-l.md) intègrent des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t _mbccpy_s(  
   unsigned char *dest,  
   size_t buffSizeInBytes,  
   int * pCopied,  
   const unsigned char *src   
);  
errno_t _mbccpy_s_l(  
   unsigned char *dest,  
   size_t buffSizeInBytes,  
   int * pCopied,  
   const unsigned char *src,  
   locale_t locale  
);  
template <size_t size>  
errno_t _mbccpy_s(  
   unsigned char (&dest)[size],  
   int * pCopied,  
   const unsigned char *src   
); // C++ only  
template <size_t size>  
errno_t _mbccpy_s_l(  
   unsigned char (&dest)[size],  
   int * pCopied,  
   const unsigned char *src,  
   locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>Paramètres  
 [out] `dest`  
 Destination de la copie.  
  
 [in] `buffSizeInBytes`  
 Taille de la mémoire tampon de destination.  
  
 [out] `pCopied`  
 Rempli avec le nombre d’octets copiés (1 ou 2 en cas de réussite). Transmettez `NULL` si le nombre n’a pas d’importance.  
  
 [in] `src`  
 Caractère multioctet à copier.  
  
 [in] `locale`  
 Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro si l'opération a réussi ; code d'erreur en cas de échec. Si `src` ou `dest` a la valeur `NULL` ou que plus de `buffSizeinBytes` octets seraient copiés vers `dest`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à continuer, les fonctions retournent `EINVAL` et `errno` est défini à `EINVAL`.  
  
## <a name="remarks"></a>Notes  
 La fonction `_mbccpy_s` copie un caractère multioctet depuis `src` vers `dest`. Si `src` ne pointe pas vers l’octet de tête d’un caractère multioctet comme déterminé par un appel implicite à [_ismbblead](../../c-runtime-library/reference/ismbblead-ismbblead-l.md), l’octet unique désigné par `src` est copié. Si `src` pointe vers un octet de tête, mais que l’octet suivant est 0 (donc non valide), 0 est copié vers `dest`, `errno` est défini sur `EILSEQ` et la fonction retourne `EILSEQ`.  
  
 `_mbccpy_s` n’ajoute pas de marque de fin Null ; toutefois, si `src` désigne un caractère Null, celui-ci est copié vers `dest` (il s’agit d’une copie sur un octet normale).  
  
 La valeur de `pCopied` est remplie avec le nombre d’octets copiés. Les valeurs possibles sont 1 et 2 si l’opération réussit. Si `NULL` est transmis, ce paramètre est ignoré.  
  
|`src`|Copié vers `dest`|`pCopied`|Valeur de retour|  
|-----------|----------------------|---------------|------------------|  
|Octet autre qu’un octet de tête|Octet autre qu’un octet de tête|1|0|  
|0|0|1|0|  
|Octet de tête suivi d’une valeur différente de 0|Octet de tête suivi d’une valeur différente de 0|2|0|  
|Octet de tête suivi de 0|0|1|`EILSEQ`|  
  
 Notez que la deuxième ligne est simplement un cas spécial de la première. Notez également que ce tableau suppose `buffSizeInBytes` >= `pCopied`.  
  
 `_mbccpy_s` utilise les paramètres régionaux actuels pour le comportement dépendant des paramètres régionaux. `_mbccpy_s_l` est identique à `_mbccpy_s`, à ceci près que `_mbccpy_s_l` utilise les paramètres régionaux passés pour tout comportement dépendant des paramètres régionaux.  
  
 En C++, l’utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire automatiquement la longueur de la mémoire tampon, ce qui évite d’avoir à spécifier un argument de taille. Pour plus d’informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine Tchar.h|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tccpy_s`|Mappe à la macro ou à la fonction inline.|`_mbccpy_s`|Mappe à la macro ou à la fonction inline.|  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_mbccpy_s`|\<mbstring.h>|  
|`_mbccpy_s_l`|\<mbstring.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)