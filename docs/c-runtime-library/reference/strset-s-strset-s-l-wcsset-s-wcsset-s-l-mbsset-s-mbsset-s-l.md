---
title: _strset_s, _strset_s_l, _wcsset_s, _wcsset_s_l, _mbsset_s, _mbsset_s_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wcsset_s
- _wcsset_s_l
- _strset_s
- _mbsset_s_l
- _strset_s_l
- _mbsset_s
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wcsset_s_l
- strset_s
- _mbsset_s
- mbsset_s
- _strset_s
- _mbsset_s_l
- strset_s_l
- _wcsset_s
- mbsset_s_l
- wcsset_s_l
- wcsset_s
- _strset_s_l
- _tcsset_s_l
- _tcsset_s
dev_langs:
- C++
helpviewer_keywords:
- mbsset_s_l function
- wcsset_s function
- _mbsset_s function
- tcsset_s function
- strset_s_l function
- characters [C++], setting
- _wcsset_s_l function
- _strset_s function
- strset_s function
- wcsset_s_l function
- strings [C++], setting characters
- _strset_s_l function
- _mbsset_s_l function
- _wcsset_s function
- tcsset_s_l function
- _tcsset_s_l function
- _tcsset_s function
- mbsset_s function
ms.assetid: dceb2909-6b41-4792-acb7-888e45bb8b35
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: bf90cc3bd9935a3070581d7c74fa2b65054f93bc
ms.lasthandoff: 02/24/2017

---
# <a name="strsets-strsetsl-wcssets-wcssetsl-mbssets-mbssetsl"></a>_strset_s, _strset_s_l, _wcsset_s, _wcsset_s_l, _mbsset_s, _mbsset_s_l
Remplace les caractères d’une chaîne par un caractère. Ces versions de [_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md) intègrent les améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  `_mbsset_s` et `_mbsset_s_l` ne peuvent pas être utilisées dans les applications qui s'exécutent dans Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t _strset_s(  
   char *str,  
   size_t numberOfElements,  
   int c   
);  
errno_t _strset_s_l(  
   char *str,  
   size_t numberOfElements,  
   int c,  
   locale_t locale  
);  
errno_t _wcsset_s(  
   wchar_t *str,  
   size_t numberOfElements,  
   wchar_t c   
);  
errno_t *_wcsset_s_l(  
   wchar_t *str,  
   size_t numberOfElements,  
   wchar_t c,  
   locale_t locale  
);  
errno_t _mbsset_s(  
   unsigned char *str,  
   size_t numberOfElements,  
   unsigned int c   
);  
errno_t _mbsset_s_l(  
   unsigned char *str,  
   size_t numberOfElements,  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `str`  
 Chaîne se terminant par un caractère Null à définir.  
  
 `numberOfElements`  
 Taille de la mémoire tampon `str`.  
  
 `c`  
 Paramètre de caractère.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro en cas de réussite ; code d’erreur dans un autre cas.  
  
 Ces fonctions valident leurs arguments. Si `str` est un pointeur Null ou que l’argument `numberOfElements` est inférieur ou égal à 0 ou encore que le bloc transmis ne se termine pas par un caractère Null, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions retournent `EINVAL` et définissent `errno` avec la valeur `EINVAL`.  
  
## <a name="remarks"></a>Notes  
 La fonction `_strset_s` remplace tous les caractères de `str` par `c` (converti en `char`), à l’exclusion du caractère Null de fin. `_wcsset_s` et `_mbsset_s` sont des versions à caractères larges et à caractères multioctets de `_strset_s`. Les types de données des arguments et des valeurs de retour varient en conséquence. Ces fonctions se comportent sinon de façon identique.  
  
 La valeur de sortie est affectée par la valeur du paramètre de catégorie `LC_CTYPE` des paramètres régionaux. Pour plus d’informations, consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux transmis. Pour plus d’informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Les versions debug de ces fonctions remplissent d'abord la mémoire tampon avec 0xFD. Pour désactiver ce comportement, utilisez [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsset_s`|`_strset_s`|`_mbsset_s`|`_wcsset_s`|  
|`_tcsset_s_l`|`_strset_s_l`|`_mbsset_s_l`|`_wcsset_s_l`|  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_strset_s`|\<string.h>|  
|`_strset_s_l`|\<tchar.h>|  
|`_wcsset_s`|\<string.h> ou \<wchar.h>|  
|`_wcsset_s_l`|\<tchar.h>|  
|`_mbsset_s`, `_mbsset_s_l`|\<mbstring.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_strset_s.c  
#include <string.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char string[] = "Fill the string with something.";  
   printf( "Before: %s\n", string );  
   _strset_s( string, _countof(string), '*' );  
   printf( "After:  %s\n", string );  
}  
```  
  
```Output  
Before: Fill the string with something.  
After:  *******************************  
```  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbsnbset, _mbsnbset_l](../../c-runtime-library/reference/mbsnbset-mbsnbset-l.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcat, wcscat, _mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcpy, wcscpy, _mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [_strnset, _strnset_l, _wcsnset, _wcsnset_l, _mbsnset, _mbsnset_l](../../c-runtime-library/reference/strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)
