---
title: _strninc, _wcsninc, _mbsninc, _mbsninc_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsninc
- _mbsninc_l
- _wcsninc
- _strninc
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
- strninc
- wcsninc
- mbsninc_l
- _strninc
- _tcsninc
- mbsninc
- _mbsninc_l
- _ftcsninc
- _wcsninc
- _mbsninc
dev_langs: C++
helpviewer_keywords:
- _mbsninc_l function
- mbsninc function
- _strninc function
- tcsninc function
- wcsninc function
- _mbsninc function
- strninc function
- _wcsninc function
- mbsninc_l function
- _tcsninc function
ms.assetid: 6caace64-f9e4-48c0-afa8-ea51824ad723
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 37bf361f9be420f2f2d54ae073a37afb1016f700
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="strninc-wcsninc-mbsninc-mbsnincl"></a>_strninc, _wcsninc, _mbsninc, _mbsninc_l
Fait avancer un pointeur de chaîne de `n` caractères.  
  
> [!IMPORTANT]
>  `_mbsninc` et `_mbsninc_l` ne peuvent pas être utilisées dans les applications qui s'exécutent dans Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
char *_strninc(  
   const char *str,  
   size_t count   
);  
wchar_t *_wcsninc(  
   const wchar_t *str,  
   size_t count   
);  
unsigned char *_mbsninc(  
   const unsigned char *str,  
   size_t count   
);  
unsigned char *_mbsninc(  
   const unsigned char *str,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `str`  
 Chaîne source.  
  
 `count`  
 Nombre de caractères dont un pointeur de chaîne est incrémenté.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 Chacune de ces routines retourne un pointeur vers `str` après que `str` a été incrémenté de `count` caractères ou `NULL` si le pointeur fourni a la valeur `NULL`. Si la valeur de `count` est supérieure ou égale au nombre de caractères contenus dans `str`, le résultat n’est pas défini.  
  
## <a name="remarks"></a>Notes  
 La fonction `_mbsninc` incrémente `str` de `count` caractères multioctets. `_mbsninc` reconnaît les séquences de caractères multioctets en fonction de la [page de codes multioctets](../../c-runtime-library/code-pages.md) en cours d’utilisation.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine Tchar.h|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tcsninc`|`_strninc`|`_mbsninc`|`_wcsninc`|  
  
 `_strninc`et `_wcsninc` sont une chaîne de caractères codés unique et les versions de chaîne à caractères larges de `_mbsninc`. `_wcsninc` et `_strninc` sont fournies uniquement pour ce mappage et ne doivent sinon pas être utilisées. Pour plus d’informations, consultez [Utilisation de mappages de texte générique](../../c-runtime-library/using-generic-text-mappings.md) et [Mappages de texte générique](../../c-runtime-library/generic-text-mappings.md).  
  
 La fonction `_mbsninc_l` est identique, sauf qu’elle utilise à la place les paramètres régionaux transmis. Pour plus d’informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_mbsninc`|\<mbstring.h>|  
|`_mbsninc_l`|\<mbstring.h>|  
|`_strninc`|\<tchar.h>|  
|`_wcsninc`|\<tchar.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_strdec, _wcsdec, _mbsdec, _mbsdec_l](../../c-runtime-library/reference/strdec-wcsdec-mbsdec-mbsdec-l.md)   
 [_strinc, _wcsinc, _mbsinc, _mbsinc_l](../../c-runtime-library/reference/strinc-wcsinc-mbsinc-mbsinc-l.md)   
 [_strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l](../../c-runtime-library/reference/strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)